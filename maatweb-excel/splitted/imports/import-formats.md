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