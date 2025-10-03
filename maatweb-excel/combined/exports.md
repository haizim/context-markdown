## === collection.md ===

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

## === column-formatting.md ===

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

## === concerns.md ===

[#](#export-concerns) Export concerns
=====================================

Interface

Explanation

Documentation

`Maatwebsite\Excel\Concerns\FromArray`

Use an array to populate the export.

[Exporting collections](/3.1/exports/collection.html#using-arrays)

`Maatwebsite\Excel\Concerns\FromCollection`

Use a Laravel Collection to populate the export.

[Exporting collections](/3.1/exports/collection.html)

`Maatwebsite\Excel\Concerns\FromGenerator`

Use a generator to populate the export.

[From Generator](/3.1/exports/from-generator.html)

`Maatwebsite\Excel\Concerns\FromIterator`

Use an iterator to populate the export.

`Maatwebsite\Excel\Concerns\FromQuery`

Use an Eloquent query to populate the export.

[From Query](/3.1/exports/from-query.html)

`Maatwebsite\Excel\Concerns\FromView`

Use a (Blade) view to to populate the export.

[From View](/3.1/exports/from-view.html)

`Maatwebsite\Excel\Concerns\HasReferencesToOtherSheets`

Allows precalculated values where one sheet has references to another sheet.

[References to other sheets](/3.1/exports/multiple-sheets.html#making-calculations-work-when-referencing-between-sheets)

`Maatwebsite\Excel\Concerns\ShouldAutoSize`

Auto-size the columns in the worksheet.

[Auto size](/3.1/exports/column-formatting.html#auto-size)

`Maatwebsite\Excel\Concerns\WithCharts`

Allows to run one or multiple PhpSpreadsheet Chart instances.

[Charts](/3.1/exports/charts.html)

`Maatwebsite\Excel\Concerns\WithColumnFormatting`

Format certain columns.

[Formatting columns](/3.1/exports/column-formatting.html)

`Maatwebsite\Excel\Concerns\WithColumnWidths`

Set Column widths.

[Column widths](/3.1/exports/column-formatting.html#styling)

`Maatwebsite\Excel\Concerns\WithCustomChunkSize`

Allows Exportables to define their chunk size.

`Maatwebsite\Excel\Concerns\WithCustomCsvSettings`

Allows to run custom Csv settings for this specific exportable.

[Custom CSV Settings](/3.1/exports/settings.html)

`Maatwebsite\Excel\Concerns\WithCustomQuerySize`

Allows Exportables that implement the FromQuery concern to provide their own custom query size.

[Custom Query Size](/3.1/exports/queued.html#custom-query-size)

`Maatwebsite\Excel\Concerns\WithCustomStartCell`

Allows to specify a custom start cell. Do note that this is only supported for FromCollection exports.

[Custom start cell](/3.1/exports/collection.html#custom-start-cell)

`Maatwebsite\Excel\Concerns\WithCustomValueBinder`

Allows to specify a custom value binder.

[Custom Value Binder](/3.1/exports/column-formatting.html#value-binders)

`Maatwebsite\Excel\Concerns\WithDrawings`

Allows to run one or multiple PhpSpreadsheet (Base)Drawing instances.

[Drawings](/3.1/exports/drawings.html)

`Maatwebsite\Excel\Concerns\WithEvents`

Register events to hook into the PhpSpreadsheet process.

[Events](/3.1/exports/extending.html#events)

`Maatwebsite\Excel\Concerns\WithHeadings`

Prepend a heading row.

[Adding a heading row](/3.1/exports/mapping.html#adding-a-heading-row)

`Maatwebsite\Excel\Concerns\WithMapping`

Format the row before it's written to the file.

[Mapping data](/3.1/exports/mapping.html)

`Maatwebsite\Excel\Concerns\WithMultipleSheets`

Enable multi-sheet support. Each sheet can have its own concerns (except this one).

[Multiple Sheets](/3.1/exports/multiple-sheets.html)

`Maatwebsite\Excel\Concerns\WithPreCalculateFormulas`

Forces PhpSpreadsheet to recalculate all formulae in a workbook when saving, so that the pre-calculated values are immediately available to MS Excel or other office spreadsheet viewer when opening the file.

`Maatwebsite\Excel\Concerns\WithProperties`

Allows setting properties on the document.

[Properties](/3.1/exports/settings.html#properties)

`Maatwebsite\Excel\Concerns\WithStrictNullComparison`

Uses strict comparisons when testing cells for null value.

[Strict null comparisons](/3.1/exports/collection.html#strict-null-comparisons)

`Maatwebsite\Excel\Concerns\WithStyles`

Allows setting styles on worksheets.

[Styles](/3.1/exports/column-formatting.html#styling)

`Maatwebsite\Excel\Concerns\WithTitle`

Set the Workbook or Worksheet title.

[Multiple Sheets](/3.1/exports/multiple-sheets.html)

### [#](#traits) Traits

Trait

Explanation

Documentation

`Maatwebsite\Excel\Concerns\Exportable`

Add download/store abilities right on the export class itself.

[Exportables](/3.1/exports/exportables.html)

`Maatwebsite\Excel\Concerns\RegistersEventListeners`

Auto-register the available event listeners.

[Auto register event listeners](/3.1/exports/extending.html#auto-register-event-listeners)

## === drawings.md ===

[#](#drawings) Drawings
=======================

*   [Instantiating a drawing](#instantiating-a-drawing)
*   [Adding a single drawing](#adding-a-single-drawing)
*   [Adding multiple drawings](#adding-multiple-drawings)
*   [Adding a drawing of remote image](#adding-a-drawing-of-remote-image)

By using the `WithDrawings` concern, you can add one or multiple drawings to your worksheet.

[#](#instantiating-a-drawing) Instantiating a drawing
-----------------------------------------------------

You first have to instantiate a new `\PhpOffice\PhpSpreadsheet\Worksheet\Drawing`, and assign its properties a meaningful value.

    $drawing = new \PhpOffice\PhpSpreadsheet\Worksheet\Drawing();
    $drawing->setName('Logo');
    $drawing->setDescription('This is my logo');
    $drawing->setPath(public_path('/img/logo.jpg'));
    $drawing->setHeight(90);
    

1  
2  
3  
4  
5  

You can view all available properties for Drawing on the [PhpSpreadsheet docs (opens new window)](https://phpspreadsheet.readthedocs.io/en/latest/topics/recipes/#add-a-drawing-to-a-worksheet).

[#](#adding-a-single-drawing) Adding a single drawing
-----------------------------------------------------

When you've instantiated the drawing, you can add the `WithDrawings` concern to your export class. Return the Drawing instance in the `drawings` method.

    <?php
    
    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithDrawings;
    use PhpOffice\PhpSpreadsheet\Worksheet\Drawing;
    
    class InvoicesExport implements WithDrawings
    {
        public function drawings()
        {
            $drawing = new Drawing();
            $drawing->setName('Logo');
            $drawing->setDescription('This is my logo');
            $drawing->setPath(public_path('/img/logo.jpg'));
            $drawing->setHeight(90);
            $drawing->setCoordinates('B3');
    
            return $drawing;
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

[#](#adding-multiple-drawings) Adding multiple drawings
-------------------------------------------------------

You can add multiple drawings to the worksheet by returning an array in the `drawings` method.

    <?php
    
    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithDrawings;
    use PhpOffice\PhpSpreadsheet\Worksheet\Drawing;
    
    class InvoicesExport implements WithDrawings
    {
        public function drawings()
        {
            $drawing = new Drawing();
            $drawing->setName('Logo');
            $drawing->setDescription('This is my logo');
            $drawing->setPath(public_path('/img/logo.jpg'));
            $drawing->setHeight(50);
            $drawing->setCoordinates('B3');
    
            $drawing2 = new Drawing();
            $drawing2->setName('Other image');
            $drawing2->setDescription('This is a second image');
            $drawing2->setPath(public_path('/img/other.jpg'));
            $drawing2->setHeight(120);
            $drawing2->setCoordinates('G2');
    
            return [$drawing, $drawing2];
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

[#](#adding-a-drawing-of-remote-image) Adding a drawing of remote image
-----------------------------------------------------------------------

You can instantiate a new drawing from `\PhpOffice\PhpSpreadsheet\Worksheet\MemoryDrawing`, and create a string containing the binary image data, or from an external url by `imagecreatefromstring(file_get_contents($url))`, then assign it to `setImageResource`. Return the Drawing instance in the `drawings` method.

    <?php
    
    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithDrawings;
    use PhpOffice\PhpSpreadsheet\Worksheet\MemoryDrawing;
    
    class InvoicesExport implements WithDrawings
    {
        public function drawings()
        {
            if (!$imageResource = @imagecreatefromstring(file_get_contents('http://example.jpg'))) {
                throw new \Exception('The image URL cannot be converted into an image resource.');
            }
    
            $drawing = new MemoryDrawing();
            $drawing->setName('Logo');
            $drawing->setDescription('This is my logo');
            $drawing->setImageResource($imageResource);
            $drawing->setHeight(90);
            $drawing->setCoordinates('B3');
    
            return $drawing;
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

## === export-formats.md ===

[#](#export-formats) Export formats
===================================

*   [XLSX](#xlsx)
*   [CSV](#csv)
*   [TSV](#tsv)
*   [ODS](#ods)
*   [XLS](#xls)
*   [HTML](#html)
*   [MPDF](#mpdf)
*   [DOMPDF](#dompdf)
*   [TCPDF](#tcpdf)

By default, the export format is determined by the extension of the file. If you want to explicitly configure the export format, you can pass it through as 2nd parameter.

[#](#xlsx) XLSX
---------------

    return Excel::download(new InvoicesExport, 'invoices.xlsx', \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#csv) CSV
-------------

    return Excel::download(new InvoicesExport, 'invoices.csv', \Maatwebsite\Excel\Excel::CSV);
    

1  

By default the CSV is download with Content Type `text/plain`, if you want to customize the Content-Type header, you can do so by passing it as 3rd parameter.

    return Excel::download(new InvoicesExport, 'invoices.csv', \Maatwebsite\Excel\Excel::CSV, [
          'Content-Type' => 'text/csv',
    ]);
    

1  
2  
3  

Laravel CSV

You may have a look at our [Laravel CSV](/csv/1.0/getting-started/) package as well.

[#](#tsv) TSV
-------------

    return Excel::download(new InvoicesExport, 'invoices.tsv', \Maatwebsite\Excel\Excel::TSV);
    

1  

[#](#ods) ODS
-------------

    return Excel::download(new InvoicesExport, 'invoices.ods', \Maatwebsite\Excel\Excel::ODS);
    

1  

[#](#xls) XLS
-------------

    return Excel::download(new InvoicesExport, 'invoices.xls', \Maatwebsite\Excel\Excel::XLS);
    

1  

[#](#html) HTML
---------------

    return Excel::download(new InvoicesExport, 'invoices.html', \Maatwebsite\Excel\Excel::HTML);
    

1  

Exporting to PDF

If you'd like to export to PDF, you must now install a PDF rendering library yourself. Please refer to the [PhpSpreadsheet Documentation (opens new window)](https://phpspreadsheet.readthedocs.io/en/latest/topics/reading-and-writing-to-file/#pdf) for more information.

[#](#mpdf) MPDF
---------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::MPDF);
    

1  

[#](#dompdf) DOMPDF
-------------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::DOMPDF);
    

1  

[#](#tcpdf) TCPDF
-----------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::TCPDF);
    

1

## === exportables.md ===

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

## === extending.md ===

[#](#extending) Extending
=========================

*   [Events](#events)
    *   [Auto register event listeners](#auto-register-event-listeners)
    *   [Global event listeners](#global-event-listeners)
    *   [Available events](#available-events)
*   [Custom Concerns](#custom-concerns)
*   [Macroable](#macroable)
    *   [Writer](#writer)
    *   [Sheet](#sheet)
    *   [Customize](#customize)
    *   [RTL (Right to Left) Sheets](#rtl-right-to-left-sheets)

[#](#events) Events
-------------------

The export process has a few events you can leverage to interact with the underlying classes to add custom behaviour to the export.

You are able to hook into the parent package by using events. No need to use convenience methods like "query" or "view", if you need full control over the export.

The events will be activated by adding the `WithEvents` concern. Inside the `registerEvents` method, you will have to return an array of events. The key is the Fully Qualified Name (FQN) of the event and the value is a callable event listener. This can either be a closure, array-callable or invokable class.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\BeforeExport;
    use Maatwebsite\Excel\Events\BeforeWriting;
    use Maatwebsite\Excel\Events\BeforeSheet;
    
    class InvoicesExport implements WithEvents
    {
        /**
         * @return array
         */
        public function registerEvents(): array
        {
            return [
                // Handle by a closure.
                BeforeExport::class => function(BeforeExport $event) {
                    $event->writer->getProperties()->setCreator('Patrick');
                },
                
                // Array callable, refering to a static method.
                BeforeWriting::class => [self::class, 'beforeWriting'],
                
                // Using a class with an __invoke method.
                BeforeSheet::class => new BeforeSheetHandler()
            ];
        }
        
        public static function beforeWriting(BeforeWriting $event) 
        {
            //
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

Do note that using a `Closure` will not be possible in combination with queued exports, as PHP cannot serialize the closure. In those cases it might be better to use the `RegistersEventListeners` trait.

### [#](#auto-register-event-listeners) Auto register event listeners

By using the `RegistersEventListeners` trait you can auto-register the event listeners, without the need of using the `registerEvents`. The listener will only be registered if the method is created.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Concerns\RegistersEventListeners;
    use Maatwebsite\Excel\Events\BeforeExport;
    use Maatwebsite\Excel\Events\BeforeWriting;
    use Maatwebsite\Excel\Events\BeforeSheet;
    use Maatwebsite\Excel\Events\AfterSheet;
    
    class InvoicesExport implements WithEvents
    {
        use Exportable, RegistersEventListeners;
        
        public static function beforeExport(BeforeExport $event)
        {
            //
        }
    
        public static function beforeWriting(BeforeWriting $event)
        {
            //
        }
    
        public static function beforeSheet(BeforeSheet $event)
        {
            //
        }
    
        public static function afterSheet(AfterSheet $event)
        {
            //
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

### [#](#global-event-listeners) Global event listeners

Event listeners can also be configured globally, if you want to perform the same actions on all exports in your app. You can add them to e.g. your `AppServiceProvider` in the `register()` method.

    Writer::listen(BeforeExport::class, function () {
        //
    });
    
    Writer::listen(BeforeWriting::class, function () {
        //
    });
    
    Sheet::listen(BeforeSheet::class, function () {
        //
    });
    
    Sheet::listen(AfterSheet::class, function () {
        //
    });
    

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

### [#](#available-events) Available events

Event name

Payload

Explanation

`Maatwebsite\Excel\Events\BeforeExport`

`$event->writer : Writer`

Event gets raised at the start of the process.

`Maatwebsite\Excel\Events\BeforeWriting`

`$event->writer : Writer`

Event gets raised before the download/store starts.

`Maatwebsite\Excel\Events\BeforeSheet`

`$event->sheet : Sheet`

Event gets raised just after the sheet is created.

`Maatwebsite\Excel\Events\AfterSheet`

`$event->sheet : Sheet`

Event gets raised at the end of the sheet process.

[#](#custom-concerns) Custom Concerns
-------------------------------------

You can add custom concerns to your app. This can be useful if you want to share some concerns over a few projects or want to open source your custom concerns.

Let's add a `WithCustomProperties` concern to your app. You could add these concerns to `App/Exports/Concerns`, but any location will do as long as it can be autoloaded by Composer.

    namespace App\Exports\Concerns;
    
    interface WithCustomProperties
    {
        /**
         *
         * @return string
         */
        public function description(): string;
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

Next to this concern we will create a concern handler `WithCustomPropertiesHandler`. This class can also be added to `App/Exports/Concerns`, but is again completely free of choice. A concern handler is basically just an invokable class. It receives your exportable object and either a `Writer` or `Sheet` object, depending on the chosen event.

    namespace App\Exports\Concerns;
    
    use App\Exports\Concerns\WithCustomProperties;
    use Maatwebsite\Excel\Writer;
    
    class WithCustomPropertiesHandler
    {
        /**
         * @param WithCustomProperties $exportable
         * @param Writer               $writer
         */
        public function __invoke(WithCustomProperties $exportable, Writer $writer)
        {
            $writer
                ->getDelegate()
                ->getProperties()
                ->setDescription(
                    $exportable->description()
                );
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

We will then register this concern in a service provider. You could use `App/Providers/AppServiceProvider` for this.

    public function register()
    {
        Excel::extend(WithCustomProperties::class, new WithCustomPropertiesHandler);
    }
    

1  
2  
3  
4  

💡 `::extend` accepts a callable as second parameter. It's also possible to pass a closure.

    public function register()
    {
        Excel::extend(WithCustomProperties::class, function(WithCustomProperties $exportable, Writer $writer) {
            $writer->getDelegate()->getProperties()->setDescription($exportable->description());
        });
    }
    

1  
2  
3  
4  
5  
6  

You can also bind concern handlers to different hooks. By default a concern handler is always bound to the `BeforeWriting` event. You can easily customize this, by supplying a 3rd parameter.

    public function register()
    {
        Excel::extend(WithCustomProperties::class, new WithCustomPropertiesHandler, BeforeExport::class);
    }
    

1  
2  
3  
4  

[#](#macroable) Macroable
-------------------------

Both `Writer` and `Sheet` are "macroable" which means they can easily be extended to fit your needs. Both Writer and Sheet have a `->getDelegate()` method which returns the underlying PhpSpreadsheet class. This will allow you to add custom macros as shortcuts to PhpSpreadsheet methods that are not available in this package.

### [#](#writer) Writer

    use \Maatwebsite\Excel\Writer;
    
    Writer::macro('setCreator', function (Writer $writer, string $creator) {
        $writer->getDelegate()->getProperties()->setCreator($creator);
    });
    

1  
2  
3  
4  
5  

### [#](#sheet) Sheet

    use \Maatwebsite\Excel\Sheet;
    
    Sheet::macro('setOrientation', function (Sheet $sheet, $orientation) {
        $sheet->getDelegate()->getPageSetup()->setOrientation($orientation);
    });
    

1  
2  
3  
4  
5  

### [#](#customize) Customize

You can create your own macro to add custom methods to a spreadsheet instance.

For example, to add styling to a cell, we first create a macro, let's call it `styleCells`:

    use \Maatwebsite\Excel\Sheet;
    
    Sheet::macro('styleCells', function (Sheet $sheet, string $cellRange, array $style) {
        $sheet->getDelegate()->getStyle($cellRange)->applyFromArray($style);
    });
    

1  
2  
3  
4  
5  

Once the macro is created, it can be used inside the `registerEvents()` method as such:

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\BeforeExport;
    use Maatwebsite\Excel\Events\AfterSheet;
    
    class InvoicesExport implements WithEvents
    {
        /**
         * @return array
         */
        public function registerEvents(): array
        {
            return [
                BeforeExport::class  => function(BeforeExport $event) {
                    $event->writer->setCreator('Patrick');
                },
                AfterSheet::class    => function(AfterSheet $event) {
                    $event->sheet->setOrientation(\PhpOffice\PhpSpreadsheet\Worksheet\PageSetup::ORIENTATION_LANDSCAPE);
    
                    $event->sheet->styleCells(
                        'B2:G8',
                        [
                            'borders' => [
                                'outline' => [
                                    'borderStyle' => \PhpOffice\PhpSpreadsheet\Style\Border::BORDER_THICK,
                                    'color' => ['argb' => 'FFFF0000'],
                                ],
                            ]
                        ]
                    );
                },
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
29  
30  
31  
32  
33  
34  
35  

### [#](#rtl-right-to-left-sheets) RTL (Right to Left) Sheets

To change the Excel sheet direction you can use `setRightToLeft(true)` as in the below example

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\BeforeExport;
    use Maatwebsite\Excel\Events\AfterSheet;
    
    class InvoicesExport implements WithEvents
    {
        /**
         * @return array
         */
        public function registerEvents(): array
        {
            return [
                AfterSheet::class    => function(AfterSheet $event) {
                    $event->sheet->getDelegate()->setRightToLeft(true);
                },
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

Feel free to use the above macro, or be creative and invent your own!

For PhpSpreadsheet methods, please refer to [their documentation (opens new window)](https://phpspreadsheet.readthedocs.io/).

## === from-generator.md ===

[#](#from-generator) From Generator
===================================

Exports can be created from a PHP [generator (opens new window)](https://www.php.net/manual/en/class.generator.php) class, by using the `FromGenerator` concern.

A generator allows you to write code that uses foreach to iterate over a set of data without needing to build an array in memory.

    namespace App\Exports;
    
    use Generator;
    use Maatwebsite\Excel\Concerns\Exportable;
    use Maatwebsite\Excel\Concerns\FromGenerator;
    
    class DataExport implements FromGenerator
    {
        use Exportable;
    
        public function generator(): Generator
        {
            for ($i = 1; $i <= 100; $i++) {
                yield [$i, $i+1, $i+2];
            }
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

You can download the export in your controller:

    public function export() 
    {
        return (new DataExport)->download('data.xlsx');
    }
    

1  
2  
3  
4

## === from-query.md ===

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

## === from-view.md ===

[#](#from-view) From View
=========================

Exports can be created from a Blade view, by using the `FromView` concern.

    namespace App\Exports;
    
    use App\Invoice;
    use Illuminate\Contracts\View\View;
    use Maatwebsite\Excel\Concerns\FromView;
    
    class InvoicesExport implements FromView
    {
        public function view(): View
        {
            return view('exports.invoices', [
                'invoices' => Invoice::all()
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

It will convert an HTML table into an Excel spreadsheet. For example; `invoices.blade.php`:

    <table>
        <thead>
        <tr>
            <th>Name</th>
            <th>Email</th>
        </tr>
        </thead>
        <tbody>
        @foreach($invoices as $invoice)
            <tr>
                <td>{{ $invoice->name }}</td>
                <td>{{ $invoice->email }}</td>
            </tr>
        @endforeach
        </tbody>
    </table>
    

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

Attribute in tag html support:

Attributes

Description

bgcolor

set background color to cell `<td>`

colspan

merge column cell

rowspan

merge row cell

width

set width to cell

height

set height to cell

data-format

set format `PhpOffice\PhpSpreadsheet\Style::NumberFormat`

data-type

set type `PhpOffice\PhpSpreadsheet\Cell`

align

set text align to cell

valign

set vertical align to cell

style

set style to cell

Style inline support

*   background
*   background-color
*   color
*   border|border-top|border-bottom|border-left|border-right
*   font-size|font-weight|font-sytle|font-family
*   text-decoration: underline|line-through
*   text-align
*   vertical-align
*   with|height
*   word-wrap
*   text-indent

You can download the export in your controller:

    public function export() 
    {
        return Excel::download(new InvoicesExport, 'invoices.xlsx');
    }
    

1  
2  
3  
4

## === index.md ===

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

## === mapping.md ===

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

## === multiple-sheets.md ===

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

## === queued.md ===

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

## === settings.md ===

[#](#settings) Settings
=======================

*   [Properties](#properties)
*   [Custom CSV Settings](#custom-csv-settings)
    *   [Available csv settings](#available-csv-settings)
*   [Cell caching](#cell-caching)

[#](#properties) Properties
---------------------------

By default the Worksheet properties get configured in `config/excel.php`. You can configure a default title, description, creator, etc.

If you want to overrule on a per export basis, you can use the `WithProperties` concern.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithProperties;
    
    class InvoicesExport implements WithProperties
    {    
        public function properties(): array
        {
            return [
                'creator'        => 'Patrick Brouwers',
                'lastModifiedBy' => 'Patrick Brouwers',
                'title'          => 'Invoices Export',
                'description'    => 'Latest Invoices',
                'subject'        => 'Invoices',
                'keywords'       => 'invoices,export,spreadsheet',
                'category'       => 'Invoices',
                'manager'        => 'Patrick Brouwers',
                'company'        => 'Maatwebsite',
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

It's not required to return all properties, you can ommit the keys you don't want to overrule.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithProperties;
    
    class InvoicesExport implements WithProperties
    {    
        public function properties(): array
        {
            return [
                'creator'        => 'Patrick Brouwers',
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

[#](#custom-csv-settings) Custom CSV Settings
---------------------------------------------

By default Laravel Excel uses the defaults from the config (`config/excel.php`). You can change this by adding the `WithCustomCsvSettings` interface.

    namespace App\Exports;
    
    use Maatwebsite\Excel\Concerns\WithCustomCsvSettings;
    
    class InvoicesExport implements WithCustomCsvSettings
    {    
        public function getCsvSettings(): array
        {
            return [
                'delimiter' => ';',
                'use_bom' => false,
                'output_encoding' => 'ISO-8859-1',
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

### [#](#available-csv-settings) Available csv settings

*   `delimiter`
*   `enclosure`
*   `line_ending`
*   `use_bom`
*   `include_separator_line`
*   `excel_compatibility`
*   `output_encoding`

[#](#cell-caching) Cell caching
-------------------------------

By default PhpSpreadsheet keeps all cell values in memory, however when dealing with large files, this might result into memory issues. If you want to mitigate that, you can configure a cell caching driver here.

When using the illuminate driver, it will store each value in the cache store. This can slow down the process, because it needs to store each value. However it will use less memory. It will automatically use your default cache store. However if you prefer to have the cell cache on a separate store, you can configure the store name here. You can use any store defined in your cache config. When leaving at "null" it will use the default store.

You can use the "batch" store if you want to only persist to the store when the memory limit is reached. You can tweak the memory limit in the config.

## === store.md ===

[#](#storing-exports-on-disk) Storing exports on disk
=====================================================

*   [Default disk](#default-disk)
*   [Custom disks](#custom-disks)
*   [Disk options](#disk-options)
*   [Note about queuing](#note-about-queuing)

Exports can easily be stored on any [filesystem (opens new window)](https://laravel.com/docs/master/filesystem) that Laravel supports.

[#](#default-disk) Default disk
-------------------------------

    public function storeExcel() 
    {
        // Store on default disk
        Excel::store(new InvoicesExport(2018), 'invoices.xlsx');
    }
    

1  
2  
3  
4  
5  

[#](#custom-disks) Custom disks
-------------------------------

    public function storeExcel() 
    {
        // Store on a different disk (e.g. s3)
        Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3');
        
        // Store on a different disk with a defined writer type. 
        Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3', Excel::XLSX);
    }
    

1  
2  
3  
4  
5  
6  
7  
8  

[#](#disk-options) Disk options
-------------------------------

If you want to pass some options to the disk, pass them to Excel::store() as the fifth parameter.

    public function storeExcel() 
    {
        Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3', null, [
            'visibility' => 'private',
        ]);
    }
    

1  
2  
3  
4  
5  
6  

Laravel has a shortcut for private files:

    public function storeExcel() 
    {
        Excel::store(new InvoicesExport(2018), 'invoices.xlsx', 's3', null, 'private');
    }
    

1  
2  
3  
4  

File names cannot include certain characters:

*   `<` (less than)
*   `>` (greater than)
*   `:` (colon)
*   `"` (double quote)
*   `/` (forward slash)
*   `\` (backslash)
*   `|` (vertical bar or pipe)
*   `?` (question mark)
*   `*` (asterisk)

[#](#note-about-queuing) Note about queuing
-------------------------------------------

If you are storing the export using `Excel::queue()` or using the `ShouldQueue` interface, make sure to have a look at the [queuing docs (opens new window)](https://docs.laravel-excel.com/3.1/exports/queued.html)

## === testing.md ===

[#](#testing) Testing
=====================

*   [Testing downloads](#testing-downloads)
*   [Testing storing exports](#testing-storing-exports)
*   [Testing queuing exports](#testing-queuing-exports)
*   [Testing exports with dynamic file name/path](#testing-exports-with-dynamic-file-name-path)

The Excel facade can be used to swap the exporter to a fake.

[#](#testing-downloads) Testing downloads
-----------------------------------------

    /**
    * @test
    */
    public function user_can_download_invoices_export() 
    {
        Excel::fake();
    
        $this->actingAs($this->givenUser())
             ->get('/invoices/download/xlsx');
    
        Excel::assertDownloaded('filename.xlsx', function(InvoicesExport $export) {
            // Assert that the correct export is downloaded.
            return $export->collection()->contains('#2018-01');
        });
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

[#](#testing-storing-exports) Testing storing exports
-----------------------------------------------------

    /**
    * @test
    */
    public function user_can_store_invoices_export() 
    {
        Excel::fake();
    
        $this->actingAs($this->givenUser())
             ->get('/invoices/store/xlsx');
    
        Excel::assertStored('filename.xlsx', 'diskName');
        
        Excel::assertStored('filename.xlsx', 'diskName', function(InvoicesExport $export) {
            return true;
        });
        
        // When passing the callback as 2nd param, the disk will be the default disk.
        Excel::assertStored('filename.xlsx', function(InvoicesExport $export) {
            return true;
        });
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

[#](#testing-queuing-exports) Testing queuing exports
-----------------------------------------------------

    /**
    * @test
    */
    public function user_can_queue_invoices_export() 
    {
        Excel::fake();
    
        $this->actingAs($this->givenUser())
             ->get('/invoices/queue/xlsx');
    
        Excel::assertQueued('filename.xlsx', 'diskName');
        
        Excel::assertQueued('filename.xlsx', 'diskName', function(InvoicesExport $export) {
            return true;
        });
        
        // When passing the callback as 2nd param, the disk will be the default disk.
        Excel::assertQueued('filename.xlsx', function(InvoicesExport $export) {
            return true;
        });
        
        // Assert that the export was queued with a specific chain of other jobs.
        Excel::assertQueuedWithChain([
            new NotifyUsers(),
        ])
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

[#](#testing-exports-with-dynamic-file-name-path) Testing exports with dynamic file name/path
---------------------------------------------------------------------------------------------

If you have dynamic naming for files or paths, you can use a regular expression to represent those while testing:

    /**
    * @test
    */
    public function user_can_store_invoices_export() 
    {
       Excel::fake();
       
       $this->actingAs($this->givenUser())
            ->get('/invoices/store/xlsx');
       
       // Tells the mock to use regular expressions
       Excel::matchByRegex(); 
       // For a given dynamic named file 'invoices_2019.xlsx'
       Excel::assertStored('/invoices_\d{4}\.xlsx/', 'diskName');
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

Please note that your expression must match only one file/path. If more than one match is found, the test will fail.