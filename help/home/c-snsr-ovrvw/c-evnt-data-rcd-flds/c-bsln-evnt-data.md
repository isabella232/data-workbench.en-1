---
description: Information about baseline event data record fields as recorded by Sensor.
seo-description: Information about baseline event data record fields as recorded by Sensor.
seo-title: Baseline Event Data Record Fields
solution: Insight
title: Baseline Event Data Record Fields
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
index: y
internal: n
snippet: y
---

# Baseline Event Data Record Fields{#baseline-event-data-record-fields}

Information about baseline event data record fields as recorded by Sensor.

<table id="table_E29606BB010E4DB48C463979B7BEC769"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>The IP address of the client as included in the request made to the server. </p> <p>Example: 207.68.146.68 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>The cookies sent by the client with the request. </p> <p>Example: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>The HTTP referrer string sent by the client to the server with the request. </p> <p>Example: http://www.mysite.net/cgi-bin/websearch?qry </p> <p>If you are using page tags, the cs(referrer) is the full URL of the document containing the tag image, including HTTP or HTTPs. </p> <p>Also, you can configure Apache (1.3, 2.0, and 2.2) and IIS sensors to capture the port that is used for the request, which can identify HTTP vs. HTTPS requests. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>The string sent by the client with its request to the server that indicates what type of user agent the client is. </p> <p>Example: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>The method type of the HTTP request </p> <p>Example: GET </p> <p>Reference: http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>The query string portion of URI (stem + query string = URI) </p> <p>This is preceded by a question mark (?) and may contain one or more name-value pairs separated by ampersands (&amp;). </p> <p>Example: page=homepage </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>The stem portion of URI (stem + query string = URI) </p> <p>The stem is the actual or logical path to the requested resource on the server. </p> <p>Example: /index.asp </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>The content type of the resource being requested by the client as reported by the server. </p> <p>Examples: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>The number of bytes of data sent from the server to the client in response to the request. </p> <p>Example: 4996 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>The status code returned to the client by the server. </p> <p>Example: 200 </p> <p>Reference: http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>The fully qualified domain name or IP address of the host of the requested resource. </p> <p>Example: www.omniture.com </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>The list of all the controlled experiment names and groups that the client is a member of at the time of the request. </p> <p>Example: Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>The date and time (GMT) at which the request was received by the server. </p> <p>The time is expressed as the number of 100 nanoseconds since January 1, 1600. </p> <p>Example: 127710989320000000 would be the x-timestamp value for 11:28:52.0000000 on Tuesday, September 13, 2005. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>The 64-bit, hexadecimal value of the unique browser identifier found in a persistent cookie as set by a <span class="wintitle"> Sensor </span> and provided by the client with a request to a server. </p> <p>Example: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL data workbench server] can derive a number of variables from the baseline event data record fields. For more information, see the *Dataset Configuration Guide*. 
