---
description: For some sites, it is necessary to use embedded object requests to pass information to the web server so that details about what page was actually served may be acquired by Sensor and used for reporting and analysis.
seo-description: For some sites, it is necessary to use embedded object requests to pass information to the web server so that details about what page was actually served may be acquired by Sensor and used for reporting and analysis.
seo-title: Acquiring Dynamic Page Names
solution: Analytics
title: Acquiring Dynamic Page Names
topic: Data workbench
uuid: acff3bc7-37d9-4057-9980-eb3b272f3064
index: y
internal: n
snippet: y
---

# Acquiring Dynamic Page Names{#acquiring-dynamic-page-names}

For some sites, it is necessary to use embedded object requests to pass information to the web server so that details about what page was actually served may be acquired by Sensor and used for reporting and analysis.

 This might be required if the page’s URL, as seen by the web server, is not indicative of the page content that is shown to the browser. This case often results from the use of personalization or dynamic content management systems in which the actual content served in a page is determined on the fly by the URL, the cookie, related data and application logic.

The implementation of an embedded object to gather additional measurements should have minimal impact on your overall site performance. Adobe suggests that you embed a JavaScript file as the object used to collect the extended attributes. (Note that a JavaScript file can be embedded without any potential impact to the layout and presentation of your web page as may result with the use of an embedded image.) To accurately capture the information passed within the embedded object, Adobe also suggests that a common name be used. For naming purposes, Adobe refers to this object as [!DNL zig.js]. The [!DNL zig.js] file should be created within the appropriate directory on a web server on which [!DNL Sensor] is installed. This file needs to exist so that the request does not return a 404 error code. The contents of the file itself are not important. You should use a blank file named [!DNL zig.js] to minimize the amount of network traffic incurred as a result of the request.

For [!DNL Sensor] to collect a usable name for the page that was actually served, a few lines of JavaScript code must be added to the dynamic pages that you want to track or to which you want to add a unique page name. This code embeds a snippet of JavaScript in the page, which causes a tertiary embedded object request to be made to the web server as the page is loading. That request sends details about the specific page that was served back to the web server. The name of the page that was actually served is carried back to the web server as a variable in the query string of the embedded object (in this case JavaScript) request.

In general, the object request embedded in each such HTML page should look like the following:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] ensures that [!DNL Sensor] logs the request in spite of the [!DNL Sensor] content type filtering rules to the contrary, such as the filtering out of JavaScript and image requests before they are stored. The declared v_pn variable identifies the name of the actual page content being served so that [!DNL Site] knows the name of the page the visitor actually viewed. The v_pn value could be established manually or by other script or application code.

After the value is collected, you can configure the data workbench server to use the contents of the query string variable (name=value pair, for example, v_pn=Application Form) appended to the [!DNL zag.gif] URI (for example, [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form]), as an augmentation of the [!DNL zag.gif] URI. In addition to the baseline measurements acquired with every HTTP request, an extended measurement would be acquired with this request.

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_pn=  | Value associated with the v_pn query string variable  | v_pn=Application Form  |

