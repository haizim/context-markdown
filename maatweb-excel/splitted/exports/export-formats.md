[#](#export-formats) Export formats
===================================

*   [XLSX](#xlsx)
*   [CSV](#csv)
*   [TSV](#tsv)
*   [ODS](#ods)
*   [XLS](#xls)
*   [HTML](#html)
*   [MPDF](#mpdf)
*   [DOMPDF](#dompdf)
*   [TCPDF](#tcpdf)

By default, the export format is determined by the extension of the file. If you want to explicitly configure the export format, you can pass it through as 2nd parameter.

[#](#xlsx) XLSX
---------------

    return Excel::download(new InvoicesExport, 'invoices.xlsx', \Maatwebsite\Excel\Excel::XLSX);
    

1  

[#](#csv) CSV
-------------

    return Excel::download(new InvoicesExport, 'invoices.csv', \Maatwebsite\Excel\Excel::CSV);
    

1  

By default the CSV is download with Content Type `text/plain`, if you want to customize the Content-Type header, you can do so by passing it as 3rd parameter.

    return Excel::download(new InvoicesExport, 'invoices.csv', \Maatwebsite\Excel\Excel::CSV, [
          'Content-Type' => 'text/csv',
    ]);
    

1  
2  
3  

Laravel CSV

You may have a look at our [Laravel CSV](/csv/1.0/getting-started/) package as well.

[#](#tsv) TSV
-------------

    return Excel::download(new InvoicesExport, 'invoices.tsv', \Maatwebsite\Excel\Excel::TSV);
    

1  

[#](#ods) ODS
-------------

    return Excel::download(new InvoicesExport, 'invoices.ods', \Maatwebsite\Excel\Excel::ODS);
    

1  

[#](#xls) XLS
-------------

    return Excel::download(new InvoicesExport, 'invoices.xls', \Maatwebsite\Excel\Excel::XLS);
    

1  

[#](#html) HTML
---------------

    return Excel::download(new InvoicesExport, 'invoices.html', \Maatwebsite\Excel\Excel::HTML);
    

1  

Exporting to PDF

If you'd like to export to PDF, you must now install a PDF rendering library yourself. Please refer to the [PhpSpreadsheet Documentation (opens new window)](https://phpspreadsheet.readthedocs.io/en/latest/topics/reading-and-writing-to-file/#pdf) for more information.

[#](#mpdf) MPDF
---------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::MPDF);
    

1  

[#](#dompdf) DOMPDF
-------------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::DOMPDF);
    

1  

[#](#tcpdf) TCPDF
-----------------

    return Excel::download(new InvoicesExport, 'invoices.pdf', \Maatwebsite\Excel\Excel::TCPDF);
    

1