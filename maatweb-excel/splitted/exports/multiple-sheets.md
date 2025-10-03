[#](#multiple-sheets) Multiple Sheets
=====================================

*   [Sheet classes](#sheet-classes)

To allow the export to have multiple sheets, the `WithMultipleSheets` concern should be used. The `sheets()` method expects an array of sheet export objects to be returned.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\Exportable;
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    
    class InvoicesExport implements WithMultipleSheets
    {
        use Exportable;
    
        protected $year;
        
        public function __construct(int $year)
        {
            $this->year = $year;
        }
    
        /**
         * @return array
         */
        public function sheets(): array
        {
            $sheets = [];
    
            for ($month = 1; $month <= 12; $month++) {
                $sheets[] = new InvoicesPerMonthSheet($this->year, $month);
            }
    
            return $sheets;
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

[#](#sheet-classes) Sheet classes
---------------------------------

The `InvoicesPerMonthSheet` can implement concerns like `FromQuery`, `FromCollection`, `FromView`, ...

_Note: The WithTitle concern is needed in order to name each sheet using the `title()` method_

    namespace App\Exports\Sheets;
    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithTitle;
    
    class InvoicesPerMonthSheet implements FromQuery, WithTitle
    {
        private $month;
        private $year;
    
        public function __construct(int $year, int $month)
        {
            $this->month = $month;
            $this->year  = $year;
        }
    
        /**
         * @return Builder
         */
        public function query()
        {
            return Invoice
                ::query()
                ->whereYear('created_at', $this->year)
                ->whereMonth('created_at', $this->month);
        }
    
        /**
         * @return string
         */
        public function title(): string
        {
            return 'Month ' . $this->month;
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

The code below can be implemented in any class in order to download an xlsx of all invoices from the current year, with 12 worksheets representing each month of the year.

    public function downloadInvoices() 
    {
        return (new InvoicesExport(2018))->download('invoices.xlsx');
    }
    

1  
2  
3  
4