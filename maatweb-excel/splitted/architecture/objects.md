[#](#import-export-objects) Import & Export Objects
===================================================

*   [Directory structure](#directory-structure)
*   [Encapsulation](#encapsulation)
*   [Data transfer object](#data-transfer-object)
*   [Plain Old PHP Object](#plain-old-php-object)
    *   [Constructor](#constructor)
    *   [Setters](#setters)
    *   [Getters](#getters)
*   [Concerns](#concerns)
*   [Hooks](#hooks)

The entire Laravel Excel philosophy evolves around having `Export` and/or `Import` objects.

[#](#directory-structure) Directory structure
---------------------------------------------

The location of these Import and Exports classes could be as follows:

    .
    ├── app
    │   ├── Exports (Groups all exports in your app)
    │   │   ├── UsersExport.php
    │   │   ├── ProductsExport.php
    │   │   └── Sheets (You can group sheets together)
    │   │      ├── InactiveUsersSheet.php
    │   │      └── ActiveUsersSheet.php
    |   |
    │   ├── Imports (Groups all imports in your app)
    │   │   ├── UsersImport.php
    │   │   ├── ProductsImport.php
    │   │   └── Sheets (You can group sheets together)
    │   │      ├── OutOfStockProductsSheet.php
    │   │      └── ProductsOnSaleSheet.php
    │ 
    └── composer.json
    

[#](#encapsulation) Encapsulation
---------------------------------

These objects encapsulate the entire export or import process. The idea behind it is that you can neatly use these objects in controllers, services, jobs, event listeners or commands. In all of theses cases, the entire logic of how the export/import needs to happen is kept within this object.

[#](#data-transfer-object) Data transfer object
-----------------------------------------------

The import/export objects are in essence simple data transfer objects (DTO). This means they will transfer the information you want to export/import to the Excel writer/reader. This information is not only the actual data you want to export, but also additional information like the styling of the file, the name of the worksheet, the number format of the cell etc.

In most cases, this means that your code doesn't need to have direct exposure to the actual read/write process.

[#](#plain-old-php-object) Plain Old PHP Object
-----------------------------------------------

Besides being a DTO, the import/export objects are also just Plain Old PHP Objects (POPO). This means that you can do anything with them that you can do with normal PHP objects.

### [#](#constructor) Constructor

For instance, you can simply inject data through the constructor of the export object.

    class UsersExport implements FromCollection {
        private $year;
    
        public function __construct(int $year) 
        {
            $this->year = $year;
        }
        
        public function collection()
        {
            return Users::whereYear('created_at', $this->year)->get();
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  

    Excel::download(new UsersExport(2019), 'users.xlsx');
    

1  

### [#](#setters) Setters

Another option is to add setters for data that you want to pass.

    class UsersExport implements FromCollection {
        private $year;
    
        public function setYear(int $year)
        {
            $this->year = $year;
        }
        
        public function collection()
        {
            return Users::whereYear('created_at', $this->year)->get();
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  

    $export = new UsersExport();
    $export->setYear(2019);
    
    Excel::download($export, 'users.xlsx');
    

1  
2  
3  
4  

### [#](#getters) Getters

In similar fashion to setters, you can also add getters. This can potentially be useful if you want to keep a state of your export/import.

For instance, you can keep a row count in your users import.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        private $rows = 0;
    
        public function model(array $row)
        {
            ++$this->rows;
        
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function getRowCount(): int
        {
            return $this->rows;
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  
21  
22  
23  

After doing the import, we can request the state with the getter.

    $import = new UsersImport;
    Excel::import($import, 'users.xlsx');
    
    dd('Row count: ' . $import->getRowCount()); 
    

1  
2  
3  
4  

[#](#concerns) Concerns
-----------------------

Most of the export/import configuration is done by using **Concerns**. Concerns are basically just simple interfaces. Implementing them will make the object adhere to a certain contract. This contract can request specific methods that e.g. data can be passed through. In other cases it might not ask for any methods to be implemented, but merely functions as a pointer interface.

Read more about Concerns in the [concerns documentation](/3.1/architecture/concerns.html).

[#](#hooks) Hooks
-----------------

In more complex cases you might want to hook into certain moments of the read/write process. This can be done by using Events. To register these events in your import/export object, you need to implement the `Maatwebsite\Excel\Concerns\WithEvents` concern.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\BeforeExport;
    
    class UsersExport implements WithEvents
    {
        /**
         * @return array
         */
        public function registerEvents(): array
        {
            return [
                // Handle by a closure.
                BeforeExport::class => function(BeforeExport $event) {
                    // Do something before the export process starts.
                },
            ];
        }
    }
    

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15  
16  
17  
18  
19  
20  

Alternatively, you can also configure these listeners globally if you want it to happen to any export.

    Writer::listen(BeforeExport::class, function () {
        // Do something before any export process starts.
    });
    

1  
2  
3