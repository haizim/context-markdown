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