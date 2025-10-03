[#](#from-query) From Query
===========================

*   [Customizing the query](#customizing-the-query)
    *   [As constructor parameter](#as-constructor-parameter)
    *   [As setter](#as-setter)
    *   [Macro's and Mixins](#macro-s-and-mixins)

In the previous example, we did the query inside the export class. While this is a good solution for small exports, for bigger exports this will come at a hefty performance price.

By using the `FromQuery` concern, we can prepare a query for an export. Behind the scenes this query is executed in chunks.

In the `InvoicesExport` class, add the `FromQuery` concern and return a query. Be sure to **not** `->get()` the results!

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\Exportable;
    
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

We can still download the export in the same way:

    return (new InvoicesExport)->download('invoices.xlsx');
    

1  

[#](#customizing-the-query) Customizing the query
-------------------------------------------------

It's easy to pass custom parameters to the query, by simply passing them as dependencies to the export class.

### [#](#as-constructor-parameter) As constructor parameter

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class InvoicesExport implements FromQuery
    {
        use Exportable;
    
        public function __construct(int $year)
        {
            $this->year = $year;
        }
    
        public function query()
        {
            return Invoice::query()->whereYear('created_at', $this->year);
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

The year can now be passed as dependency to the export class:

    return (new InvoicesExport(2018))->download('invoices.xlsx');
    

1  

### [#](#as-setter) As setter

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class InvoicesExport implements FromQuery
    {
        use Exportable;
    
        public function forYear(int $year)
        {
            $this->year = $year;
            
            return $this;
        }
    
        public function query()
        {
            return Invoice::query()->whereYear('created_at', $this->year);
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

We can adjust the year by using the `forYear` method:

    return (new InvoicesExport)->forYear(2018)->download('invoices.xlsx');
    

1  

### [#](#macro-s-and-mixins) Macro's and Mixins

The Eloquent Builder/Model has a macro to directly download an Eloquent query to Excel.

    User::query()->where('name', 'Patrick')->downloadExcel('query-download.xlsx');
    

1  

If you want to include header row, you can pass `true` as third parameter:

    User::query()->downloadExcel('query-download.xlsx', Excel::XLSX, true);
    

1  

Similarly, you can store the results of a query:

    User::query()->storeExcel('query-store.xlsx', 'your-disk');
    

1