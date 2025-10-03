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