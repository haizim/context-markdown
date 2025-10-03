[#](#mapping-data) Mapping data
===============================

*   [Mapping rows](#mapping-rows)
    *   [Multiple rows](#multiple-rows)
*   [Adding a heading row](#adding-a-heading-row)
*   [Prepare rows](#prepare-rows)

[#](#mapping-rows) Mapping rows
-------------------------------

By adding `WithMapping` you map the data that needs to be added as row. This way you have control over the actual source for each column. In case of using the Eloquent query builder:

    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithMapping;
    use PhpOffice\PhpSpreadsheet\Shared\Date;
    
    class InvoicesExport implements FromQuery, WithMapping
    {    
        /**
        * @param Invoice $invoice
        */
        public function map($invoice): array
        {
            return [
                $invoice->invoice_number,
                $invoice->user->name,
                Date::dateTimeToExcel($invoice->created_at),
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

### [#](#multiple-rows) Multiple rows

You can also return multiple rows inside the map function:

    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithMapping;
    use PhpOffice\PhpSpreadsheet\Shared\Date;
    
    class InvoicesExport implements FromQuery, WithMapping
    {    
        /**
        * @param Invoice $invoice
        */
        public function map($invoice): array
        {
            // This example will return 3 rows.
            // First row will have 2 column, the next 2 will have 1 column
            return [
                [
                    $invoice->invoice_number,
                    Date::dateTimeToExcel($invoice->created_at),
                ],
                [
                    $invoice->lines->first()->description,
                ],
                [
                    $invoice->lines->last()->description,
                ]
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
21  
22  
23  
24  
25  
26  
27  
28  

[#](#adding-a-heading-row) Adding a heading row
-----------------------------------------------

A heading row can easily be added by adding the `WithHeadings` concern. The heading row will be added as very first row of the sheet.

    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithHeadings;
    
    class InvoicesExport implements FromQuery, WithHeadings
    {   
        public function headings(): array
        {
            return [
                '#',
                'User',
                'Date',
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

If you need to have multiple heading rows, you can return multiple rows from the `headings()` method:

    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithHeadings;
    
    class InvoicesExport implements FromQuery, WithHeadings
    {   
        public function headings(): array
        {
            return [
               ['First row', 'First row'],
               ['Second row', 'Second row'],
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

[#](#prepare-rows) Prepare rows
-------------------------------

If you need to prepare rows before appending these rows to sheet, you can add method `prepareRows` to your export class. This method will be called before flattening the query output and calling `map()`.

    
    use Maatwebsite\Excel\Concerns\FromQuery;
    use Maatwebsite\Excel\Concerns\WithHeadings;
    
    class UsersExport implements FromQuery, WithHeadings
    {   
        public function prepareRows($rows)
        {
            return $rows->transform(function ($user) {
                $user->name .= ' (prepared)';
    
                return $user;
            });
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