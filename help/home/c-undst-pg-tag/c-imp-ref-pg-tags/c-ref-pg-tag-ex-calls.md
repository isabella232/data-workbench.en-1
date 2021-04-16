---
description: The Reference Page Tag Execution Call is inserted into web pages for which you want to collect measurement data.
title: Adding Reference Page Tag Execution Calls
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
---
# Adding Reference Page Tag Execution Calls{#adding-reference-page-tag-execution-calls}

The Reference Page Tag Execution Call is inserted into web pages for which you want to collect measurement data.

 It should be included in the body of the HTML document and can be placed within a global include footer if applicable. The [!DNL Reference Page Tag Execution Call] can be modified by your team to collect additional information that might be identified during requirements gathering meetings with the Adobe Consulting Services team.

To facilitate data collection through the use of the [!DNL Reference Page Tag], complete the following steps:

1. Copy the following code into your HTML document body: 

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
    
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
    
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. Modify the path to the location of the [!DNL zig.js] and [!DNL zag.gif] files. For example: 

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   
   ```

Please ensure that the appropriate HTTP Cache-Control headers have been set on your web server to ensure that the [!DNL zig.js]and [!DNL zag.gif] files are not cached by the browser. You can set the HTTP Cache-Control header information using one of two methods. The first method is to set an HTTP header via the web server. The second method is to set an HTTP header for each specific page or embedded object using script. With the scripting method, the web page must have been created using a programming language such as JSP or ASP. The page then is scripted so that it sends the appropriate header information. Two obvious drawbacks accompany this method: 1) all pages must be coded to send the header, and 2) the pages cannot be static HTML, which has some effect on web server performance.

Web sites running on Microsoft IIS can add the appropriate HTTP header through the Microsoft Management Console. Websites served from Netscape iPlanet Web Servers can accomplish this by editing the [!DNL obj.conf] file within the site’s configuration directory. The Apache Web Server provides webmasters the ability to customize HTTP headers using the included mod_headers module where AOLServer becomes customizable through the use of Tcl modules. Before implementing HTTP Cache-Control headers, you should refer to the documentation specific to your web server platform.

In general, the HTTP header should be structured as follows: 

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
