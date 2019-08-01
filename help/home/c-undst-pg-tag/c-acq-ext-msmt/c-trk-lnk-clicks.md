---
description: Steps used to facilitate the collection of Link Clicks through the use of the Reference Page Tag.
seo-description: Steps used to facilitate the collection of Link Clicks through the use of the Reference Page Tag.
seo-title: Tracking Link Clicks
solution: Analytics
title: Tracking Link Clicks
topic: Data workbench
uuid: 4ed3c721-7652-44f5-a56e-888c52f16e5f
index: y
internal: n
snippet: y
---

# Tracking Link Clicks{#tracking-link-clicks}

Steps used to facilitate the collection of Link Clicks through the use of the Reference Page Tag.

Through the deployment of the [!DNL Reference Page Tag], it is possible to collect measurement data denoting the links (or href values) that visitors click while visiting particular pages. Typically, this collection does not involve the implementation of additional link identifiers into your HTML pages.

To facilitate collection of Link Clicks through the use of the [!DNL Reference Page Tag], complete the following steps:

1. Copy the following code into the existing file named [!DNL zig.js]: 

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. Create or place the 1 pixel by 1 pixel image file named [!DNL zag2.gif] into a directory present on your web server. 
1. Modify the [!DNL lc.src] variable to reference the appropriate domain of your website from which the [!DNL zag2.gif]file is referenced. 

1. Ensure appropriate cache-control headers are established for the [!DNL zag.gif] and [!DNL zig.js] files. 

1. Within the HTML files you desire to collect link click values from, the [!DNL Reference Page Tag Execution Call] must be modified to inform the [!DNL Page Tag Execution Script] to capture link clicks for that page. To do so, change the vlc variable value to “1” as highlighted in the following code example:

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_ln=  | Value denoting the Impression Campaign  | v_ln=”About%20Us”  |

