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