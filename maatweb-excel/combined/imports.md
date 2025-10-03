## === basics.md ===

[#](#importing-basics) Importing basics
---------------------------------------

*   [Importing basics](#importing-basics)
*   [Importing from default disk](#importing-from-default-disk)
    *   [Importing from another disk](#importing-from-another-disk)
*   [Importing uploaded files](#importing-uploaded-files)
    *   [Importing full path](#importing-full-path)
*   [Importing to array or collection](#importing-to-array-or-collection)
*   [Specifying a reader type](#specifying-a-reader-type)

If you have followed the 5 minute quick start, you'll already have a `UsersImport` class.

    <?php
    
    namespace App\Imports;
    
    use App\Models\User;
    use Illuminate\Support\Facades\Hash;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        /**
         * @param array $row
         *
         * @return User|null
         */
        public function model(array $row)
        {
            return new User([
               'name'     => $row[0],
               'email'    => $row[1],
               'password' => Hash::make($row[2]),
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
18  
19  
20  
21  
22  
23  
24  

[#](#importing-from-default-disk) Importing from default disk
-------------------------------------------------------------

Passing the UsersImport object to the `Excel::import()` method will tell the package how to import the file that is passed as second parameter. The file is expected to be located in your default filesystem disk (see `config/filesystems.php`).

    Excel::import(new UsersImport, 'users.xlsx');
    

1  

### [#](#importing-from-another-disk) Importing from another disk

You can specify another disk with the third parameter like your Amazon s3 disk. (see `config/filesystems.php`)

    Excel::import(new UsersImport, 'users.xlsx', 's3');
    

1  

[#](#importing-uploaded-files) Importing uploaded files
-------------------------------------------------------

If you let your user upload the document, you can also just pass the uploaded file directly.

    Excel::import(new UsersImport, request()->file('your_file'));
    

1  

### [#](#importing-full-path) Importing full path

If you want to specifiy the path where your file is, without having to move it to a disk, you can directly pass that file path to the import method.

    Excel::import(new UsersImport, storage_path('users.xlsx'));
    

1  

[#](#importing-to-array-or-collection) Importing to array or collection
-----------------------------------------------------------------------

If you want to bypass the `ToArray` or `ToCollection` concerns and want to have an array of imported data in your controller (beware of performance!), you can use the `::toArray()` or `::toCollection()` method.

    $array = Excel::toArray(new UsersImport, 'users.xlsx');
    
    $collection = Excel::toCollection(new UsersImport, 'users.xlsx');
    

1  
2  
3  

[#](#specifying-a-reader-type) Specifying a reader type
-------------------------------------------------------

If the reader type is not detectable by the file extension, you can specify a reader type by passing it as fourth parameter.

    Excel::import(new UsersImport, 'users.xlsx', 's3', \Maatwebsite\Excel\Excel::XLSX);
    

1

## === batch-inserts.md ===

[#](#batch-inserts) Batch inserts
=================================

*   [Batch upserts](#batch-upserts)
*   [Skipping duplicate rows](#skipping-duplicate-rows)

Importing a large file to Eloquent models, might quickly become a bottleneck as every row results into an insert query.

With the `WithBatchInserts` concern you can limit the amount of queries done by specifying a batch size. This batch size will determine how many models will be inserted into the database in one time. This will drastically reduce the import duration.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithBatchInserts;
    
    class UsersImport implements ToModel, WithBatchInserts
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function batchSize(): int
        {
            return 1000;
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

ToModel

This concern **only** works with the `ToModel` concern.

Batch Size

A batch size of `1000` will not be the most optimal situation for your import. Play around with this number to find the sweet spot.

[#](#batch-upserts) Batch upserts
---------------------------------

For batch upserts, you can additionally implement the `WithUpserts` concern.

    class UsersImport implements ToModel, WithBatchInserts, WithUpserts
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function batchSize(): int
        {
            return 1000;
        }
    
        public function uniqueBy()
        {
            return 'email';
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

In the example above, if a user already exists with the same email, the row will be updated instead. Behind the scenes, this feature uses the Laravel `upsert` method and the `uniqueBy` method is used for the second argument of the `upsert` method, which lists the column(s) that uniquely identify records within the associated table.

All databases except SQL Server require the `uniqueBy` columns to have a "primary" or "unique" index.

[#](#skipping-duplicate-rows) Skipping duplicate rows
-----------------------------------------------------

For skipping duplicate models, you can additionally implement the `WithSkipDuplicates` concern.

    class UsersImport implements ToModel, WithBatchInserts, WithSkipDuplicates
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function batchSize(): int
        {
            return 1000;
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

In the example above, if a user already exists with the same primary or unique key, the row will be ignored. Behind the scenes, this feature uses the Laravel `insertOrIgnore` method to insert records while ignoring duplicates, preventing any errors that would normally occur due to duplicate entries.

## === chunk-reading.md ===

[#](#chunk-reading) Chunk reading
=================================

*   [Using it together with Batch Inserts](#using-it-together-with-batch-inserts)
*   [Keep Track of the Row number](#keep-track-of-the-row-number)

Importing a large file can have a huge impact on the memory usage, as the library will try to load the entire sheet into memory.

To mitigate this increase in memory usage, you can use the `WithChunkReading` concern. This will read the spreadsheet in chunks and keep the memory usage under control.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithChunkReading
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function chunkSize(): int
        {
            return 1000;
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

A chunk size of `1000` will not be the most optimal situation for your import. Play around with this number to find the sweet spot.

[#](#using-it-together-with-batch-inserts) Using it together with Batch Inserts
-------------------------------------------------------------------------------

The most ideal situation (regarding time and memory consumption) you will find when combining batch inserts and chunk reading.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithBatchInserts;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithBatchInserts, WithChunkReading
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function batchSize(): int
        {
            return 1000;
        }
        
        public function chunkSize(): int
        {
            return 1000;
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

[#](#keep-track-of-the-row-number) Keep Track of the Row number
---------------------------------------------------------------

If you need the row number you can use the `RemembersRowNumber` Trait.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\RemembersRowNumber;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithChunkReading
    {
        use RemembersRowNumber;
    
        public function model(array $row)
        {
            $currentRowNumber = $this->getRowNumber();
    
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function chunkSize(): int
        {
            return 1000;
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

Remembering row numbers is only intended for ToModel imports.

If you only need the information about the offset of the chunk you can use the `RemembersChunkOffset` Trait.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\RemembersChunkOffset;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithChunkReading
    {
        use RemembersChunkOffset;
    
        public function model(array $row)
        {
            $chunkOffset = $this->getChunkOffset();
    
            return new User([
                'name' => $row[0],
            ]);
        }
        
        public function chunkSize(): int
        {
            return 1000;
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

## === collection.md ===

[#](#importing-to-collections) Importing to collections
=======================================================

The easiest way to start an import is to create a custom import class. We'll use a user import as example.

Create a new class called `UsersImport` in `app/Imports`:

    namespace App\Imports;
    
    use App\User;
    use Illuminate\Support\Collection;
    use Maatwebsite\Excel\Concerns\ToCollection;
    
    class UsersImport implements ToCollection
    {
        public function collection(Collection $rows)
        {
            foreach ($rows as $row) 
            {
                User::create([
                    'name' => $row[0],
                ]);
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
18  

The collection method will receive a collection of rows. A row is an array filled with the cell values.

In case of the file having multiple sheets, the `collection()` method will be called multiple times.

In your controller we can now import this:

    public function import() 
    {
        Excel::import(new UsersImport, 'users.xlsx');
    }
    

1  
2  
3  
4  

Whatever you return in the `collection()` method will **not** be returned to the controller.

## === concerns.md ===

[#](#import-concerns) Import concerns
=====================================

Interface

Explanation

Documentation

`Maatwebsite\Excel\Concerns\ToCollection`

Import to a collection.

[Importing to collections](/3.1/imports/collection.html)

`Maatwebsite\Excel\Concerns\ToArray`

Import to an array.

`Maatwebsite\Excel\Concerns\ToModel`

Import each row to a model.

[Importing to models](/3.1/imports/model.html)

`Maatwebsite\Excel\Concerns\OnEachRow`

Handle each row manually.

`Maatwebsite\Excel\Concerns\WithBatchInserts`

Insert models in batches.

[Batch inserts](/3.1/imports/batch-inserts.html)

`Maatwebsite\Excel\Concerns\WithChunkReading`

Read the sheet in chunks.

[Chunk reading](/3.1/imports/chunk-reading.html)

`Maatwebsite\Excel\Concerns\WithHeadingRow`

Define a row as heading row.

[Heading row](/3.1/imports/heading-row.html)

`Maatwebsite\Excel\Concerns\WithGroupedHeadingRow`

Allows columns sharing the same header key to group values in array

[Heading row](/3.1/imports/heading-row.html#grouping-values-of-multiple-columns-sharing-same-header)

`Maatwebsite\Excel\Concerns\WithLimit`

Define a limit of the amount of rows that need to be imported.

`Maatwebsite\Excel\Concerns\WithCustomValueBinder`

Define a custom value binder.

[Custom Formatting Values](/3.1/imports/custom-formatting-values.html)

`Maatwebsite\Excel\Concerns\WithMappedCells`

Define a custom cell mapping.

[Mapped Cells](/3.1/imports/mapped-cells.html)

`Maatwebsite\Excel\Concerns\WithMapping`

Map the row before being called in ToModel/ToCollection.

`Maatwebsite\Excel\Concerns\WithMultipleSheets`

Enable multi-sheet support. Each sheet can have its own concerns (except this one).

[Multiple Sheets](/3.1/imports/multiple-sheets.html)

`Maatwebsite\Excel\Concerns\WithCalculatedFormulas`

Calculates the formulas when importing. By default this is disabled.

`Maatwebsite\Excel\Concerns\WithEvents`

Register events to hook into the PhpSpreadsheet process.

[Events](/3.1/imports/extending.html#events)

`Maatwebsite\Excel\Concerns\WithCustomCsvSettings`

Allows to run custom Csv settings for this specific importable.

[Custom CSV Settings](/3.1/imports/custom-csv-settings.html)

`Maatwebsite\Excel\Concerns\WithStartRow`

Define a custom start row.

`Maatwebsite\Excel\Concerns\WithProgressBar`

Shows a progress bar when uploading via the console.

[Progress Bar](/3.1/imports/progress-bar.html)

`Maatwebsite\Excel\Concerns\WithUpserts`

Allows to upsert models.

[Upserting models](/3.1/imports/model.html#upserting-models)

`Maatwebsite\Excel\Concerns\WithUpsertColumns`

Allows upsert columns definition.

[Upserting with specific columns](/3.1/imports/model.html#upserting-with-specific-columns)

`Maatwebsite\Excel\Concerns\WithValidation`

Validates each row against a set of rules.

[Row Validation](/3.1/imports/validation.html)

`Maatwebsite\Excel\Concerns\SkipsEmptyRows`

Skips empty rows.

[Row Validation](/3.1/imports/validation.html#skipping-empty-rows)

`Maatwebsite\Excel\Concerns\SkipsOnFailure`

Skips on validation errors.

[Row Validation](/3.1/imports/validation.html#skipping-failures)

`Maatwebsite\Excel\Concerns\SkipsOnError`

Skips on database exceptions.

[Row Validation](/3.1/imports/validation.html#skipping-errors)

`Maatwebsite\Excel\Concerns\WithColumnLimit`

Allows setting an end column

`Maatwebsite\Excel\Concerns\WithReadFilter`

Allows defining a custom read filter

### [#](#traits) Traits

Trait

Explanation

Documentation

`Maatwebsite\Excel\Concerns\Importable`

Add import/queue abilities right on the import class itself.

[Importables](/3.1/imports/importables.html)

`Maatwebsite\Excel\Concerns\RegistersEventListeners`

Auto-register the available event listeners.

[Auto register event listeners](/3.1/imports/extending.html#auto-register-event-listeners)

## === custom-csv-settings.md ===

[#](#custom-csv-settings) Custom CSV Settings
=============================================

*   [Available settings](#available-settings)

By default Laravel Excel uses the defaults from the config (`config/excel.php`). You can change this by adding the `WithCustomCsvSettings` interface.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithCustomCsvSettings;
    
    class UsersImport implements ToModel, WithCustomCsvSettings
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row['0'],
                'email' => $row['1']
            ]);
        }
        
        public function getCsvSettings(): array
        {
            return [
                'input_encoding' => 'ISO-8859-1'
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

A CSV file stores data in rows and the values in each row is separated with a separator, also known as a delimiter. Although the file is defined as Comma Separated Values, the delimiter could be anything. Delimiter requires a single character. For Tab use `"\t"`. The most common delimiters are: a comma `,`, a semicolon `;`, a tab `\t`, a space , or a pipe `|`.

    public function getCsvSettings(): array
    {
        return [
            'delimiter' => "\t"
        ];
    }
    

1  
2  
3  
4  
5  
6  

[#](#available-settings) Available settings
-------------------------------------------

*   `delimiter`
*   `enclosure`
*   `escape_character`
*   `contiguous`
*   `input_encoding`

## === extending.md ===

[#](#extending) Extending
=========================

*   [Events](#events)
    *   [Auto register event listeners](#auto-register-event-listeners)
    *   [Global event listeners](#global-event-listeners)
    *   [Available events](#available-events)
*   [Macroable](#macroable)
    *   [Reader](#reader)
    *   [Sheet](#sheet)

[#](#events) Events
-------------------

The import process has a few events you can leverage to interact with the underlying classes to add custom behaviour to the import.

You are able to hook into the parent package by using events.

The events will be activated by adding the `WithEvents` concern. Inside the `registerEvents` method, you will have to return an array of events. The key is the Fully Qualified Name (FQN) of the event and the value is a callable event listener. This can either be a closure, array-callable or invokable class.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\BeforeImport;
    use Maatwebsite\Excel\Events\AfterImport;
    use Maatwebsite\Excel\Events\AfterSheet;
    use Maatwebsite\Excel\Events\BeforeSheet;
    
    
    class UsersImport implements WithEvents
    {
        /**
         * @return array
         */
        public function registerEvents(): array
        {
            return [
                // Handle by a closure.
                BeforeImport::class => function(BeforeImport $event) {
                    $creator = $event->reader->getProperties()->getCreator();
                },
    			
    		   
                // Using a class with an __invoke method.
                BeforeSheet::class => new BeforeSheetHandler(),
                
                // Array callable, refering to a static method.
                AfterSheet::class => [self::class, 'afterSheet'],
                            
            ];
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
34  
35  
36  
37  
38  

Do note that using a `Closure` will not be possible in combination with queued imports, as PHP cannot serialize the closure. In those cases it might be better to use the `RegistersEventListeners` trait.

### [#](#auto-register-event-listeners) Auto register event listeners

By using the `RegistersEventListeners` trait you can auto-register the event listeners, without the need of using the `registerEvents`. The listener will only be registered if the method is created.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Concerns\RegistersEventListeners;
    use Maatwebsite\Excel\Events\BeforeImport;
    use Maatwebsite\Excel\Events\AfterImport;
    use Maatwebsite\Excel\Events\BeforeSheet;
    use Maatwebsite\Excel\Events\AfterSheet;
    
    class UsersImport implements WithEvents
    {
        use Importable, RegistersEventListeners;
        
        public static function beforeImport(BeforeImport $event)
        {
            //
        }
    	
        public static function afterImport(AfterImport $event)
        {
            //
        }
    
        public static function beforeSheet(BeforeSheet $event)
        {
            //
        }
    
        // From 3.1.50 onwards the methods do not need to be static, allowing use of $this
        public function afterSheet(AfterSheet $event)
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
34  
35  
36  

### [#](#global-event-listeners) Global event listeners

Event listeners can also be configured globally, if you want to perform the same actions on all exports in your app. You can add them to e.g. your `AppServiceProvider` in the `register()` method.

    Reader::listen(BeforeImport::class, function () {
        //
    });
    
    Sheet::listen(AfterImport::class, function () {
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
16  
17  

### [#](#available-events) Available events

Event name

Payload

Explanation

`Maatwebsite\Excel\Events\BeforeImport`

`$event->reader : Reader`

Event gets raised at the start of the process.

`Maatwebsite\Excel\Events\AfterImport`

`$event->reader : Reader`

Event gets raised at the end of the process.

`Maatwebsite\Excel\Events\BeforeSheet`

`$event->sheet : Sheet`

Event gets raised just after the sheet is created.

`Maatwebsite\Excel\Events\AfterSheet`

`$event->sheet : Sheet`

Event gets raised at the end of the sheet process.

`Maatwebsite\Excel\Events\AfterChunk`

`$event->sheet : Sheet`

Event gets raised after each chunk from the import file has been processed. Only available with [chunk reading (opens new window)](https://docs.laravel-excel.com/3.1/imports/chunk-reading.html)

`Maatwebsite\Excel\Events\AfterBatch`

`$event->manager : ModelManager`

Event gets raised after each batch of model has been flushed to the database. Only available with [batch inserts (opens new window)](https://docs.laravel-excel.com/3.1/imports/batch-inserts.html)

[#](#macroable) Macroable
-------------------------

Both `Reader` and `Sheet` are "macroable" (which means they can easily be extended to fit your needs). Both Reader and Sheet have a `->getDelegate()` method which returns the underlying PhpSpreadsheet class. This will allow you to add custom macros as shortcuts to PhpSpreadsheet methods that are not available in this package.

### [#](#reader) Reader

    use \Maatwebsite\Excel\Reader;
    
    Reader::macro('setCreator', function (Reader $reader, string $creator) {
        $reader->getDelegate()->getProperties()->setCreator($creator);
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

For PhpSpreadsheet methods, please refer to [their documentation (opens new window)](https://phpspreadsheet.readthedocs.io/).

## === heading-row.md ===

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

## === import-formats.md ===

[#](#import-formats) Import formats
===================================

*   [XLSX](#xlsx)
*   [CSV](#csv)
*   [TSV](#tsv)
*   [ODS](#ods)
*   [XLS](#xls)
*   [SLK](#slk)
*   [XML](#xml)
*   [GNUMERIC](#gnumeric)
*   [HTML](#html)

By default, the import format is determined by the extension of the file. If you want to explicitly configure the import format, you can pass it through as 3rd parameter.

[#](#xlsx) XLSX
---------------

    (new UsersImport)->import('users.xlsx', null, \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#csv) CSV
-------------

    (new UsersImport)->import('users.csv', null, \Maatwebsite\Excel\Excel::CSV);
    

1  

[#](#tsv) TSV
-------------

    (new UsersImport)->import('users.tsv', null, \Maatwebsite\Excel\Excel::TSV);
    

1  

[#](#ods) ODS
-------------

    (new UsersImport)->import('users.ods', null, \Maatwebsite\Excel\Excel::ODS);
    

1  

[#](#xls) XLS
-------------

    (new UsersImport)->import('users.xls', null, \Maatwebsite\Excel\Excel::XLS);
    

1  

[#](#slk) SLK
-------------

    (new UsersImport)->import('users.slk', null, \Maatwebsite\Excel\Excel::SLK);
    

1  

[#](#xml) XML
-------------

    (new UsersImport)->import('users.xml', null, \Maatwebsite\Excel\Excel::XML);
    

1  

[#](#gnumeric) GNUMERIC
-----------------------

    (new UsersImport)->import('users.gnumeric', null, \Maatwebsite\Excel\Excel::GNUMERIC);
    

1  

[#](#html) HTML
---------------

    (new UsersImport)->import('users.html', null, \Maatwebsite\Excel\Excel::HTML);
    

1

## === importables.md ===

[#](#importables) Importables
=============================

*   [Importing](#importing)
*   [Queuing](#queuing)
*   [To array](#to-array)
*   [To collection](#to-collection)

In the previous example, we used the `Excel::import` facade to start an import.

Laravel Excel also provides a `Maatwebsite\Excel\Concerns\Importable` trait, to make import classes importable.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    
    class UsersImport implements ToModel
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
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

[#](#importing) Importing
-------------------------

We can now import without the need for the facade:

    (new UsersImport)->import('users.xlsx', 'local', \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#queuing) Queuing
---------------------

Or queue the import:

    (new UsersImport)->queue('users.xlsx');
    

1  

[#](#to-array) To array
-----------------------

The import can be loaded into an array :

    $array = (new UsersImport)->toArray('users.xlsx');
    

1  

[#](#to-collection) To collection
---------------------------------

The import can be loaded into a collection:

    $collection = (new UsersImport)->toCollection('users.xlsx');
    

1

## === index.md ===

[#](#_5-minute-quick-start) 🚀 5 minute quick start
---------------------------------------------------

💪 Create an import class in `app/Imports`

You may do this by using the `make:import` command.

    php artisan make:import UsersImport --model=User
    

1  

The file can be found in `app/Imports`:

    .
    ├── app
    │   ├── Imports
    │   │   ├── UsersImport.php
    │ 
    └── composer.json
    

If you prefer to create the import manually, you can create the following in `app/Imports`:

    <?php
    
    namespace App\Imports;
    
    use App\Models\User;
    use Illuminate\Support\Facades\Hash;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        /**
         * @param array $row
         *
         * @return User|null
         */
        public function model(array $row)
        {
            return new User([
               'name'     => $row[0],
               'email'    => $row[1], 
               'password' => Hash::make($row[2]),
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
18  
19  
20  
21  
22  
23  
24  

🔥 In your controller you can call this import now:

    
    use App\Imports\UsersImport;
    use Maatwebsite\Excel\Facades\Excel;
    use App\Http\Controllers\Controller;
    
    class UsersController extends Controller 
    {
        public function import() 
        {
            Excel::import(new UsersImport, 'users.xlsx');
            
            return redirect('/')->with('success', 'All good!');
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

📄 Find the imported users in your database!

## === mapped-cells.md ===

[#](#mapped-cells) Mapped Cells
===============================

In case you have a more custom spreadsheet and only want to access specific **cells**, you can implement the `WithMappedCells` concern.

You might have a speadsheet looking like this:

name

Patrick Brouwers

email

patrick@maatwebsite.nl

We can now map `name` to `B1` and `email` to `B2`. The value of those coordinates will then be available under the given array key.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithMappedCells;
    
    class UsersImport implements WithMappedCells, ToModel 
    {
        public function mapping(): array
        {
            return [
                'name'  => 'B1',
                'email' => 'B2',
            ];
        }
        
        public function model(array $row)
        {
            return new User([
                'name' => $row['name'],
                'email' => $row['email'],
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
18  
19  
20  
21  
22  
23  
24  

This concern is not meant to map **columns**, only specific **cell** reference are allowed.

[#](#multi-dimensional-mapping) Multi-dimensional Mapping
---------------------------------------------------------

In case you have repeating data in your table, e. g. a spreadsheet looking like this:

Team 1

Team 2

Max

2

Peter

3

Annie

0

Alex

1

you are also able to define cell coordinates in a nested array:

    public function mapping(): array
    {
        return [
            'team1' => [
                [
                    'name' => 'A2',
                    'score' => 'B2',
                ],
                [
                    'name' => 'A3',
                    'score' => 'B3',
                ],
            ],
            'team2' => [
                [
                    'name' => 'C2',
                    'score' => 'D2',
                ],
                [
                    'name' => 'C3',
                    'score' => 'D3',
                ],
            ],
        ];
    }```
    
    Note that an array of the same form will be returned.
    

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

## === model.md ===

[#](#importing-to-models) Importing to models
=============================================

*   [Upserting models](#upserting-models)
    *   [Upserting with specific columns](#upserting-with-specific-columns)
*   [Skipping duplicate rows](#skipping-duplicate-rows)
*   [Skipping specific rows](#skipping-specific-rows)
*   [Possible column names](#possible-column-names)
*   [Cascading relation persistence](#cascading-relation-persistence)
*   [Handling persistence on your own](#handling-persistence-on-your-own)
    *   [Macro's and Mixins](#macro-s-and-mixins)

In case you want to import a workbook to an Eloquent model, you can use the `ToModel` concern. The concern enforces a `model()` method which accepts a model to be returned.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    
    class UsersImport implements ToModel
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
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

The returned model will be saved for you. Each row will result into (at least) one save and will also fire model events.

When using `ToModel` you should never save the model yourself, as that will break the batch insert functionality. If you need this, consider using `OnEachRow`.

[#](#upserting-models) Upserting models
---------------------------------------

In case you want to upsert models, instead of inserting, you can implement the `WithUpserts` concern.

    class UsersImport implements ToModel, WithUpserts
    {
        /**
         * @return string|array
         */
        public function uniqueBy()
        {
            return 'email';
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

In the example above, if a user already exists with the same email, the row will be updated instead. Behind the scenes, this feature uses the Laravel `upsert` method and the `uniqueBy` method is used for the second argument of the `upsert` method, which lists the column(s) that uniquely identify records within the associated table.

All databases except SQL Server require the `uniqueBy` columns to have a "primary" or "unique" index.

### [#](#upserting-with-specific-columns) Upserting with specific columns

By default, `upsert`, in case of updating, will update all columns that match model's attributes. However, if you need to update only specific column(s) during `upsert`, you can also implement the `WithUpsertColumns` concern.

    class UsersImport implements ToModel, WithUpserts, WithUpsertColumns
    {
        /**
         * @return array
         */
        public function upsertColumns()
        {
            return ['name', 'role'];
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

In this example, if a user already exists, only "name" and "role" columns will be updated.

[#](#skipping-duplicate-rows) Skipping duplicate rows
-----------------------------------------------------

In case you want to skip duplicate models, you can implement the `WithSkipDuplicates` concern.

    class UsersImport implements ToModel, WithSkipDuplicates
    {
        // No additional methods are required for this concern
    }
    

1  
2  
3  
4  

In the example above, if a user already exists with the same primary or unique key, the row will be ignored. Behind the scenes, this feature uses the Laravel `insertOrIgnore` method to insert records while ignoring duplicates, preventing any errors that would normally occur due to duplicate entries.

[#](#skipping-specific-rows) Skipping specific rows
---------------------------------------------------

In case you want to skip a row, you can return null.

    public function model(array $row)
    {
        if (!isset($row[0])) {
            return null;
        }
    
        return new User([
            'name' => $row[0],
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

[#](#possible-column-names) Possible column names
-------------------------------------------------

In case you want to import rows by several possible column names (using `WithHeadingRow`), you can use null coalescing operator (`??`). If the column with the first name (in example _client\_name_) exists and is not NULL, return its value; otherwise look for second possible name (in example _client_) etc.

    public function model(array $row)
    {
        return new User([
            'name' => $row['client_name'] ?? $row['client'] ?? $row['name'] ?? null
        ]);
    }
    

1  
2  
3  
4  
5  
6  

[#](#cascading-relation-persistence) Cascading relation persistence
-------------------------------------------------------------------

By default, ToModel doesn't save relations, you can enable this behaviour for `BelongsTo` and `BelongsToMany` relations by adding the `PersistRelations` concern.

    class UsersImport implements ToModel, PersistRelations
    {
        public function model(array $row)
        {
            $user = new User([
                'name' => $row[0],
            ]);
            
            // There should be a `public function team(): BelongsTo` relation in the User model.
            $user->setRelation('team', new Team(['name' => $row[1]]));
            
            return $user;
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

`PersistRelations` doesn't work together with BatchInserts.

[#](#handling-persistence-on-your-own) Handling persistence on your own
-----------------------------------------------------------------------

In some cases you might not have an import in which each row is an Eloquent model and you want more control over what happens. In those cases you can use the `OnEachRow` concern.

    namespace App\Imports;
    
    use App\Group;
    use App\User;
    use Maatwebsite\Excel\Row;
    use Maatwebsite\Excel\Concerns\OnEachRow;
    
    class UsersImport implements OnEachRow
    {
        public function onRow(Row $row)
        {
            $rowIndex = $row->getIndex();
            $row      = $row->toArray();
            
            $group = Group::firstOrCreate([
                'name' => $row[1],
            ]);
        
            $group->users()->create([
                'name' => $row[0],
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
18  
19  
20  
21  
22  
23  

When using `OnEachRow` you cannot use batch inserts, as the model is already persisted in the `onRow` method.

### [#](#macro-s-and-mixins) Macro's and Mixins

The Eloquent Builder/Model has a macro to directly import an excel to Eloquent rows. When using this, make sure your file has a heading row with the database table column names.

    User::query()->import('import-users-with-headings.xlsx');
    

1  

If you want to define the mapping yourself, you can use the `importAs` method.

    User::query()->importAs('import-users.xlsx', function (array $row) {
        return [
            'name'     => $row[0],
            'email'    => $row[1],
            'password' => 'secret',
        ];
    });
    

1  
2  
3  
4  
5  
6  
7

## === multiple-sheets.md ===

[#](#multiple-sheets) Multiple Sheets
=====================================

*   [Selecting sheets by worksheet index](#selecting-sheets-by-worksheet-index)
*   [Selecting sheets by worksheet name](#selecting-sheets-by-worksheet-name)
*   [Skipping unknown sheets](#skipping-unknown-sheets)
    *   [Skipping only specific sheets](#skipping-only-specific-sheets)
*   [Conditional sheet loading](#conditional-sheet-loading)
*   [Making calculations work when referencing between sheets](#making-calculations-work-when-referencing-between-sheets)

When a file has multiple sheets, each sheet will go through the import object. If you want to handle each sheet separately, you'll need to implement the `WithMultipleSheets` concern.

The `sheets()` method expects an array of sheet import objects to be returned. The order of the sheets is important, the first sheet import object in the array will automatically be linked to the first worksheet in the Excel file.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    
    class UsersImport implements WithMultipleSheets 
    {
       
        public function sheets(): array
        {
            return [
                new FirstSheetImport()
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

A sheet import class can import the same concerns as a normal import object.

    namespace App\Imports;
    
    use Illuminate\Support\Collection;
    use Maatwebsite\Excel\Concerns\ToCollection;
    
    class FirstSheetImport implements ToCollection
    {
        public function collection(Collection $rows)
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

[#](#selecting-sheets-by-worksheet-index) Selecting sheets by worksheet index
-----------------------------------------------------------------------------

If you want more control over which sheets are selected and how they are mapped to specific sheet import objects, you can use the sheet index as key. Sheet indices start at 0.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    
    class UsersImport implements WithMultipleSheets 
    {
       
        public function sheets(): array
        {
            return [
                0 => new FirstSheetImport(),
                1 => new SecondSheetImport(),
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

[#](#selecting-sheets-by-worksheet-name) Selecting sheets by worksheet name
---------------------------------------------------------------------------

If you only know the name of the worksheet and don't know the sheet index, you can also use the worksheet name as a selector. Put the worksheet name as array index to link that worksheet to your sheet import object.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    
    class UsersImport implements WithMultipleSheets 
    {
        public function sheets(): array
        {
            return [
                'Worksheet 1' => new FirstSheetImport(),
                'Worksheet 2' => new SecondSheetImport(),
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

Sheets that are not explicitly defined in the `sheet()` method, will be ignored and thus not be imported.

[#](#skipping-unknown-sheets) Skipping unknown sheets
-----------------------------------------------------

When you have defined a sheet **name** or **index** that does not exist a `Maatwebsite\Excel\Exceptions\SheetNotFoundException` will be thrown.

If you want to ignore when a sheet does not exists, you can use the `Maatwebsite\Excel\Concerns\SkipsUnknownSheets` concern.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    use Maatwebsite\Excel\Concerns\SkipsUnknownSheets;
    
    class UsersImport implements WithMultipleSheets, SkipsUnknownSheets
    {
        public function sheets(): array
        {
            return [
                'Worksheet 1' => new FirstSheetImport(),
                'Worksheet 2' => new SecondSheetImport(),
            ];
        }
        
        public function onUnknownSheet($sheetName)
        {
            // E.g. you can log that a sheet was not found.
            info("Sheet {$sheetName} was skipped");
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

### [#](#skipping-only-specific-sheets) Skipping only specific sheets

If you want to have 1 optional sheet and still have the others fail, you can also let the Sheet import object implement `SkipsUnknownSheets`.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\SkipsUnknownSheets;
    
    class FirstSheetImport implements SkipsUnknownSheets
    {
        public function onUnknownSheet($sheetName)
        {
            // E.g. you can log that a sheet was not found.
            info("Sheet {$sheetName} was skipped");
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

Now only `FirstSheetImport` will be skipped if it's not found. Any other defined sheet will be skipped.

[#](#conditional-sheet-loading) Conditional sheet loading
---------------------------------------------------------

If you want to indicate per import which sheets should be imported, you can use the `Maatwebsite\Excel\Concerns\WithConditionalSheets` trait.

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    use Maatwebsite\Excel\Concerns\WithConditionalSheets;
    
    class UsersImport implements WithMultipleSheets 
    {
        use WithConditionalSheets;
    
        public function conditionalSheets(): array
        {
            return [
                'Worksheet 1' => new FirstSheetImport(),
                'Worksheet 2' => new SecondSheetImport(),
                'Worksheet 3' => new ThirdSheetImport(),
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

Now you can use the `onlySheets` method to indicate which sheets should be loaded for this import.

    $import = new UsersImport();
    $import->onlySheets('Worksheet 1', 'Worksheet 3');
    
    Excel::import($import, 'users.xlsx');
    

1  
2  
3  
4  

[#](#making-calculations-work-when-referencing-between-sheets) Making calculations work when referencing between sheets
-----------------------------------------------------------------------------------------------------------------------

When importing you have to implement the `Maatwebsite\Excel\Concerns\WithCalculatedFormulas` concern for Laravel Excel to calculate values from formulas. However, if one sheet creates a calculation by referencing another sheet, e.g. `=Sheet1!A1`, then you also have to implement the concern `Maatwebsite\Excel\Concerns\HasReferencesToOtherSheets`. An example is given below

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithMultipleSheets;
    
    class UsersImport implements WithMultipleSheets 
    {
        public function sheets(): array
        {
            return [
                new FirstSheetImport(),
                new SecondSheetImport()
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

Then if `SecondSheetImport` contains formulas that reference `FirstSheetImport` then `FirstSheetImport` has to be defined using the `HasReferencesToOtherSheets` concern

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\ToArray;
    use Maatwebsite\Excel\Concerns\HasReferencesToOtherSheets;
    
    class FirstSheetImport implements ToArray, HasReferencesToOtherSheets
    {
        public function array(array: $row)
        {
            
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

    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\WithCalculatedFormulas;
    
    class SecondSheetImport implements ToArray, WithCalculatedFormulas
    {
        public function array(array: $row)
        {
            
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

## === progress-bar.md ===

[#](#progress-bar) Progress Bar
===============================

You can implement the `WithProgressBar` concern to display a progress bar when importing an Excel file via the console.

For example, your import class could look like this:

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Support\Facades\Hash;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithProgressBar;
    
    class UsersImport implements ToModel, WithProgressBar
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name'     => $row[0],
                'email'    => $row[1],
                'password' => Hash::make($row[2]),
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
18  
19  
20  
21  
22  
23  

In your console command, you'd use it as follows:

    <?php
    
    namespace App\Console\Commands;
    
    use App\Imports\UsersImport;
    use Illuminate\Console\Command;
    
    class ImportExcel extends Command
    {
        protected $signature = 'import:excel';
    
        protected $description = 'Laravel Excel importer';
    
        public function handle()
        {
            $this->output->title('Starting import');
            (new UsersImport)->withOutput($this->output)->import('users.xlsx');
            $this->output->success('Import successful');
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

By calling `php artisan import:excel` on the command line, your import will start. You should now see the start message, the progress bar and (when completed) the success message.

## === queued.md ===

[#](#queued-reading) Queued reading
===================================

*   [Notes](#notes)
*   [Queuing chunks](#queuing-chunks)
    *   [Explicit queued imports](#explicit-queued-imports)
    *   [Implicit queued imports](#implicit-queued-imports)
*   [Handling failures in queued imports](#handling-failures-in-queued-imports)
*   [Appending jobs](#appending-jobs)
*   [Custom queues](#custom-queues)
*   [Multi-server setup](#multi-server-setup)
*   [Job Middleware](#job-middleware)

[#](#notes) Notes
-----------------

You currently cannot queue `xls` imports. PhpSpreadsheet's Xls reader contains some non-utf8 characters, which makes it impossible to queue.

[#](#queuing-chunks) Queuing chunks
-----------------------------------

When using the `WithChunkReading` concern, you can also choose to execute each chunk into a queue job. You can do so by simply adding the `ShouldQueue` contract.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Illuminate\Contracts\Queue\ShouldQueue;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithChunkReading, ShouldQueue
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
    
        public function chunkSize(): int
        {
            return 1000;
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

Each chunk of 1000 rows will now be executed into a queue job.

`ShouldQueue` is only supported in combination with `WithChunkReading`.

### [#](#explicit-queued-imports) Explicit queued imports

You can explicitly queue the import by using `::queueImport`.

    Excel::queueImport(new UsersImport, 'users.xlsx');
    

1  

When using the `Importable` trait you can use the `queue` method:

    (new UsersImport)->queue('users.xlsx');
    

1  

The `ShouldQueue` is always required.

### [#](#implicit-queued-imports) Implicit queued imports

When `ShouldQueue` is used, the import will automatically be queued.

    Excel::import(new UsersImport, 'users.xlsx');
    

1  

[#](#handling-failures-in-queued-imports) Handling failures in queued imports
-----------------------------------------------------------------------------

When queuing imports you might want a way to handle failed imports. You can do this by using the `ImportFailed` event.

    namespace App\Imports;
    
    use App\User;
    use App\Notifications\ImportHasFailedNotification;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithEvents;
    use Maatwebsite\Excel\Events\ImportFailed;
    use Illuminate\Contracts\Queue\ShouldQueue;
    use Maatwebsite\Excel\Concerns\WithChunkReading;
    
    class UsersImport implements ToModel, WithChunkReading, ShouldQueue, WithEvents
    {
        public function __construct(User $importedBy)
        {
            $this->importedBy = $importedBy;
        }
    
        public function registerEvents(): array
        {
            return [
                ImportFailed::class => function(ImportFailed $event) {
                    $this->importedBy->notify(new ImportHasFailedNotification);
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

[#](#appending-jobs) Appending jobs
-----------------------------------

When queuing an import an instance of Laravel's `PendingDispatch` is returned. This means you can chain extra jobs that will be added to the end of the queue and only executed if all import jobs are correctly executed.

    (new UsersImport)->queue('users.xlsx')->chain([
        new NotifyUserOfCompletedImport(request()->user()),
    ]);
    

1  
2  
3  

    namespace App\Jobs;
    
    use App\User;
    use Illuminate\Bus\Queueable;
    use Illuminate\Contracts\Queue\ShouldQueue;
    use Illuminate\Queue\SerializesModels;
    
    class NotifyUserOfCompletedImport implements ShouldQueue
    {
        use Queueable, SerializesModels;
    
        public $user;
    
        public function __construct(User $user)
        {
            $this->user = $user;
        }
    
        public function handle()
        {
            $this->user->notify(new ImportReady());
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

[#](#custom-queues) Custom queues
---------------------------------

Because `PendingDispatch` is returned, we can also change the queue that should be used.

    (new UsersImport)->queue('users.xlsx')->allOnQueue('imports');
    

1  

[#](#multi-server-setup) Multi-server setup
-------------------------------------------

If you are dealing with a multi-server setup (using e.g. a loadbalancer), you might want to make sure the temporary file is the same for each job. You can achieve this by configuring a remote temporary file in the config.

In `config/excel.php`

    'temporary_files' => [
        'remote_disk' => 's3',
    ],
    

1  
2  
3  

When dealing with a multi server setup as above, it's possible for the clean up that occurs after entire queue has been run to only cleanup the server that the last AfterImportJob runs on. The rest of the server would still have the local temporary file stored on it. In this case your local storage limits can be exceeded and future imports won't be processed. To mitigate this you can set this config value to be true, so that after every queued chunk is processed the local temporary file is deleted on the server that processed it.

    'temporary_files' => [
        'force_resync_remote' => true,
    ],
    

1  
2  
3  

[#](#job-middleware) Job Middleware
-----------------------------------

If you are using Laravel, [job middleware (opens new window)](https://laravel.com/docs/7.x/queues#job-middleware) can be attached to the import class using the `middleware` method.

    namespace App\Imports;
    
    use App\Jobs\Middleware\RateLimited;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\FromQuery;
    
    class ImportClass implements FromQuery
    {
        use Importable;
    
        public function middleware()
        {
            return [new RateLimited];
        }
    
        public function retryUntil()
        {
            return now()->addSeconds(5);
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
21  
22  
23  
24  
25

## === start-row.md ===

[#](#start-row) Start row
=========================

If you want to skip a certain number of rows during an import, you can specify the starting row by implementing the `WithStartRow` concern.

    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithStartRow;
    
    class UsersImport implements ToModel, WithStartRow
    {
        public function model(array $row)
        {
            return new User([
                'name' => $row[0],
            ]);
        }
    
        public function startRow(): int
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

## === testing.md ===

[#](#testing) Testing
=====================

*   [Testing imports](#testing-imports)
*   [Testing queuing imports](#testing-queuing-imports)
*   [Testing imports with dynamic file name/path](#testing-imports-with-dynamic-file-name-path)

The Excel facade can be used to swap the importer to a fake.

[#](#testing-imports) Testing imports
-------------------------------------

    /**
    * @test
    */
    public function user_can_import_users() 
    {
        Excel::fake();
        
        $this->actingAs($this->givenUser())
             ->get('/users/import/xlsx');
    
        Excel::assertImported('filename.xlsx', 'diskName');
        
        Excel::assertImported('filename.xlsx', 'diskName', function(UsersImport $import) {
            return true;
        });
        
        // When passing the callback as 2nd param, the disk will be the default disk.
        Excel::assertImported('filename.xlsx', function(UsersImport $import) {
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

[#](#testing-queuing-imports) Testing queuing imports
-----------------------------------------------------

    /**
    * @test
    */
    public function user_can_queue_the_users_import() 
    {
        Excel::fake();
    
        $this->actingAs($this->givenUser())
             ->get('/users/queue/xlsx');
    
        Excel::assertQueued('filename.xlsx', 'diskName');
        
        Excel::assertQueued('filename.xlsx', 'diskName', function(UsersImport $import) {
            return true;
        });
        
        // When passing the callback as 2nd param, the disk will be the default disk.
        Excel::assertQueued('filename.xlsx', function(UsersImport $import) {
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

[#](#testing-imports-with-dynamic-file-name-path) Testing imports with dynamic file name/path
---------------------------------------------------------------------------------------------

If you have dynamic naming for files or paths, you can use a regular expression to represent those while testing:

    /**
    * @test
    */
    public function user_can_import_users() 
    {
        Excel::fake();
        
        $this->actingAs($this->givenUser())
             ->get('/users/import/xlsx');
        
        // Tells the mock to use regular expressions
        Excel::matchByRegex(); 
        // For a given dynamic named file 'dynamic_1234_filename.xlsx'
        Excel::assertImported('/\w{7}_\d{4}\_\w{8}\.xlsx/', 'diskName');
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

## === validation.md ===

[#](#row-validation) Row Validation
===================================

*   [Validating with a heading row](#validating-with-a-heading-row)
*   [Custom validation messages](#custom-validation-messages)
*   [Custom validation attributes](#custom-validation-attributes)
*   [Handling validation errors](#handling-validation-errors)
    *   [Database transactions](#database-transactions)
    *   [Gathering all failures at the end](#gathering-all-failures-at-the-end)
    *   [Skipping failures](#skipping-failures)
*   [Skipping empty rows](#skipping-empty-rows)
*   [Extend empty rows logic](#extend-empty-rows-logic)
    *   [Skipping errors](#skipping-errors)
*   [Row Validation without ToModel](#row-validation-without-tomodel)
*   [Prepare data for validation](#prepare-data-for-validation)
*   [Configuring the validator](#configuring-the-validator)

Sometimes you might want to validate each row before it's inserted into the database. By implementing the `WithValidation` concern, you can indicate the rules that each row need to adhere to.

The `rules()` method, expects an array with Laravel Validation rules to be returned.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Validation\Rule;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name'     => $row[0],
                'email'    => $row[1],
                'password' => 'secret',
            ]);
        }
    
        public function rules(): array
        {
            return [
                '1' => Rule::in(['patrick@maatwebsite.nl']),
    
                 // Above is alias for as it always validates in batches
                 '*.1' => Rule::in(['patrick@maatwebsite.nl']),
                 
                 // Can also use callback validation rules
                 '0' => function($attribute, $value, $onFailure) {
                      if ($value !== 'Patrick Brouwers') {
                           $onFailure('Name is not Patrick Brouwers');
                      }
                  }
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
36  
37  
38  
39  
40  

[#](#validating-with-a-heading-row) Validating with a heading row
-----------------------------------------------------------------

When using the `WithHeadingRow` concern, you can use the heading row name as rule attribute.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Validation\Rule;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    
    class UsersImport implements ToModel, WithValidation, WithHeadingRow
    {
        use Importable;
    
        public function model(array $row)
        {
            return new User([
                'name'     => $row['name'],
                'email'    => $row['email'],
                'password' => 'secret',
            ]);
        }
    
        public function rules(): array
        {
            return [
                'email' => Rule::in(['patrick@maatwebsite.nl']),
    
                 // Above is alias for as it always validates in batches
                 '*.email' => Rule::in(['patrick@maatwebsite.nl']),
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

If your validation rules reference other field names, as in the `different`, `lt`, `lte`, `gt`, `gte`, and `same` rules, the field name must be prefixed with `*.` as in the example below, because validation is done in batches.

    public function rules(): array
    {
        return [
            'maximum' => 'gte:*.minimum',
        ];
    }
    

1  
2  
3  
4  
5  
6  

[#](#custom-validation-messages) Custom validation messages
-----------------------------------------------------------

By adding `customValidationMessages()` method to your import, you can specify custom messages for each failure.

    /**
    * @return array
    */
    public function rules(): array
    {
        return [
            '1' => Rule::in(['patrick@maatwebsite.nl']),
        ];
    }
    
    /**
     * @return array
     */
    public function customValidationMessages()
    {
        return [
            '1.in' => 'Custom message for :attribute.',
        ];
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

[#](#custom-validation-attributes) Custom validation attributes
---------------------------------------------------------------

By adding `customValidationAttributes()` method to your import, you can specify custom attribute names for each column.

    /**
    * @return array
    */
    public function rules(): array
    {
        return [
            '1' => Rule::in(['patrick@maatwebsite.nl']),
        ];
    }
    
    /**
     * @return array
     */
    public function customValidationAttributes()
    {
        return ['1' => 'email'];
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

[#](#handling-validation-errors) Handling validation errors
-----------------------------------------------------------

### [#](#database-transactions) Database transactions

The entire import is automatically wrapped in a **database transaction**, that means that _every_ error will rollback the entire import. When using batch inserts, only the **current** batch will be rollbacked.

#### [#](#disable-transactions) Disable transactions

If you prefer to not have any database transactions around your import (or chunk import), you can change which transaction handler you want to use in the config:

In `config/excel.php`:

    'transactions' => [
        'handler' => 'db',
    ],
    

1  
2  
3  

Supported handlers are currently: `null` or `db`.

#### [#](#custom-transaction-handlers) Custom transaction handlers

If you want a custom transaction handler (for e.g. a MongoDB database), you can add your own handler:

    $this->app->make(\Maatwebsite\Excel\Transactions\TransactionManager::class)->extend('your_handler', function() {
        return new YourTransactionHandler();
    });
    

1  
2  
3  

The Handler should implement `Maatwebsite\Excel\Transactions\TransactionHandler`.

### [#](#gathering-all-failures-at-the-end) Gathering all failures at the end

You can gather all validation failures at the end of the import, when used in conjunction with Batch Inserts. You can try-catch the `ValidationException`. On this exception you can get all failures.

Each failure is an instance of `Maatwebsite\Excel\Validators\Failure`. The `Failure` holds information about which row, which column and what the validation errors are for that cell.

    try {
        $import->import('import-users.xlsx');
    } catch (\Maatwebsite\Excel\Validators\ValidationException $e) {
         $failures = $e->failures();
         
         foreach ($failures as $failure) {
             $failure->row(); // row that went wrong
             $failure->attribute(); // either heading key (if using heading row concern) or column index
             $failure->errors(); // Actual error messages from Laravel validator
             $failure->values(); // The values of the row that has failed.
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

### [#](#skipping-failures) Skipping failures

Sometimes you might want to skip failures. By using the `SkipsOnFailure` concern, you get control over what happens the moment a validation failure happens. When using `SkipsOnFailure` the entire import will **not** be rollbacked when a failure occurs.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnFailure;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnFailure
    {
        use Importable;
    
        /**
         * @param Failure[] $failures
         */
        public function onFailure(Failure ...$failures)
        {
            // Handle the failures how you'd like.
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

If you automatically want to skip all failed rows and collect the failures at the end of the import, you can use the `Maatwebsite\Excel\Concerns\SkipsFailures` trait.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnFailure;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\SkipsFailures;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnFailure
    {
        use Importable, SkipsFailures;
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

Every row that has failed the validation rules, will have been skipped. We can now collect all the failures at the end:

    $import = new UsersImport();
    $import->import('users.xlsx');
    
    foreach ($import->failures() as $failure) {
         $failure->row(); // row that went wrong
         $failure->attribute(); // either heading key (if using heading row concern) or column index
         $failure->errors(); // Actual error messages from Laravel validator
         $failure->values(); // The values of the row that has failed.
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

[#](#skipping-empty-rows) Skipping empty rows
---------------------------------------------

Sometimes you might want to skip empty rows, for example when using the `required` validation rule. By using the `SkipsEmptyRows` concern, empty rows will get skipped during both validation **and the import**.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsEmptyRows;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\WithHeadingRow;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, SkipsEmptyRows, WithHeadingRow, WithValidation
    {
        use Importable;
        
        public function rules(): array
        {
            return [
                'name' => [
                    'required',
                    'string',
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
25  

[#](#extend-empty-rows-logic) Extend empty rows logic
-----------------------------------------------------

Along with `SkipsEmptyRows` you can have your own logic to skip rows by having `isEmptyWhen` in the importer

    <?php
    
    namespace App\Imports;
    
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\ToArray;
    
    class UsersImport implements ToArray,
    {
        use Importable;
        
        public function isEmptyWhen(array $row): bool
        {
            return $row['name'] === 'John Doe';
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

### [#](#skipping-errors) Skipping errors

Sometimes you might want to skip **all** errors, e.g. duplicate database records. By using the `SkipsOnError` concern, you get control over what happens the moment a model import fails. When using `SkipsOnError` the entire import will **not** be rollbacked when an database exception occurs.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnError;
    use Maatwebsite\Excel\Concerns\WithValidation;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnError
    {
        use Importable;
    
        /**
         * @param \Throwable $e
         */
        public function onError(\Throwable $e)
        {
            // Handle the exception how you'd like.
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

If you automatically want to skip all exceptions and collect them at the end of the import, you can use the `Maatwebsite\Excel\Concerns\SkipsErrors` trait.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Maatwebsite\Excel\Concerns\ToModel;
    use Maatwebsite\Excel\Validators\Failure;
    use Maatwebsite\Excel\Concerns\Importable;
    use Maatwebsite\Excel\Concerns\SkipsOnError;
    use Maatwebsite\Excel\Concerns\WithValidation;
    use Maatwebsite\Excel\Concerns\SkipsErrors;
    
    class UsersImport implements ToModel, WithValidation, SkipsOnError
    {
        use Importable, SkipsErrors;
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

Every row that has errored, will have been skipped. We can now collect all the errors at the end:

    $import = new UsersImport();
    $import->import('users.xlsx');
    
    dd($import->errors());
    

1  
2  
3  
4  

[#](#row-validation-without-tomodel) Row Validation without ToModel
-------------------------------------------------------------------

If you are not using the `ToModel` concern, you can very easily do row validation by just using the Laravel validator.

    <?php
    
    namespace App\Imports;
    
    use App\User;
    use Illuminate\Support\Collection;
    use Illuminate\Support\Facades\Validator;
    use Maatwebsite\Excel\Concerns\ToCollection;
    
    class UsersImport implements ToCollection
    {
        public function collection(Collection $rows)
        {
             Validator::make($rows->toArray(), [
                 '*.0' => 'required',
             ])->validate();
    
            foreach ($rows as $row) {
                User::create([
                    'name' => $row[0],
                ]);
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
18  
19  
20  
21  
22  
23  
24  

[#](#prepare-data-for-validation) Prepare data for validation
-------------------------------------------------------------

Sometimes data may not pass validation directly, but still be valid. When this happens you may want to tweak the data slightly before sending it to the validator, to do this you may add a `prepareForValidation` method on your import, this method receives row data as well as the row number and should return the manipulated row data.

    class UsersImport implements WithValidation
    {
        public function prepareForValidation($data, $index)
        {
            $data['email'] = $data['email'] ?? $this->myOtherWayOfFindingTheEmail($data);
            
            return $data;
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

[#](#configuring-the-validator) Configuring the validator
---------------------------------------------------------

If you want to add conditional validation or complex validation that cannot be expressed through rules you can configure the validator similar to how you would do this with a [Form request (opens new window)](https://laravel.com/docs/master/validation#form-request-validation)

Manual validation

You can use `$validator->getData()` to get access to the data under validation

    class UsersImport implements WithValidation
    {
        public function withValidator($validator)
        {
            $validator->after(function ($validator) {
                if ($this->somethingElseIsInvalid()) {
                    $validator->errors()->add('field', 'Something is wrong with this field!');
                }
            });
    
            // or...
    
            $validator->sometimes('*.email', 'required', $this->someConditionalRequirement());
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

Validation rules

For a list of all validation rules, please refer to the [Laravel document (opens new window)](https://laravel.com/docs/master/validation#available-validation-rules).

Validating Across Multiple Rows

Validation rules that check multiple rows (such as `distinct`) will work only when using `WithBatchInserts` or `ToCollection` concerns.