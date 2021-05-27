---
description: The Reference Page Tag consists of a Page Tag Execution Script that resides on a web server, and when called results in the collection of all client-side data for the page requested by the site visitor.
title: Editing the Reference Page Tag Execution Script
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
---
# Editing the Reference Page Tag Execution Script{#editing-the-reference-page-tag-execution-script}

The Reference Page Tag consists of a Page Tag Execution Script that resides on a web server, and when called results in the collection of all client-side data for the page requested by the site visitor.

 You can modify the [!DNL Reference Page Tag Execution Script] to collect additional information that may be identified during requirements gathering meetings with the Adobe Consulting Services team. The [!DNL Reference Page Tag Execution Script] is relatively small in size to avoid large download additions to your web pages.

The following [!DNL Reference Page Tag Execution Script] code is provided to you in a file named [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 

```

To facilitate data collection through the use of the [!DNL Reference Page Tag], complete the following steps: 

1. Create or place the 1 pixel by 1 pixel image file named [!DNL zag.gif] into a directory present on your web server.
1. Modify the cd variable to reference the appropriate domain of your website or Adobe managed services domain from which the [!DNL zag.gif] file is referenced. The reference to the file is created through the execution of the [!DNL zig.js] file functions. For example:

   ```
   //www.mysite.com
   ```

1. Modify the cu variable to reference the appropriate path to the location of the [!DNL zag.gif] file. For example

   ```
   /scripts
   ```

1. Ensure appropriate cache-control headers are established for the [!DNL zag.gif] and [!DNL zig.js] files.
