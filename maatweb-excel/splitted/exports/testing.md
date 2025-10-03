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