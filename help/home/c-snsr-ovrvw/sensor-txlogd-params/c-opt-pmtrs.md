---
description: Information about optional Sensor txlogd.conf file parameters.
title: Optional Parameters
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
---
# Optional Parameters{#optional-parameters}

Information about optional Sensor txlogd.conf file parameters.

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>Enables you to filter specified IP addresses. </p> <p>When you filter a particular address, a “packet” is not logged. This feature eliminates internal or monitored agents before log processing, thereby increasing the speed of log processing and reducing data storage requirements. You can use wildcards when specifying addresses. </p> <p>Example: <span class="filepath"> AddressFilter 10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>Specify whether to include or exclude certain types of content from logging. </p> <p>The parameter values are prefix-matched against the content type of the reply. </p> <p>For example, “image/” matches all image content types while “image/gif” matches only that type exactly. When multiple matches occur for a given content-type, the most specific match is used. Therefore, you could put “image/gif” in the ContentFilterInclude parameter and “image/” in the ContentFilterExclude parameter and “image/gif” replies are allowed but all other image types are filtered out. </p> <p>Example: <span class="filepath"> ContentFilterInclude *</span> </p> <p>Example: <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Enables debug logging for the web module and transmitter. </p> <p>You use this parameter when the <span class="wintitle"> Sensor</span> is not working correctly. After this parameter is set, you must create an empty file at the specified path location and give “write” rights to it for all users. For example (inside a unix shell on the web server): 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>You should enable debug logging for only a short period of time, after which the log file should be sent to Adobe Consulting Services to be analyzed. </p> <p>Example: <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe recommends that this parameter first be set in a test environment to determine the effect on your system. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>Disables the specified field </p> <p>Users can eliminate fields they do not use or do not want to store. If the field takes string values, disabling it passes a blank string. If the field takes numeric values, disabling it passes the number zero (0). You can disable the following fields: 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experiment </li> 
     </ul> </p> <p>Example: <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>Path to the Controlled Experiment configuration file. </p> <p>Example: <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>Resource that, when requested, causes a new tracking ID to be generated and the user to be placed in an experiment group. </p> <p> <p>Note:  This resource does not have to physically exist on the web server. </p> </p> <p>Example: <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>If you want to enable your controlled experiments to remap your entire site or an entire subdirectory of your site to another location, set this parameter to “on.” The default is “off.” </p> <p>Example: <span class="filepath"> ExpPartialMatch off</span> </p> <p> <p>Note:  Be very careful when setting this parameter to “on.” </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>Determines whether every new user’s first click is logged even if the user requests a document type that is filtered out by the ContentFilterExclude parameter. </p> <p>The default is “no.” </p> <p>Typically image files are filtered out by the ContentFilterExclude parameter. If LogAllNewUsers is set to “yes” and the very first document a new user gets from the server is an image, that request is logged. If the LogAllNewUsers parameter is either set to “no” or not set at all (and assuming that images are filtered out by the ContentFilterExclude parameter) and the very first document a new user gets from the server is an image, that request is not logged. </p> <p>Example: <span class="filepath"> LogAllNewUsers no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>The amount of time in seconds that the transmitter waits to send the next batch of packets. </p> <p>The default is 15. </p> <p>Example: <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>Note:  Do not change this parameter value without first contacting Adobe Consulting Services. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>Enables you to disable visitor tracking, which can be used to comply with opt-out policies. </p> <p>When enabled, <span class="wintitle"> Sensor</span> does not log a “packet” for any visitor whose V1st cookie is set to the PrivacyID specified. Because no information is logged for those visitors, no information about those visitors is sent to the <span class="keyword"> data workbench server</span> for processing. </p> <p>To enable this feature, you must complete the following steps: 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID must be defined with a value of 0 (zero) in the <span class="filepath"> txlogd.conf</span> file for the <span class="wintitle"> Sensor</span>. <p>Example: <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">Website owners must write code to set visitor (V1st) cookies such that the cookie ID value matches the PrivacyID value defined “<span class="filepath"> txlogd.conf</span>." </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>Location to which the transmitter (txlogd) periodically sends requests to see if the website is operating correctly. </p> <p>Note that the location is specified in the following format, not as a URL: </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>where <i>serverAddress</i> is server name or IP address, <i>port</i> is server’s HTTP listening port, and <i>resource</i> is the specific resource to request (can include a query string). </p> <p>You can specify multiple SiteTest lines. </p> <p>Example: <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>Note:  Only http is supported at this time. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>The name of the cookie set on the visitor’s browser. </p> <p>The default is “v1st.” </p> <p>Example: <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>Indicates whether to validate the server against CertName parameter </p> <p>The default is “on.” </p> <p>Example: <span class="filepath"> VerifyCertName on</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Tells the IIS <span class="wintitle"> Sensor</span> which of two possible logging “hooks” should be used to log a packet </p> <p>Use this parameter when the IIS <span class="wintitle"> Sensor</span> is not logging packets correctly. This parameter would be set to “off” if the default logging hook was not working correctly. The default is “on.” </p> <p>Example: <span class="filepath"> IISCaptureBytesSent on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Tells the <span class="wintitle"> Sensor</span> which of two possible “hooks” should be used to set the v1st cookie. </p> <p>You use this parameter when the IIS <span class="wintitle"> Sensor</span> is not setting the v1st cookie correctly. This parameter would be set to “yes” if the default hook was not correctly setting the v1st cookie. The default is “no.” </p> <p>Example: <span class="filepath"> IISUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>By default, <span class="wintitle"> Sensor</span> sends cache control response headers on each request. When the cache control feature is enabled <span class="wintitle"> Sensor</span> sends an Expires header with a value of Thu, 01 Dec 1994 16:00:00 GMT to the browser. </p> <p>You can modify the response strings as desired by editing the following two lines in the <span class="filepath"> txlogd.conf</span> file: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Example: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>To disable the sending of cache control response headers, type a hyphen for each line as shown below: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In this Parameter... </th> 
   <th colname="col2" class="entry"> Specify... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Tells the <span class="wintitle"> Sensor</span> which of two possible “hooks” should be used to set the v1st cookie. </p> <p>You use this parameter when the Apache <span class="wintitle"> Sensor</span> is not setting the v1st cookie correctly. This parameter would be set to “yes” if the default hook was not correctly setting the v1st cookie. The default is “no.” </p> <p>Example: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Instructs the <span class="wintitle"> Sensor</span> to try setting the v1st cookie in both hooks. </p> <p>You use this parameter when the Apache <span class="wintitle"> Sensor</span> is not setting the v1st cookie correctly. The default is “yes.” </p> <p>If set to “yes” and the v1st cookie is not properly set in the first hook, the second hook is used. If set to “no,” you would set the ApacheUseAlternateHandler parameter to indicate which hook to use to set the v1st cookie. </p> <p>Example: <span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>By default, <span class="wintitle"> Sensor</span> sends cache control response headers on each request. When the cache control feature is enabled <span class="wintitle"> Sensor</span> sends an Expires header with a value of Thu, 01 Dec 1994 16:00:00 GMT to the browser. </p> <p>You can modify the response strings as desired by editing the following two lines in the <span class="filepath"> txlogd.conf</span> file: </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>Example: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl private,max-age=0,must-revalidate</span> </p> <p>To disable the sending of cache control response headers, type a hyphen for each line as shown below: </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>Note:  Adobe recommends that you do not disable this feature. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In this Parameter... </th> 
   <th colname="col2" class="entry"> Specify... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Tells the <span class="wintitle"> Sensor</span> which of two possible “hooks” should be used to set the v1st cookie. </p> <p>You use this parameter when the Apache <span class="wintitle"> Sensor</span> is not setting the v1st cookie correctly. This parameter would be set to “yes” if the default hook was not correctly setting the v1st cookie. The default is “no.” </p> <p>Example: <span class="filepath"> ApacheUseAlternateHandler no</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>Set this parameter only when working with Adobe Consulting Services. </p> <p>Instructs the <span class="wintitle"> Sensor</span> to try setting the v1st cookie in both hooks. </p> <p>You use this parameter when the Apache <span class="wintitle"> Sensor</span> is not setting the v1st cookie correctly. The default is “yes.” </p> <p>If set to “yes” and the v1st cookie is not properly set in the first hook, the second hook is used. If set to “no,” you would set the ApacheUseAlternateHandler parameter to indicate which hook to use to set the v1st cookie. </p> <p>Example: <span class="filepath"> ApacheUseBothHandlers yes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
