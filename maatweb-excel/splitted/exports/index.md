[#](#_5-minute-quick-start) 🚀 5 minute quick start
===================================================

💪 Create an export class in `app/Exports`

You may do this by using the `make:export` command.

    php artisan make:export UsersExport --model=User
    

1  

The file can be found in `app/Exports`:

    .
    ├── app
    │   ├── Exports
    │   │   ├── UsersExport.php
    │ 
    └── composer.json
    

If you prefer to create the export manually, you can create the following in `app/Exports`:

    <?php
    
    namespace App\Exports;
    
    use App\Models\User;
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

🔥 In your controller you can call this export now:

    <?php
    
    namespace App\Http\Controllers;
    
    use App\Exports\UsersExport;
    use Maatwebsite\Excel\Facades\Excel;
    
    class UsersController extends Controller 
    {
        public function export() 
        {
            return Excel::download(new UsersExport, 'users.xlsx');
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

And finally add a route to be able to access the export:

    Route::get('users/export/', [UsersController::class, 'export']);
    

1  

📄 Find your `users.xlsx` in your downloads folder!