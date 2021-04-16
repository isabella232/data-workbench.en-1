---
description: Values entered into a form in a web page can be collected and appended in the query string of the subsequently requested page (on form submission) through the use of JavaScript.
title: General Information
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
---
# General Information{#general-information}

Values entered into a form in a web page can be collected and appended in the query string of the subsequently requested page (on form submission) through the use of JavaScript.

This is shown in the following example. Include this JavaScript after any form validation scripts used in your HTML pages.

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 

```

This example appends the values entered into the form by the browser user to the subsequent “thankyou.asp” page indicated in the FORM Action value as follows:

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

The following extended measurements would be acquired with this request in addition to the baseline measurements collected by [!DNL Sensor]:

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_1  | Value associated with the NAME form field  | v_1=John Smith  |
|  v_2  | Value associated with the CITY form field  | v_2=Los Angeles  |
|  v_3  | Value associated with the STATE form field  | v_3=California  |
|  v_4  | Value associated with the ZIP form field  | v_4=90210  |
