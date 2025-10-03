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