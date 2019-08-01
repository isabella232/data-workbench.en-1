---
description: Websites architected using Flash require special attention with respect to the capture of visitor actions performed within the rich media content.
seo-description: Websites architected using Flash require special attention with respect to the capture of visitor actions performed within the rich media content.
seo-title: Tracking Visitor Activity Within Flash Rich Media Content
solution: Analytics
title: Tracking Visitor Activity Within Flash Rich Media Content
topic: Data workbench
uuid: b5edf2f2-9b1c-429a-8d65-ff8ffe32a553
index: y
internal: n
snippet: y
---

# Tracking Visitor Activity Within Flash Rich Media Content{#tracking-visitor-activity-within-flash-rich-media-content}

Websites architected using Flash require special attention with respect to the capture of visitor actions performed within the rich media content.

 Using [!DNL Flash] ActionScript, you can make simple changes to your existing [!DNL Flash] movies to allow the tracking of all visitor interactions with the movie, such as button clicks or mouse movements.

To facilitate Visitor activity tracking within your [!DNL Flash] movie, please follow the steps listed below: 

1. Add the following ActionScript code to your movie. This code represents a function that can be called by events within the [!DNL Flash] movie that you want to track.

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. Create a blank file named [!DNL flashtag.txt] and place the file on your web servers.
1. Within the function in Step 1, replace the [!DNL [PATH_TO_WEB_SERVER]] placeholder with the fully qualified or relative path to the location of the [!DNL flashtag.txt] file. For example:

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. Add the following ActionScript code to all events to be tracked. This code represents a function call used to capture data about the event:

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   This example illustrates the use of the on(release) event; however, the tag() function may be referenced through any event that you may want to track, such as an on(press), on(rollover), on(rollout), or on(keypress) event.

   The [!DNL [PUT_PAGE_NAME_HERE]] placeholder should be replaced with a string that represents the name of the page or event that you are tracking. The [!DNL [PUT_PAGE_NAME_HERE]]variable can be modified either manually or through variable reference to denote a unique name for the page or event within the [!DNL Flash] application. The value replacing the [!DNL [PUT_PAGE_NAME_HERE]] placeholder may consist of a simple name or may be structured to represent a hierarchical structure similar to a full URI. For example:

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe recommends that, prior to code deployment, you compile a written specification for page names and event names to facilitate the alignment of business requirements and development tasks and reduce the potential for additional development cycles. 

1. If desired, additional variables may be collected and associated with pages or events in the [!DNL Flash] movie. To do so, replace the [!DNL [PUT_ADDITIONAL_VAR_HERE]] placeholder with a set of name=value pairs separated by an ampersand (&). For example:

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   The variables can be modified either manually or through variable reference to denote additional attributes to be collected and associated with the page or event. If there are no applicable additional variables to collect, remove [!DNL [PUT_ADDITIONAL_VAR_HERE]].

   Your setup of visitor tracking within [!DNL Flash] rich media content is now complete. When the event is invoked, the tag [!DNL (PAGENAME,VARIABLES)] function will be called, resulting in an HTTP request being made for the following file. This function will be called in addition to other functions that may be triggered as defined within your [!DNL Flash] movie:

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

The HTTP request resulting from the [!DNL Flash] Tag ActionScript function results in the following information being collected with respect to each event within the [!DNL Flash] movie. The last row in the table (W3C Name cs-uri-query) represents the information collected for the additional variables specified in your function call.

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> W3C Name </th> 
   <th colname="col2" class="entry"> Data Collected </th> 
   <th colname="col3" class="entry"> Explanation </th> 
   <th colname="col4" class="entry"> Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> Tracking Identifier (unique visitor) </td> 
   <td colname="col3"> Identifier read from a cookie placed in the user’s browser by <span class="wintitle"> Sensor </span> on Visitor’s initial request </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Date </p> <p>Time </p> </td> 
   <td colname="col2"> Timestamp </td> 
   <td colname="col3"> Time at which request was processed by server (at 100ns precision; accuracy depends on server environment and NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> sc(content-Type) </td> 
   <td colname="col2"> Content Type </td> 
   <td colname="col3"> Type of object returned from server </td> 
   <td colname="col4"> Text/html </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP Response Status Code </td> 
   <td colname="col3"> Numerical code generated by the server that notes the status of the HTTP server's response </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> The stem portion of the URI requested by the client </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> Client IP </td> 
   <td colname="col3"> IP Address of the requesting client </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> Server Domain Name </td> 
   <td colname="col3"> Domain name of the web server processing the request </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> Referring URL </td> 
   <td colname="col3"> Contents of the HTTP referrer field sent by the client </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> User Agent </td> 
   <td colname="col3"> Device used to make a request to the HTTP server </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0; +Windows+NT+5.1) </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> Client Cookies from Domain </td> 
   <td colname="col3"> Contents of all of the user’s cookies for the site </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> Query String </td> 
   <td colname="col3"> The query string portion, if any, of the URI requested by the client </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

