[#](#heading-row) Heading row
=============================

*   [Heading row on different row](#heading-row-on-different-row)
*   [Heading key formatting](#heading-key-formatting)
    *   [No formatting](#no-formatting)
    *   [Custom formatter](#custom-formatter)
*   [Importing only the heading row](#importing-only-the-heading-row)
*   [Grouping values of multiple columns sharing same header](#grouping-values-of-multiple-columns-sharing-same-header)

In case your file contains a heading row (a row in which each cells indicates the purpose of that column) and you want to use those names as array keys of each row, you can implement the `WithHeadingRow` concern.

Given we have an Excel file looking like this:

Name

Email

@ Field

Patrick Brouwers

patrick@maatwebsite.nl

Some value

We can now reference the heading instead of a numeric array key.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    
    class UsersImport implements ToModel, WithHeadingRow
    {
        public function model(array $row)
        {
            return new User([
                'name'  => $row['name'],
                'email' => $row['email'],
                'at'    => $row['at_field'],
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
16  
17  

[#](#heading-row-on-different-row) Heading row on different row
---------------------------------------------------------------

In case your heading row is not on the first row, you can easily specify this in your import class:

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    
    class UsersImport implements ToModel, WithHeadingRow
    {
        public function model(array $row)
        {
            return new User([
                'name'  => $row['name'],
                'email' => $row['email'],
            ]);
        }
        
        public function headingRow(): int
        {
            return 2;
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

The 2nd row will now be used as heading row.

[#](#heading-key-formatting) Heading key formatting
---------------------------------------------------

By default the heading keys are formatted with the Laravel `str_slug()` helper. E.g. this means all spaces are converted to `_`.

If you want to change this behaviour, you can do so by extending the `HeadingRowFormatter`

### [#](#no-formatting) No formatting

If you want no formatting at all, you can use the `none` formatter. The array keys will contain the exact data that was in the heading row.

    use Maatwebsite\Excel\Imports\HeadingRowFormatter;
    
    HeadingRowFormatter::default('none');
    
    public function model(array $row)
    {
        return new User([
            'name'  => $row['Name'],
            'email' => $row['Email'],
        ]);
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

### [#](#custom-formatter) Custom formatter

You can define a custom formatter with `::extend()` in a service provider.

    HeadingRowFormatter::extend('custom', function($value, $key) {
        return 'do-something-custom' . $value; 
        
        // And you can use heading column index.
        // return 'column-' . $key; 
    });
    

1  
2  
3  
4  
5  
6  

You can set the custom formatter in `config/excel.php`.

    'imports' => [
        'heading_row' => [
            'formatter' => 'custom',
        ],
    ],
    

1  
2  
3  
4  
5  

Or you can then set this new formatter in a service provider.

    HeadingRowFormatter::default('custom');
    

1  

[#](#importing-only-the-heading-row) Importing only the heading row
-------------------------------------------------------------------

Sometimes you might want to prefetch the heading row to do some validation. We have an easy shortcut for this: `HeadingRowImport`.

    use Maatwebsite\Excel\HeadingRowImport;
    
    class UsersImportController extends Controller 
    {
        public function import()
        {
            $headings = (new HeadingRowImport)->toArray('users.xlsx');
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

The headings array contains an array of headings per sheet.

[#](#grouping-values-of-multiple-columns-sharing-same-header) Grouping values of multiple columns sharing same header
---------------------------------------------------------------------------------------------------------------------

Given we have an Excel file looking like this:

Name

Email

Options

Options

Patrick Brouwers

patrick@maatwebsite.nl

Some value

Some other value

We can group the values of the Options columns in an array using import concern `WithGroupedHeadingRow`. Data returned from row will be in format:

    [
        'name'    => 'Patrick Brouwers',
        'email'   => 'patrick@maatwebsite.nl',
        'options' => [
            'Some value',
            'Some other value'
        ]
    ]
    

1  
2  
3  
4  
5  
6  
7  
8