---
description: Web pages are often structured using ASP (Active Server Pages) programming language.
solution: Analytics
title: ASP-Specific Information
topic: Data workbench
uuid: 552288cb-b775-4121-8869-322f2a26932b
---

# ASP-Specific Information{#asp-specific-information}

Web pages are often structured using ASP (Active Server Pages) programming language.

 ASP is a Microsoft technology that runs within IIS (Internet Information Services). When a browser requests an ASP file, IIS passes the request to the ASP engine. The ASP engine reads the ASP file, line by line, and executes the scripts in the file. Finally, the ASP file is returned to the browser as plain HTML. ASP provides RESPOND or REQUEST objects which, in addition to other uses, allow the response or request of user queries or data submitted from HTML forms.

In certain cases, you may not want to append the values entered into forms to the URL that is displayed within the Address bar of a user’s browser or that is viewable within the HTML code itself. Simple server-side JavaScript allows you to append form field names and their respective values to the log file without making them available within the user’s browser or embedding them into the HTML file. To capture the actual form values entered into particular forms within your website, a few lines of code must be added to append the form values to the log request.

Within the processing page of a form, include the following code to append the entered form values to the request data (in addition to writing the submitted form values to an external database or other location):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

This process would append the form values as defined to the request data for the [!DNL Form Processing] page. Within the log data, the appended values would be available as query strings of the [!DNL Form Processing] page as illustrated below. For example, v_1, v_2, v_3 and v_4 would now be query strings containing the data entered into the appropriate form fields. The syntax described in the example above can be duplicated for any additional form fields and values that you want to capture.

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

If you want every form field and value to be captured and available for analysis, you can use the following syntax:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 

```

This example would take all form fields present within the HTML along with their respective values and append them as query strings to the log entry for the [!DNL Form Processing] page. It should be noted that this would include any hidden fields present within the form.

The log data would be augmented as detailed in the following table:

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_1  | Value associated with the NAME query string  | v_1=John Smith  |
|  v_2  | Value associated with the CITY query string  | v_2=Los Angeles  |
|  v_3  | Value associated with the STATE query string  | v_3=California  |
|  v_4  | Value associated with the ZIP query string  | v_4=90210  |

