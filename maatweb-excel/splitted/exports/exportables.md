[#](#exportables) Exportables
=============================

*   [Responsable](#responsable)

In the previous example, we used the `Excel::download` facade to start an export.

Laravel Excel also provides a `Maatwebsite\Excel\Concerns\Exportable` trait, to make export classes exportable.

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Concerns\FromCollection;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class InvoicesExport implements FromCollection
    {
        use Exportable;
    
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
13  
14  
15  

We can now download the export without the need for the facade:

    return (new InvoicesExport)->download('invoices.xlsx');
    

1  

You can also pass the Writer Type and optional headers to the download method:

    return (new InvoicesExport)->download('invoices.csv', Excel::CSV, ['Content-Type' => 'text/csv']);
    

1  

Or store it on a disk:

    return (new InvoicesExport)->store('invoices.xlsx', 's3');
    

1  

You can also pass options to the disk if you like:

    return (new InvoicesExport)->store('invoices.xlsx', 's3', null, 'private');
    

1  

[#](#responsable) Responsable
-----------------------------

The previous (download) example can be made even shorter when adding Laravel's `Responsable` interface to the export class:

    namespace App\Exports;
    
    use App\Invoice;
    use Maatwebsite\Excel\Excel;
    use Illuminate\Contracts\Support\Responsable;
    use Maatwebsite\Excel\Concerns\FromCollection;
    use Maatwebsite\Excel\Concerns\Exportable;
    
    class InvoicesExport implements FromCollection, Responsable
    {
        use Exportable;
        
        /**
        * It's required to define the fileName within
        * the export class when making use of Responsable.
        */
        private $fileName = 'invoices.xlsx';
        
        /**
        * Optional Writer Type
        */
        private $writerType = Excel::XLSX;
        
        /**
        * Optional headers
        */
        private $headers = [
            'Content-Type' => 'text/csv',
        ];
    
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
25  
26  
27  
28  
29  
30  
31  
32  
33  
34  
35  

You can now easily return the export class, without the need of calling `->download()`.

    return new InvoicesExport();
    

1