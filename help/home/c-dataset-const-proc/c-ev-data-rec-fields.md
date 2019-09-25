---
description: Information about the fields of data that the data workbench server can process to construct a dataset.
seo-description: Information about the fields of data that the data workbench server can process to construct a dataset.
seo-title: Event Data Record Fields
solution: Analytics
title: Event Data Record Fields
topic: Data workbench
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
---

# Event Data Record Fields{#event-data-record-fields}

Information about the fields of data that the data workbench server can process to construct a dataset.

* [About Event Data](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe) 
* [Baseline Event Data Record Fields](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7) 
* [Derived Fields](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## About Event Data {#section-3a0705f8c1824017aa4effed9903efbe}

The event data used to build a dataset resides in files referred to as log sources. The data available in the log sources is called event data because each data record represents a transaction record or a single instance of an event with an associated timestamp.

A log source's event data is collected in real-time by [!DNL Sensors]. Event data collected by [!DNL Sensors] from HTTP and application servers is transmitted to data workbench servers, which convert the data into compressed log ( [!DNL .vsl]) files. Event data that resides in a flat file, XML file, or an ODBC data source is read by the data workbench server, which provides decoders that you define to extract a common set of data fields from these different formats.

The following sections provide information about the data fields (referred to as event data record fields or log entry fields ) that are collected by [!DNL Sensors] or read and made available to the data workbench server.

>[!NOTE]
>
>The names of the fields generally follow the naming convention for the W3C extended log file format. Many of the fields have prefixes that indicate the source of the information contained in the field:

* cs indicates communication from the client to the server. 
* sc indicates communication from the server to the client. 
* s indicates information from the server. 
* c indicates information from the client. 
* x indicates information that is created by an Adobe software product.

## Baseline Event Data Record Fields {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

Log ( [!DNL .vsl]) files contain the fields of event data that are collected from servers by [!DNL Sensors] and used by the data workbench server in the dataset construction process. The following table lists the fields in a typical event data record as recorded by [!DNL Sensor]: 

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>The IP address of the client as included in the request made to the server. </p> <p> Example: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>The cookies sent by the client with the request. </p> <p> Example: v1st=42FDF66DE610CF36; ASPSESSIONIDQCATDAQC=GPIBKEIBFBFIPLOJMKCAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>The HTTP referrer string sent by the client to the server with the request. </p> <p> Example: <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>The string sent by the client with its request to the server that indicates what type of user agent the client is. </p> <p> Example: Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>The method type of the HTTP request. </p> <p> Example: GET </p> <p> Reference: <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>The query string portion of URI (stem + query string = URI). This is preceded by a question mark (?) and may contain one or more name-value pairs separated by ampersands (&amp;). </p> <p> Example: page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>The stem portion of URI (stem + query string = URI). The stem is the actual or logical path to the requested resource on the server. </p> <p> Example: <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>The content type of the resource being requested by the client as reported by the server. </p> <p> Examples: text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>The number of bytes of data sent from the server to the client in response to the request </p> <p> Example: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>The status code returned to the client by the server. </p> <p> Example: 200 </p> <p> Reference: <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>The fully qualified domain name or IP address of the host of the requested resource. </p> <p> Example: <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experiment </td> 
   <td colname="col2"> <p>The list of all the controlled experiment names and groups that the client is a member of at the time of the request. </p> <p> Example: VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>The date and time (GMT) at which the request was received by the server. The time is expressed as the number of 100 nanoseconds since January 1, 1600. </p> <p> Example: 127710989320000000 would be the x-timestamp value for 11:28:52.0000000 on Tuesday, September 13, 2005. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>The 64-bit, hexadecimal value of the unique browser identifier found in a persistent cookie as set by a <span class="wintitle"> Sensor </span> and provided by the client with a request to a server. </p> <p> Example: 42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Derived Fields {#section-b6c57ee2aa31469fbd5dab90e52bc677}

The table below lists examples of fields that are derived by the data workbench server from the baseline event data record fields: 

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> The value of a given name-value pair within a cookie. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>The domain name or IP address of the HTTP referring URI. </p> <p> <p>Note:  This field is read-only. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>The entire hostname of the referrer. </p> <p> Example: If cs(referrer) is <span class="filepath"> http://my.domain.com/my/page </span>, cs(referrer-host) is <span class="filepath"> my.domain.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>The value of a referrer query string. </p> <p> <p>Note:  You cannot access a referrer query string value using the cs(referrer)(name) field. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>The complete URI (stem + query string = entire URI). </p> <p> Example: <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>The value associated with the given name. If multiple values exist for the given name, this field returns the last of those values. </p> Examples: 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> For the URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3) would return cd. </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> For the URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1) </span> would return casette. </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp expressed as seconds since January 1, 1970. This field is also called x-unixtime. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> x-timestamp in the format YYYY-MM-DD. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> time </td> 
   <td colname="col2"> x-timestamp in the format HH:MM:SS. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp converted to the local timezone that is specified in the <span class="filepath"> Transformation.cfg </span> file for the dataset. The format is YYYY-MM-DD HH:MM:SS.mmm. </p> <p> <p>Note:  You also can define time conversions such as x-local-timestring in the <span class="filepath"> Log Processing.cfg </span> file. For information, see <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-proc-config-file.md#concept-20e3148be47841a1b33ae55d23667d33" format="dita" scope="local"> Log Processing Configuration File </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>The identifier corresponding to the log source for a particular log entry. For the identifier to be recorded, you must specify it in the <span class="wintitle"> Log Source ID </span> field of the <span class="filepath"> Log Processing.cfg </span> file when defining <span class="wintitle"> Sensor </span>, log file, or ODBC data sources. For more information, see <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-proc-config-file.md#concept-20e3148be47841a1b33ae55d23667d33" format="dita" scope="local"> Log Processing Configuration File </a>. </p> <p> Example: from VSensor01. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> The mask pattern of the <span class="wintitle"> Sensor </span> data sources (derived from the <span class="filepath"> .vsl </span> file names). For a file whose name is of the format <span class="filepath"> YYYYMMDD-SENSORID.VSL </span>, x-mask is SENSORID. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> x-timestamp in the format YYYY-MM-DD HH:MM:SS.mmm. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> The decimal UNIX time derived from x-timestamp. </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor], when used on a server, can collect fields of event data from any valid HTTP request or response header or variable available to it through the server's API. To collect such fields of data, you must specify the desired header fields or variables in the [!DNL txlogd.conf]configuration file for [!DNL Sensor]. For more information, see the *Data Workbench [!DNL Sensor] Guide*. 
