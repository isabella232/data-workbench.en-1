---
description: Using the JavaScript Document Object Model, additional scripting methods can be employed to augment the request for the zig.js file.
seo-description: Using the JavaScript Document Object Model, additional scripting methods can be employed to augment the request for the zig.js file.
seo-title: Acquiring Document Objects
solution: Analytics
title: Acquiring Document Objects
topic: Data workbench
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
index: y
internal: n
snippet: y
---

# Acquiring Document Objects{#acquiring-document-objects}

Using the JavaScript Document Object Model, additional scripting methods can be employed to augment the request for the zig.js file.

 Information such as the value of META tags, ID values of DIV tags, and so forth, can be referenced by name and collected as variables for use in analysis. For example, to dynamically capture the information contained within the META element of the HTML document, you can use the following JavaScript syntax:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_1=  | Value associated with the METAVALUE query string variable. This value represents the data within the META element of the HTML document.  | v_1=This page serves content related to the order thank you page.  |

After the data is collected, you can configure the data workbench server to process this measurement data for the purposes of analysis and reporting. 
