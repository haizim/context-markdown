[#](#importing-basics) Importing basics
---------------------------------------

*   [Importing basics](#importing-basics)
*   [Importing from default disk](#importing-from-default-disk)
    *   [Importing from another disk](#importing-from-another-disk)
*   [Importing uploaded files](#importing-uploaded-files)
    *   [Importing full path](#importing-full-path)
*   [Importing to array or collection](#importing-to-array-or-collection)
*   [Specifying a reader type](#specifying-a-reader-type)

If you have followed the 5 minute quick start, you'll already have a `UsersImport` class.

    <?php
    
    namespace App\Imports;
    
    use App\Models\User;
    use Illuminate\Support\Facades\Hash;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        /**
         * @param array $row
         *
         * @return User|null
         */
        public function model(array $row)
        {
            return new User([
               'name'     => $row[0],
               'email'    => $row[1],
               'password' => Hash::make($row[2]),
            ]);
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
24  

[#](#importing-from-default-disk) Importing from default disk
-------------------------------------------------------------

Passing the UsersImport object to the `Excel::import()` method will tell the package how to import the file that is passed as second parameter. The file is expected to be located in your default filesystem disk (see `config/filesystems.php`).

    Excel::import(new UsersImport, 'users.xlsx');
    

1  

### [#](#importing-from-another-disk) Importing from another disk

You can specify another disk with the third parameter like your Amazon s3 disk. (see `config/filesystems.php`)

    Excel::import(new UsersImport, 'users.xlsx', 's3');
    

1  

[#](#importing-uploaded-files) Importing uploaded files
-------------------------------------------------------

If you let your user upload the document, you can also just pass the uploaded file directly.

    Excel::import(new UsersImport, request()->file('your_file'));
    

1  

### [#](#importing-full-path) Importing full path

If you want to specifiy the path where your file is, without having to move it to a disk, you can directly pass that file path to the import method.

    Excel::import(new UsersImport, storage_path('users.xlsx'));
    

1  

[#](#importing-to-array-or-collection) Importing to array or collection
-----------------------------------------------------------------------

If you want to bypass the `ToArray` or `ToCollection` concerns and want to have an array of imported data in your controller (beware of performance!), you can use the `::toArray()` or `::toCollection()` method.

    $array = Excel::toArray(new UsersImport, 'users.xlsx');
    
    $collection = Excel::toCollection(new UsersImport, 'users.xlsx');
    

1  
2  
3  

[#](#specifying-a-reader-type) Specifying a reader type
-------------------------------------------------------

If the reader type is not detectable by the file extension, you can specify a reader type by passing it as fourth parameter.

    Excel::import(new UsersImport, 'users.xlsx', 's3', \Maatwebsite\Excel\Excel::XLSX);
    

1