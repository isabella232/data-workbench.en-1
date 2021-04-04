---
description: Capturing activity across third-party website links to enable Exit Target analysis.
solution: Analytics
title: Tracking Exits to External Links
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
---
# Tracking Exits to External Links{#tracking-exits-to-external-links}

Capturing activity across third-party website links to enable Exit Target analysis.

 Web pages can contain links to third-party websites, and activity across those links can be captured to enable Exit Target analysis, especially in the case that the third-party site is responsible for paying referral fees when such referrals are received. Because the click event is written to the log files of the third-party system by default, modifications need to be made to the link for the click event to be captured locally. The third-party link present within your website must be modified as follows:

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

The referenced [!DNL PageExit.htm] file must be created and should be structured to contain the following script:

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

By making the request for the [!DNL PageExit.htm] file, the v_eurl value is collected for analysis purposes. Additionally, when [!DNL PageExit.htm] is loaded, it immediately redirects to the specified v_eurl target location.

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_eurl  | Value associated with the v_eurl query string variable. This value represents the target URL of the link present within the HTML page.  | v_eurl=www.othersite.com  |
