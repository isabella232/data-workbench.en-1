---
description: As a part of the Baseline Measurement data collected, Sensor collects the domain cookies sent from a visitor’s machine when making a request from your web server.
solution: Analytics
title: Acquiring Measurement Data Through Cookies
topic: Data workbench
uuid: 34cd6baf-6317-4774-8165-58208698b53c
---

# Acquiring Measurement Data Through Cookies{#acquiring-measurement-data-through-cookies}

As a part of the Baseline Measurement data collected, Sensor collects the domain cookies sent from a visitor’s machine when making a request from your web server.

 This includes both persistent and session cookies that your website sets when a visitor interacts with your system.

In most cases, websites set persistent cookies to identify visitors or capture user input for use within subsequent visitor sessions. Any information written to and stored within persistent cookies can be captured and used alongside all other measurement data within the data workbench server.

An example of such a persistent cookie could involve a customer identifier in the form of a numeric key present within a domain specific cookie residing on the visitor’s machine. In addition to identifying the user as a return visitor, the persistent cookie could also be used to further identify the visitor as a returning customer or to tie the visitor to information contained within a customer database to allow offline customer demographic information to be displayed within [!DNL Site] and used for interactive analysis.

Session cookies can be a good mechanism to collect user input through form fields or other dynamic interactive elements within your website. In the case of a website implementing forms to capture user-specific input data, the information remains in the session cookie only for as long as the session is active. When a user leaves your website or subsequently ends a session, the information is no longer stored on the user’s computer. However, the information entered is captured by [!DNL Sensor] and made available as measurement data within [!DNL Site].

Following is an example of using a session cookie to capture a single form variable entered by a visitor.

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 

```

In this example, a function is called to set a session cookie on the visitor’s machine with the name of the field and the value entered into the form field. As the form is submitted, and the subsequent web page is requested, the session cookie set is passed to the web server and collected by [!DNL Sensor]. The following data is therefore available within the data workbench server for use in data analysis:

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_1  | Value associated with the v_1 cookie. This value represents the NAME entered into the form field that resulted in the session cookie being set.  | v_1=John Smith  |

Session cookies may also be utilized to iteratively capture form fields or a multitude of embedded JavaScript variables present within an HTML page. In the following example, JavaScript is used to recursively capture any form field present within an HTML file and set a session cookie with the appropriate name=value pairs.

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

In this example, a session cookie is set on the visitor’s machine with the name and value of every form field that exists within the form. This includes input fields, check boxes, radio buttons, select boxes, and text areas. As you may notice in this example, because the number of form fields is unknown, it is necessary to capture all form name and field values as a single string, delimited by an ampersand. This step must be taken because of a limit on the number of cookies a user may have on his or her computer at one point in time. Microsoft Internet Explorer allows only twenty (20) session cookies to be present before it begins dropping the oldest. 
