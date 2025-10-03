[#](#customizing-columns) Customizing columns
=============================================

*   [Formatting columns](#formatting-columns)
    *   [Dates](#dates)
    *   [Value binders](#value-binders)
    *   [Disable intelligent formatting](#disable-intelligent-formatting)
    *   [Default Value Binder](#default-value-binder)
*   [Auto size](#auto-size)
*   [Column widths](#column-widths)
*   [Styling](#styling)
*   [Default styles](#default-styles)
*   [Workbook background color](#workbook-background-color)
*   [Full Styling Map](#full-styling-map)

[#](#formatting-columns) Formatting columns
-------------------------------------------

You can easily format an entire column, by using `WithColumnFormatting`. In case you want something more custom, it's suggested to use the `AfterSheet` event to directly interact with the underlying `Worksheet` class.

    namespace App\Exports;
    
    use PhpOffice\PhpSpreadsheet\Shared\Date;
    use PhpOffice\PhpSpreadsheet\Style\NumberFormat;
    use Maatwebsite\Excel\Concerns\WithColumnFormatting;
    use Maatwebsite\Excel\Concerns\WithMapping;
    
    class InvoicesExport implements WithColumnFormatting, WithMapping
    {
        public function map($invoice): array
        {
            return [
                $invoice->invoice_number,
                Date::dateTimeToExcel($invoice->created_at),
                $invoice->total
            ];
        }
        
        public function columnFormats(): array
        {
            return [
                'B' => NumberFormat::FORMAT_DATE_DDMMYYYY,
                'C' => NumberFormat::FORMAT_CURRENCY_EUR_INTEGER,
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

### [#](#dates) Dates

When working with dates, it's recommended to use `\PhpOffice\PhpSpreadsheet\Shared\Date::dateTimeToExcel()` in your mapping to ensure correct parsing of dates.

### [#](#value-binders) Value binders

By default Laravel Excel uses PhpSpreadsheet's default value binder to intelligently format a cell's value when reading it. You may override this behavior by implementing the `WithCustomValueBinder` concern and the `bindValue` method. Your export class may also extend `DefaultValueBinder` to return the default behavior.

    namespace App\Exports;
    
    use PhpOffice\PhpSpreadsheet\Cell\Cell;
    use Maatwebsite\Excel\Concerns\ToModel;
    use PhpOffice\PhpSpreadsheet\Cell\DataType;
    use Maatwebsite\Excel\Concerns\WithCustomValueBinder;
    use PhpOffice\PhpSpreadsheet\Cell\DefaultValueBinder;
    
    class UsersExport extends DefaultValueBinder implements WithCustomValueBinder
    {
        public function bindValue(Cell $cell, $value)
        {
            if (is_numeric($value)) {
                $cell->setValueExplicit($value, DataType::TYPE_NUMERIC);
    
                return true;
            }
    
            // else return default behavior
            return parent::bindValue($cell, $value);
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

#### [#](#available-datatypes) Available DataTypes

*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_STRING`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_FORMULA`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_NUMERIC`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_BOOL`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_NULL`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_INLINE`
*   `PhpOffice\PhpSpreadsheet\Cell\DataType::TYPE_ERROR`

### [#](#disable-intelligent-formatting) Disable intelligent formatting

If you want to disable the intelligent formatting of values, you can extend your export class with `\PhpOffice\PhpSpreadsheet\Cell\StringValueBinder`. In this case all values are passed on as strings.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithCustomValueBinder;
    
    class UsersExport extends \PhpOffice\PhpSpreadsheet\Cell\StringValueBinder implements WithCustomValueBinder
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

### [#](#default-value-binder) Default Value Binder

If you want to use one value binder for all your exports, you can configure the default value binder in the config.

In `config/excel.php`:

    'value_binder' => [
        'default' => Maatwebsite\Excel\DefaultValueBinder::class,
    ],
    

1  
2  
3  

[#](#auto-size) Auto size
-------------------------

If you want Laravel Excel to perform an automatic width calculation, you need to implement the `ShouldAutoSize` interface, like the following code.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\ShouldAutoSize;
    
    class InvoicesExport implements ShouldAutoSize
    {
        ...
    }
    

1  
2  
3  
4  
5  
6  
7  
8  

[#](#column-widths) Column widths
---------------------------------

In some cases you might want more control over the actual column width instead of relying on autosizing. You can do so with the `WithColumnWidths` concerns. It accepts an array of columns (alphabetic representation: A, B, C) and a numeric width.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithColumnWidths;
    
    class InvoicesExport implements WithColumnWidths
    {
        public function columnWidths(): array
        {
            return [
                'A' => 55,
                'B' => 45,            
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

Can be used together with `ShouldAutoSize`. Only the columns with explicit widths won't be autosized.

[#](#styling) Styling
---------------------

The `WithStyles` (available after `v3.1.21`) concerns allows styling columns, cells and rows. This might be useful when you want to make the heading row bold.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithStyles;
    use PhpOffice\PhpSpreadsheet\Worksheet\Worksheet;
    
    class InvoicesExport implements WithStyles
    {
        public function styles(Worksheet $sheet)
        {
            return [
                // Style the first row as bold text.
                1    => ['font' => ['bold' => true]],
    
                // Styling a specific cell by coordinate.
                'B2' => ['font' => ['italic' => true]],
    
                // Styling an entire column.
                'C'  => ['font' => ['size' => 16]],
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

For the contents of the styles array, please refer to the [PhpSpreadsheet docs (opens new window)](https://phpspreadsheet.readthedocs.io/en/latest/topics/recipes/#valid-array-keys-for-style-applyfromarray)

If you prefer the fluent syntax for styling cells, you can do it as follows:

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithStyles;
    use PhpOffice\PhpSpreadsheet\Worksheet\Worksheet;
    
    class InvoicesExport implements WithStyles
    {
        public function styles(Worksheet $sheet)
        {
            $sheet->getStyle('B2')->getFont()->setBold(true);
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

[#](#default-styles) Default styles
-----------------------------------

The `WithDefaultStyles` (available after `v3.1.40`) concerns allows styling the entire workbook.

    namespace App\Exports;
    
    use PhpOffice\PhpSpreadsheet\Style\Fill;
    use PhpOffice\PhpSpreadsheet\Style\Style;
    use PhpOffice\PhpSpreadsheet\Style\Color;
    use Maatwebsite\Excel\Concerns\WithDefaultStyles;
    use PhpOffice\PhpSpreadsheet\Worksheet\Worksheet;
    
    class InvoicesExport implements WithDefaultStyles
    {
        public function defaultStyles(Style $defaultStyle)
        {
            // Configure the default styles
            return $defaultStyle->getFill()->setFillType(Fill::FILL_SOLID);
        
            // Or return the styles array
            return [
                'fill' => [
                    'fillType'   => Fill::FILL_SOLID,
                    'startColor' => ['argb' => Color::RED],
                ],
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

[#](#workbook-background-color) Workbook background color
---------------------------------------------------------

The `WithBackgroundColor` (available after `v3.1.40`) concerns adds support to configure the background color of the entire workbook

    namespace App\Exports;
    
    use PhpOffice\PhpSpreadsheet\Style\Fill;
    use PhpOffice\PhpSpreadsheet\Style\Style;
    use PhpOffice\PhpSpreadsheet\Style\Color;
    use PhpOffice\PhpSpreadsheet\Worksheet\Worksheet;
    use Maatwebsite\Excel\Concerns\WithBackgroundColor;
    
    class InvoicesExport implements WithBackgroundColor
    {
        public function backgroundColor()
        {
            // Return RGB color code.
            return '000000';
        
            // Return a Color instance. The fill type will automatically be set to "solid"
            return new Color(Color::COLOR_BLUE);
        
            // Or return the styles array
            return [
                 'fillType'   => Fill::FILL_GRADIENT_LINEAR,
                 'startColor' => ['argb' => Color::COLOR_RED],
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

[#](#full-styling-map) Full Styling Map
---------------------------------------

The full styling map can be taken from the PhpSpreadsheet Styles class as follows:

    /**
     * Apply styles from array.
     */
    $spreadsheet->getActiveSheet()->getStyle('B2')->applyFromArray(
        [
            'font' => [
                'name' => 'Arial',
                'bold' => true,
                'italic' => false,
                'underline' => Font::UNDERLINE_DOUBLE,
                'strikethrough' => false,
                'color' => [
                    'rgb' => '808080'
                ]
            ],
            'borders' => [
                'bottom' => [
                    'borderStyle' => Border::BORDER_DASHDOT,
                    'color' => [
                        'rgb' => '808080'
                    ]
                ],
                'top' => [
                    'borderStyle' => Border::BORDER_DASHDOT,
                    'color' => [
                        'rgb' => '808080'
                    ]
                ]
            ],
            'alignment' => [
                'horizontal' => Alignment::HORIZONTAL_CENTER,
                'vertical' => Alignment::VERTICAL_CENTER,
                'wrapText' => true,
            ],
            'quotePrefix'    => true
        ]
    );
    

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
36  
37