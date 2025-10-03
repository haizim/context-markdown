## === concerns.md ===

[#](#concerns) Concerns
=======================

*   [Contracts](#contracts)
*   [Pointer interface](#pointer-interface)

Most of the export/import configuration is done by using **Concerns**.

[#](#contracts) Contracts
-------------------------

Concerns are basically just simple interfaces. Implementing them will make the object adhere to a certain contract. This contract can request specific methods that e.g. data can be passed through.

For instance, the `FromCollection` requests the Export object to implement a `collection` method, that needs to return a `Collection` instance.

    namespace App\Exports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\FromCollection;
    
    class UsersExport implements FromCollection
    {
        public function collection()
        {
            return User::all();
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

[#](#pointer-interface) Pointer interface
-----------------------------------------

In other cases it might not ask for any methods to be implemented, but merely functions as a pointer interface.

For instance, the `ShouldAutoSize` concern doesn't pass on any specific information, but does tell the Export process that the columns need to be automatically sized.

    namespace App\Exports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ShouldAutoSize;
    
    class UsersExport implements ShouldAutoSize
    {
    
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

## === index.md ===

[#](#lifecycle) Lifecycle
=========================

*   [Introduction](#introduction)
*   [Exports Lifecycle Overview](#exports-lifecycle-overview)
    *   [Export Object](#export-object)
    *   [Passing on the Export object](#passing-on-the-export-object)
    *   [Handling the Export object](#handling-the-export-object)
    *   [Passing on to PhpSpreadsheet](#passing-on-to-phpspreadsheet)
    *   [Creating a Response](#creating-a-response)
*   [Imports Lifecycle Overview](#imports-lifecycle-overview)
    *   [Import Object](#import-object)
    *   [Passing on the Import object](#passing-on-the-import-object)
    *   [Handling the Import object](#handling-the-import-object)

[#](#introduction) Introduction
-------------------------------

When using a package in your application, it's good to understand how the package functions behind the scenes. Understanding the behind-the-scenes will make you feel more comfortable and confident using the maximum potential of the tool.

The goal of this page is to give you a high-level overview of how Laravel Excel works.

[#](#exports-lifecycle-overview) Exports Lifecycle Overview
-----------------------------------------------------------

This section will try to give you an overview of how the export works behind the scenes.

### [#](#export-object) Export Object

Everything starts with the `Export` object. This object **encapsulates** your entire export logic. It both configures and handles the export logic.

A simple example of an export object is:

    <?php
    
    namespace App\Exports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\FromCollection;
    
    class UsersExport implements FromCollection
    {
        public function collection()
        {
            return User::all();
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

If you want to read more about export objects, go to the architecture page of [export objects](/3.1/architecture/objects.html).

### [#](#passing-on-the-export-object) Passing on the Export object

Next the Export object will be passed on to the Laravel Excel package. The main entry point for this is the `Maatwebsite/Excel/Excel` class. This class can be called in multiple ways.

#### [#](#facade) Facade

The easiest way to work with the `Excel` class is to use the `Maatwebsite\Excel\Facades\Excel` facade. If you use [auto-discovery (opens new window)](https://laravel.com/docs/packages#package-discovery), you can use the alias `\Excel` directly instead of using the fully qualified namespace.

#### [#](#dependency-injection) Dependency injection

You can inject the `Maatwebsite/Excel/Excel` manager class into your class, either via constructor injection or method injection in case of a controller.

    <?php
    use App\Exports\UsersExport;
    use Maatwebsite\Excel\Excel;
    
    class ExportController
    {
        private $excel;
    
        public function __construct(Excel $excel)
        {
            $this->excel = $excel;
        }
        
        public function exportViaConstructorInjection()
        {
            return $this->excel->download(new UsersExport, 'users.xlsx');
        }
        
        public function exportViaMethodInjection(Excel $excel)
        {
            return $excel->download(new UsersExport, 'users.xlsx');
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

#### [#](#contract) Contract

You can also use the `Maatwebsite\Excel\Exporter` interface to decouple more from the concrete Excel manager implementation. The contract offers the same methods as the `Excel` class. It will make it easier to e.g. stub out the Exporter in your unit tests. The `Exporter` contract can be either injected via the constructor or a method in a controller.

    use App\Exports\UsersExport;
    use Maatwebsite\Excel\Exporter;
    
    class ExportsController
    {
        private $exporter;
    
        public function __construct(Exporter $exporter)
        {
            $this->exporter = $exporter;
        }
        
        public function export()
        {
            return $this->exporter->download(new UsersExport, 'users.xlsx');
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

#### [#](#container-binding) Container binding

If you want to bind the `Maatwebsite\Excel\Excel` manager to your own class via a container binding, you can use the `excel` container binding.

    $this->app->bind(YourCustomExporter::class, function() {
        return new YourCustomExporter($this->app['excel']);
    });
    

1  
2  
3  

#### [#](#exportable-trait) Exportable trait

If you prefer a sprinkle of magic, you can use the `Maatwebsite\Excel\Concerns\Exportable` trait in your `Export` object. This trait will expose a couple of methods that will make it possible to directly export an `Export` object.

    namespace App\Exports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\FromCollection;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class UsersExport implements FromCollection
    {
        use Exportable;
    
        public function collection()
        {
            return User::all();
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

You can now download the export without the need for the `facade` or `Excel` manager.

    return (new UsersExport)->download('users.xlsx');
    

1  

Read more about the exportable trait in the [exportables](/3.1/exports/exportables.html) docs.

### [#](#handling-the-export-object) Handling the Export object

#### [#](#writer-type-detection) Writer type detection

After using one of the above methods to pass on the `Export` object to the `Excel` manager, it will try to figure out what export it needs to be generated to. This will be either based on the extension of the file, the explicitly passed writer type. You can find the extension to writer type mapping in the `excel.php` config, in the `extension_detector` section. In case no writer type can be detected, a `Maatwebsite\Excel\Exceptions\NoTypeDetectedException` exception is thrown and the export process will be stopped.

#### [#](#starting-the-writing-process) Starting the Writing process

The `Excel` manager will then delegate the handling to the `Maatwebsite\Excel\Writer`. The first action of the `Writer` is to register the event listeners that are registered. Next it will create a new `PhpOffice\PhpSpreadsheet\Spreadsheet` instance that we will use to convert our `Export` object to.

The first event raised is the `BeforeExport` event. This is raised just after the `Spreadsheet` instance is created and allows early access to it.

#### [#](#multiple-sheets) Multiple sheets

Next the `Writer` will determine if multiple sheets are configured, by checking for the `Maatwebsite\Excel\Concerns\WithMultipleSheets` concern.

Then it will delegate the further handling of each sheet to the `Maatwebsite\Excel\Sheet` class.

#### [#](#processing-the-sheets) Processing the sheets

In the `Sheet` class, the most heavy lifting happens. It first will create a `PhpOffice\PhpSpreadsheet\Worksheet\Worksheet` instance. Then it will raise the `BeforeSheet` event which allows you to hook into the moment just before the sheet handling starts.

Then it will determine what kind of export we are dealing with: `FromQuery`, `FromArray`, `FromCollection` or `FromView`. Based on that it will start the connected export process.

*   `FromView` will pass on the rendered `Blade` view to PhpSpreadsheet's `Html` Reader. That Reader will turn the table html into Excel cells. It also handles some inline styles (color and background color) and col/rowspans.
*   The **Query** passed with the `FromQuery` will automatically be chunked and each chunk will be appended to the Sheet. The chunking is done to limit the amount of Eloquent objects it needs to keep in memory. It greatly reduces memory usage.
*   The entire array of Collection will directly be appended to the Sheet.

When the `Sheet` starts appending records, it will first call the `map()` method if the `WithMapping` concern is used. This allows the `Export` object to format the data before it is inserted.

Then it will handle column formatting (`WithColumnFormatting` concern) and cell autosizing (`ShouldAutoSize`).

To close off the Sheet processing, it will raise a `AfterSheet` event.

### [#](#passing-on-to-phpspreadsheet) Passing on to PhpSpreadsheet

After the sheets are processed, the writing process will start. The writing process is started by raising the `BeforeWriting` event; this allows you to hook into the process of writing. Next we will create a new `PhpSpreadsheet Writer` based on the writer type that was determined. Then it will save it to a temporary file and return that filepath to the `Excel` manager.

### [#](#creating-a-response) Creating a Response

The `Excel` manager basically has 2 types of responses, it either starts the **download** process or it will **store** the file to disk.

#### [#](#download-the-file) Download the file

We will take the temporary file that was returned by the `Writer` and use Laravel's `ResponseFactory` to create a `Symfony\Component\HttpFoundation\BinaryFileResponse`. When returning this response in your controller, it will start a download.

#### [#](#storing-the-file) Storing the file

The storing of the file will be handled by Laravel's `Filesystem`. By default the file will be stored on your `default` disk, but you can also pass a custom disk via the `Excel::store()` method.

[#](#imports-lifecycle-overview) Imports Lifecycle Overview
-----------------------------------------------------------

This section will try to give you an overview of how the import works behind the scenes.

### [#](#import-object) Import Object

Everything starts with the `Import` object. This object **encapsulates** your entire import logic. It both configures and handles the import logic.

A simple example of an import object is:

    namespace App\Imports;
    
    use App\User;
    use Illuminate\Support\Collection;
    use Maatwebsite\Excel\Concerns\ToCollection;
    
    class UsersImport implements ToCollection
    {
        public function collection(Collection $rows)
        {
            foreach ($rows as $row) 
            {
                User::create([
                    'name' => $row[0],
                ]);
            }
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

If you want to read more about imports objects, go to the architecture page of [imports objects](/3.1/architecture/objects.html).

### [#](#passing-on-the-import-object) Passing on the Import object

Next the Import object will be passed on to the Laravel Excel package. The main entry point for this is the `Maatwebsite/Excel/Excel` class. This class can be called in the same way as outlined in the Export lifecycle.

#### [#](#contract-2) Contract

You can also use the `Maatwebsite\Excel\Importer` interface to decouple more from the concrete Excel manager implementation. The contract offers the same methods as the `Excel` class. It will make it easier to e.g. stub out the Importer in your unit tests. The `Importer` contract can be either injected via the constructor or the method of a controller.

    use App\Imports\UsersImport;
    use Maatwebsite\Excel\Importer;
    
    class ImportsController
    {
        private $importer;
    
        public function __construct(Importer $importer)
        {
            $this->importer = $importer;
        }
        
        public function import()
        {
            return $this->importer->import(new UsersImport, 'users.xlsx');
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

#### [#](#importable-trait) Importable trait

If you prefer a sprinkle of magic, you can use the `Maatwebsite\Excel\Concerns\Importable` trait in your `Import` object. This trait will expose a couple of methods that will make it possible to directly import an `Import` object.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToCollection;
    use Maatwebsite\Excel\Concerns\Importable;
    
    class UsersImport implements ToCollection
    {
        use Importable;
    
        ...
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

You can now import without the need for the `facade` or `Excel` manager.

    (new UsersImport)->import('users.xlsx');
    

1  

Read more about the importable trait in the [importables](/3.1/imports/importables.html) docs.

### [#](#handling-the-import-object) Handling the Import object

#### [#](#reader-type-detection) Reader type detection

After using one of the above methods to pass on the `Import` object to the `Excel` manager, it will try to figure out what reader type it is . This will be either based on the extension of the file or the explicitly passed reader type. You can find the extension to reader type mapping in the `excel.php` config, in the `extension_detector` section. In case no reader type can be detected, a `Maatwebsite\Excel\Exceptions\NoTypeDetectedException` exception is thrown and the import process will be stopped.

#### [#](#starting-the-reading-process) Starting the Reading process

The `Excel` manager will then delegate the handling to the `Maatwebsite\Excel\Reader`. The first action of the `Reader` is to register the event listeners that are registered. It will copy the file from Laravel's `Filesystem` to the local filesystem, so PhpSpreadsheet can read it. Next it will create a PhpSpreadsheet `Reader` based on the reader type that was given and load the file into a `PhpOffice\PhpSpreadsheet\Spreadsheet` instance.

Next it will create a new `PhpOffice\PhpSpreadsheet\Spreadsheet` instance that we will use to read our `Import` object from.

The first event that is raised, is the `BeforeImport` event. This is raised just after the `Spreadsheet` instance is loaded and allows early access to it.

#### [#](#multiple-sheets-2) Multiple sheets

Next we will determine if we are dealing with multiple sheets. This is done based on the `WithMultipleSheets` concern.

#### [#](#processing-the-sheets-2) Processing the sheets

Then each Sheet gets processed. This process gets started off by raising the `BeforeSheet` event. Then it will either import it to a Collection, an array or handle each row as an Eloquent model.

*   When using `ToModel`, each returned model will be persisted via Eloquent. When using this in combination with `WithBatchInserts`, it will defer the persistence till the batch is complete and then insert them as one batch in the database.
*   When using `ToCollection` or `ToArray`, the entire dataset will be passed to the Import method and the user can determine itself how to use it.

The sheet handling is ended by raising the `AfterSheet` event.

## === objects.md ===

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