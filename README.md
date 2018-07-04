# utl_creating_your_own_arbitrary_date_formats
Creating your own arbitrary date formats. Keywords: sas sql join merge big data analytics macros oracle teradata mysql sas communities stackoverflow statistics artificial inteligence AI Python R Java Javascript WPS Matlab SPSS Scala Perl C C# Excel MS Access JSON graphics maps NLP natural language processing machine learning igraph DOSUBL DOW loop stackoverflow SAS community.

    Creating your own arbitrary date formats

    see
    https://listserv.uga.edu/cgi-bin/wa?A2=SAS-L;c75c94d6.1807a

    Joe Matise's profile
    snoopy369@gmail.com

    Same result in WPS and SAS

    SAS Doc
    https://v8doc.sas.com/sashtml/proc/zpicture.htm


    SAS/WPS does not support tis date format (informat anydate. works)

       2018JUL04


    INPUT
    =====

      today()

    EXAMPLE OUTPUT

      2018JUL04


    PROCESS
    =======

      * Joe Matise;
      proc format;
         picture YYYYMONDD other='%0Y%0b%0d' (datatype=date);
      run;

      data tst;
       cur=today();
       putlog cur= YYYYMONDD10.;
      run;quit;


    OUTPUT
    ======

      CUR = 2018JUL04

    *                _              _       _
     _ __ ___   __ _| | _____    __| | __ _| |_ __ _
    | '_ ` _ \ / _` | |/ / _ \  / _` |/ _` | __/ _` |
    | | | | | | (_| |   <  __/ | (_| | (_| | || (_| |
    |_| |_| |_|\__,_|_|\_\___|  \__,_|\__,_|\__\__,_|

    ;

       today()

    *          _       _   _
     ___  ___ | |_   _| |_(_) ___  _ __
    / __|/ _ \| | | | | __| |/ _ \| '_ \
    \__ \ (_) | | |_| | |_| | (_) | | | |
    |___/\___/|_|\__,_|\__|_|\___/|_| |_|

    ;

    SAS see process

    * WPS;
    %utl_submit_wps64('
    libname wrk sas7bdat "%sysfunc(pathname(work))";
      proc format;
         picture YYYYMONDD other="%0Y%0b%0d" (datatype=date);
      run;
      data tst;
       cur=today();
       putlog cur= YYYYMONDD10.;
      run;quit;
    run;quit;
    ');

