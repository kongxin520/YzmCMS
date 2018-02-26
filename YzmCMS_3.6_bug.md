# YzmCMS

**YzmCMS  3.6  bug**


> [Suggested description]    
> YzmCMS 3.6    
> allows remote attackers to discover the full path via a direct request to application/install/templates/s1.php.   
>
> ------------------------------------------
>
> [Additional Information]        
> The vulnerability was discovered by downloading the program's source code to local and online deployment tests.      
>
> Location:        
> domain/application/install/templates/s1.php         
>
> Code:      
>             <?php require './templates/header.php'; ?>      
>
> Rows : 10      
>
> Return error :      
> Warning: require(./templates/header.php): failed to open stream: No such file or directory in /www/application/install/templates/s1.php on line 10      
> Fatal error: require(): Failed opening required './templates/header.php' (include_path='.;C:\php\pear') in /www/application/install/templates/s1.php on line 10      
>
> Harm:      
> Web Site physical path leakage .      
>
> Conditions for Execution:      
> Normal access can      
>
> Edition:      
> YzmCMS  3.6      
>
> Cause the cause :      
> require(): Failed opening required './templates/header.php' (include_path='.;C:\php\pear') in /www/application/install/templates/s1.php on line 10, cause path leakage.      
>
> POC :     
> http://127.0.0.1/application/install/templates/s1.php      
>
>
> fix suggestions :      
> Modify the application source code to avoid information leakage.      
>
> ------------------------------------------
>
> [VulnerabilityType Other]     
> physical path leakage     
>
> ------------------------------------------
>
> [Vendor of Product]      
> YzmCMS     
>
> ------------------------------------------
>
> [Affected Product Code Base]      
> YzmCMS - 3.6      
>
> ------------------------------------------
>
> [Affected Component]     
> /application/install/templates/s1.php  , require(./templates/header.php): failed to open stream: No such file or directory , Web Site physical path leakage .     
>
> ------------------------------------------
>
> [Attack Type]     
> Remote    
>
> ------------------------------------------
>
> [Impact Information Disclosure]     
> true     
>
> ------------------------------------------
>
> [Attack Vectors]      
> The vulnerability is triggered by accessing the following URL :      
> http://domain/application/install/templates/s1.php      
>
> ------------------------------------------
>
> [Discoverer]      
> kongxin      
