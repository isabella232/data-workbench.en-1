---
description: After the HTML of a page is requested by a browser, the browser requests the embedded objects referenced in the HTML of that page from a web server to fill in the page shown by the browser.
title: Acquiring Embedded Object Requests (Page Tags)
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
---
# Acquiring Embedded Object Requests (Page Tags){#acquiring-embedded-object-requests-page-tags}

After the HTML of a page is requested by a browser, the browser requests the embedded objects referenced in the HTML of that page from a web server to fill in the page shown by the browser.

Such embedded object requests are most commonly requests for image files or JavaScript files, though there are hundreds or maybe thousands of types of embedded objects used on the Internet today. Many of these embedded object requests are not generally useful in analyzing or reporting on the business activity of an Internet site; many such requests are therefore not desirable for acquisition unless they have a specific business purpose, such as presenting an advertisement or taking another measurement of site activity.

For example, an image may be an advertisement, and you may want to know that the advertisement was impressed upon a visitor. A JavaScript snippet may be in use to take a measurement that the particular browser has a certain characteristic and pass it back to a [!DNL Sensor] for acquisition. Each page on a site may have 10 or 100 embedded object requests in it. If a site stores the log information for each of these requests, the amount of data storage needed to keep the log data available for future analysis is multiplied by the number of embedded object requests for each page requested. For this reason, [!DNL Site] lets you keep the requests that are important for analysis and discard others before you incur unnecessary storage costs.

By using the override feature provided in the content-type filtering capabilities of [!DNL Sensor] (appending “Log=1” to the query string of an embedded object request URL), that particular embedded object request and the related measurement data can be acquired without requiring the site manager to store all requests of that type (for example, all `<image>` requests).

[!DNL Sensor] collects the measurement data in the following table for each embedded object request made of the web server, assuming that [!DNL Sensor] is not configured to filter it out or that the filter has been overridden. The collected information is related to the visitor and session and subsequent sessions through the x-trackingid or cs(cookie) log field entries.

<table id="table_11BE08A798E743EC8E76F738F0CE5884">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C Name </th>
   <th colname="col2" class="entry"> Data Collected </th>
   <th colname="col3" class="entry"> Explanation </th>
   <th colname="col4" class="entry"> Example </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> Tracking Identifier (unique visitor) </td>
   <td colname="col3"> Identifier read from a cookie placed in the user’s browser by <span class="wintitle"> Sensor </span> on initial request </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Date </p> <p>Time </p> </td>
   <td colname="col2"> Timestamp </td>
   <td colname="col3"> Time at which request was processed by server (at 100ns precision; accuracy depends on server environment and NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-Type) </td>
   <td colname="col2"> Content Type </td>
   <td colname="col3"> Type of object returned from server </td>
   <td colname="col4"> text/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> HTTP Response Status Code </td>
   <td colname="col3"> Numerical code generated by the server that notes the status of the HTTP server's response </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI Stem </td>
   <td colname="col3"> The “stem” portion of the URI requested by the client </td>
   <td colname="col4"> pagedir/page.asp </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> Client IP </td>
   <td colname="col3"> IP Address of the requesting client </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> Server Domain Name </td>
   <td colname="col3"> Domain name of the web server processing the request </td>
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> Referring URL </td>
   <td colname="col3"> Contents of the HTTP referrer field sent by the client </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> User Agent </td>
   <td colname="col3"> Device used to make a request to the HTTP server </td>
   <td colname="col4"> <p>Mozilla/4.0+(compatible;+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> Client Cookies from Domain </td>
   <td colname="col3"> Contents of all of the user’s cookies for the site </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> Query String </td>
   <td colname="col3"> The query string portion, if any, of the URI requested by the client </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
