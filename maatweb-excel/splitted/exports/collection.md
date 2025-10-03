[#](#exporting-collections) Exporting collections
=================================================

*   [Using custom structures](#using-custom-structures)
*   [Using arrays](#using-arrays)
*   [Dependency injection](#dependency-injection)
*   [Strict null comparisons](#strict-null-comparisons)
*   [Custom start cell](#custom-start-cell)
*   [Storing raw contents](#storing-raw-contents)
*   [Collection macros](#collection-macros)
    *   [Downloading a collection as Excel](#downloading-a-collection-as-excel)
    *   [Storing a collection on disk](#storing-a-collection-on-disk)

The easiest way to start an export is to create a custom export class. We'll use an invoices export as example.

Create a new class called `InvoicesExport` in `app/Exports`:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromCollection;
    
    class InvoicesExport implements FromCollection
    {
        public function collection()
        {
            return Invoice::all();
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

In your controller we can now download this export:

    public function export() 
    {
        return Excel::download(new InvoicesExport, 'invoices.xlsx');
    }
    

1  
2  
3  
4  

Optionally you can pass in whether or not to output headers and custom response headers:

    public function export() 
    {
        return Excel::download(new InvoicesExport, 'invoices.xlsx', true, ['X-Vapor-Base64-Encode' => 'True']);
    }
    

1  
2  
3  
4  

Or store it on a disk, (e.g. s3):

    public function storeExcel() 
    {
        return Excel::store(new InvoicesExport, 'invoices.xlsx', 's3');
    }
    

1  
2  
3  
4  

💡 More about storing exports can be found in the [storing exports on disk page](/3.1/exports/store.html).

If you want to use relationships in Collection, combine with [Mapping Data](/3.1/exports/mapping.html)

[#](#using-custom-structures) Using custom structures
-----------------------------------------------------

If you are not using Eloquent or having another datasource (e.g. an API, MongoDB, Cache, ...) you can also return a custom collection:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromCollection;
    
    class InvoicesExport implements FromCollection
    {
        public function collection()
        {
            return new Collection([
                [1, 2, 3],
                [4, 5, 6]
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

[#](#using-arrays) Using arrays
-------------------------------

If you prefer to use plain arrays over Collections, you can use the `FromArray` concern:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromArray;
    
    class InvoicesExport implements FromArray
    {
        public function array(): array
        {
            return [
                [1, 2, 3],
                [4, 5, 6]
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

If you need to pass data from the controller to your export, you can use the constructor to do so:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromArray;
    
    class InvoicesExport implements FromArray
    {
        protected $invoices;
    
        public function __construct(array $invoices)
        {
            $this->invoices = $invoices;
        }
    
        public function array(): array
        {
            return $this->invoices;
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

In your controller you can now use the constructor of the export class:

    public function export() 
    {
        $export = new InvoicesExport([
            [1, 2, 3],
            [4, 5, 6]
        ]);
    
        return Excel::download($export, 'invoices.xlsx');
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

[#](#dependency-injection) Dependency injection
-----------------------------------------------

In case your export needs dependencies, you can inject the export class:

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\FromCollection;
    
    class InvoicesExport implements FromCollection
    {
        public function __construct(InvoicesRepository $invoices)
        {
            $this->invoices = $invoices;
        }
    
        public function collection()
        {
            return $this->invoices->all();
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

    public function export(Excel $excel, InvoicesExport $export) 
    {
        return $excel->download($export, 'invoices.xlsx');
    }
    

1  
2  
3  
4  

[#](#strict-null-comparisons) Strict null comparisons
-----------------------------------------------------

If you want your `0` values to be actual `0` values in your Excel sheet instead of `null` (empty cells), you can use `WithStrictNullComparison`.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\FromCollection;
    use Maatwebsite\Excel\Concerns\WithStrictNullComparison;
    
    class InvoicesExport implements FromCollection, WithStrictNullComparison
    {
        public function __construct(InvoicesRepository $invoices)
        {
            $this->invoices = $invoices;
        }
    
        public function collection()
        {
            return $this->invoices->all();
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

[#](#custom-start-cell) Custom start cell
-----------------------------------------

The default start cell is _A1_. Implementing the `WithCustomStartCell` concern in your export class allows you to specify a custom start cell.

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromCollection;
    use Maatwebsite\Excel\Concerns\WithCustomStartCell;
    
    class InvoicesExport implements FromCollection, WithCustomStartCell
    {
        public function collection()
        {
            return Invoice::all();
        }
    
        public function startCell(): string
        {
            return 'B2';
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

`WithCustomStartCell` is only supported for `FromCollection` exports.

[#](#storing-raw-contents) Storing raw contents
-----------------------------------------------

If you want to receive the raw contents of the exported file, you can use the `raw()` method:

    $contents = Excel::raw(new InvoicesExport, \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#collection-macros) Collection macros
-----------------------------------------

The package provides some macro to Laravel's collection class to easily download or store a collection.

### [#](#downloading-a-collection-as-excel) Downloading a collection as Excel

    User::all()->downloadExcel(
        $filePath,
        $writerType = null,
        $headings = false
    )
    

1  
2  
3  
4  
5  

It doesn't have to be an Eloquent collection to work:

    (new Collection([[1, 2, 3], [1, 2, 3]]))->downloadExcel(
        $filePath,
        $writerType = null,
        $headings = false
    )
    

1  
2  
3  
4  
5  

### [#](#storing-a-collection-on-disk) Storing a collection on disk

    User::all()->storeExcel(
        $filePath,
        $disk = null,
        $writerType = null,
        $headings = false
    )
    

1  
2  
3  
4  
5  
6