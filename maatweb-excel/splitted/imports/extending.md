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