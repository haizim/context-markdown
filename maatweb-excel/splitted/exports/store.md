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