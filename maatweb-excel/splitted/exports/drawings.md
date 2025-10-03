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