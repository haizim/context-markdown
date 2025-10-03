[#](#queued) Queued
===================

*   [Implicit Export queueing](#implicit-export-queueing)
*   [Appending jobs](#appending-jobs)
*   [Handling failures in queued exports](#handling-failures-in-queued-exports)
*   [Custom queues](#custom-queues)
*   [Multi-server setup](#multi-server-setup)
*   [Job Middleware](#job-middleware)
*   [Localizing Queued Export](#localizing-queued-export)
*   [Custom Query Size](#custom-query-size)
    *   [When to use](#when-to-use)

In case you are working with a lot of data, it might be wise to queue the entire process.

Given we have the following export class:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\Exportable;
    use Maatwebsite\Excel\Concerns\FromQuery;
    
    class InvoicesExport implements FromQuery
    {
        use Exportable;
    
        public function query()
        {
            return Invoice::query();
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

It's as easy as calling `->queue()` now.

    (new InvoicesExport)->queue('invoices.xlsx');
    
    return back()->withSuccess('Export started!');
    

1  
2  
3  

Behind the scenes the query will be chunked and multiple jobs will be chained. These jobs will be executed in the correct order, and will only execute if none of the previous have failed.

[#](#implicit-export-queueing) Implicit Export queueing
-------------------------------------------------------

You can also mark an export implicitly as a queued export. You can do this by using Laravel's `ShouldQueue` contract.

    namespace App\Exports;
    
    use App\Invoice;
    use Illuminate\Contracts\Queue\ShouldQueue;
    use Maatwebsite\Excel\Concerns\Exportable;
    use Maatwebsite\Excel\Concerns\FromQuery;
    
    class InvoicesExport implements FromQuery, ShouldQueue
    {
        use Exportable;
    
        public function query()
        {
            return Invoice::query();
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

In your controller you can now call the normal `->store()` method. Based on the presence of the `ShouldQueue` contract, the export will be queued.

    (new InvoicesExport)->store('invoices.xlsx');
    

1  

[#](#appending-jobs) Appending jobs
-----------------------------------

The `queue()` method returns an instance of Laravel's `PendingDispatch`. This means you can chain extra jobs that will be added to the end of the queue and only executed if all export jobs are correctly executed.

    (new InvoicesExport)->queue('invoices.xlsx')->chain([
        new NotifyUserOfCompletedExport(request()->user()),
    ]);
    

1  
2  
3  

    namespace App\Jobs;
    
    use App\User;
    use Illuminate\Bus\Queueable;
    use Illuminate\Contracts\Queue\ShouldQueue;
    use Illuminate\Queue\SerializesModels;
    
    class NotifyUserOfCompletedExport implements ShouldQueue
    {
        use Queueable, SerializesModels;
        
        public $user;
        
        public function __construct(User $user)
        {
            $this->user = $user;
        }
    
        public function handle()
        {
            $this->user->notify(new ExportReady());
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

[#](#handling-failures-in-queued-exports) Handling failures in queued exports
-----------------------------------------------------------------------------

When queuing exports you might want a way to handle failed exports. You can do this by adding `failed` method to your export class.

    
    use Throwable;
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithHeadings;
    
    class UsersExport implements FromQuery, WithHeadings
    {   
        public function failed(Throwable $exception): void
        {
            // handle failed export
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

[#](#custom-queues) Custom queues
---------------------------------

Because `PendingDispatch` is returned, we can also change the queue that should be used.

For Laravel 8+:

    (new InvoicesExport)->queue('invoices.xlsx')->onQueue('exports');
    

1  

For older versions of Laravel:

    (new InvoicesExport)->queue('invoices.xlsx')->allOnQueue('exports');
    

1  

[#](#multi-server-setup) Multi-server setup
-------------------------------------------

If you are dealing with a multi-server setup (using e.g. a loadbalancer), you might want to make sure the temporary file that is used to store each chunk of data on, is the same for each job. You can achieve this by configuring a remote temporary file in the config.

In `config/excel.php`

    'temporary_files' => [
        'remote_disk' => 's3',
    ],
    

1  
2  
3  

[#](#job-middleware) Job Middleware
-----------------------------------

If you are using Laravel 6, [job middleware (opens new window)](https://laravel.com/docs/6.x/queues#job-middleware) can be attached to the export class using the `middleware` method:

    namespace App\Exports;
    
    use App\Jobs\Middleware\RateLimited;
    use Maatwebsite\Excel\Concerns\Exportable;
    use Maatwebsite\Excel\Concerns\FromQuery;
    
    class ExportClass implements FromQuery
    {
        use Exportable;
        
        public function middleware()
        {
            return [new RateLimited];
        }
    
        public function query()
        {
            // ...
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

[#](#localizing-queued-export) Localizing Queued Export
-------------------------------------------------------

If you want to localize your queued export you should implement `HasLocalePreference` contract on your export:

    namespace App\Exports;
    
    use Illuminate\Contracts\Translation\HasLocalePreference;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class ExportClass implements HasLocalePreference
    {
        use Exportable;
        
        public function __construct(string $locale)
        {
            $this->locale = $locale;
        }
        
        public function preferredLocale()
        {
            return $this->locale;
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

[#](#custom-query-size) Custom Query Size
-----------------------------------------

Queued exportables are processed in chunks; each chunk being a job pushed to the queue by the `QueuedWriter`. In case of exportables that implement the [FromQuery](/3.1/exports/from-query.html) concern, the number of jobs is calculated by dividing the `$query->count()` by the chunk size.

### [#](#when-to-use) When to use

Depending on the implementation of the `query()` method (e.g. when using a `groupBy` clause), the calculation mentioned before might not be correct.

If this is the case, you should use the `WithCustomQuerySize` concern to provide a custom calculation of the query size.