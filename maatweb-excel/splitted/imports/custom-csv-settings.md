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