[#](#importables) Importables
=============================

*   [Importing](#importing)
*   [Queuing](#queuing)
*   [To array](#to-array)
*   [To collection](#to-collection)

In the previous example, we used the `Excel::import` facade to start an import.

Laravel Excel also provides a `Maatwebsite\Excel\Concerns\Importable` trait, to make import classes importable.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    
    class UsersImport implements ToModel
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
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

[#](#importing) Importing
-------------------------

We can now import without the need for the facade:

    (new UsersImport)->import('users.xlsx', 'local', \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#queuing) Queuing
---------------------

Or queue the import:

    (new UsersImport)->queue('users.xlsx');
    

1  

[#](#to-array) To array
-----------------------

The import can be loaded into an array :

    $array = (new UsersImport)->toArray('users.xlsx');
    

1  

[#](#to-collection) To collection
---------------------------------

The import can be loaded into a collection:

    $collection = (new UsersImport)->toCollection('users.xlsx');
    

1