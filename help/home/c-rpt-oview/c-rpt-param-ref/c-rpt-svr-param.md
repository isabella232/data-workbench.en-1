---
description: Information about Report Server.cfg parameters.
seo-description: Information about Report Server.cfg parameters.
seo-title: Report Server.cfg Parameters
solution: Analytics
title: Report Server.cfg Parameters
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
index: y
internal: n
snippet: y
---

# Report Server.cfg Parameters{#report-server-cfg-parameters}

Information about Report Server.cfg parameters.

The sample [!DNL Report Server.cfg] shown in [Configuring the Connection to Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contains only the parameters included in the [!DNL Report Server.cfg] file by default.

If you contact the Adobe License Server through a proxy server, you need to add the Licensing vector and its parameters to the [!DNL Report Server.cfg]. Following is an example of this vector and its parameters that you can use a model for your Licensing vector: 

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 

```

The following table provides descriptions of the [!DNL Report Server.cfg] file parameters:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Excel Extension </td> 
   <td colname="col2"> <p>Supported Excel extensions include: </p> <p>Excel Extension = string: <span class="filepath"> .xlsx </span> </p> <p>Excel Extension = string: <span class="filepath"> .xls </span> (this is default) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Fonts </td> 
   <td colname="col2"> <p>Optional. Vector listing the fonts that <span class="keyword"> Report Server </span> should use to render UTF8-based unicode special characters. The number of fonts in the list is unlimited. </p> <p>The first font should always be Lucida Sans Console. If this parameter is not included in the <span class="filepath"> Report Server.cfg </span> file, <span class="keyword"> Report Server </span> uses only Lucida Sans console to display text. </p> <p> <span class="keyword"> Report Server </span> uses the first font in the list to render all characters until it encounters a character that it cannot render. It then uses the second font in the list to render that character. If that font does not render the character, <span class="keyword"> Report Server </span> uses the third font in the list to render that character, and so on, until it reaches the end of the font list. If the correct font is not listed in the vector, <span class="keyword"> Report Server </span> displays the hexidecimal value for the character. </p> <p> <p>Note:  Do not make changes to this parameter while <span class="keyword"> Report Server </span> is running. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma </span> setting for <span class="filepath"> .png </span> file output. The default value is 1.6. </p> <p> <p>Note:  Adobe does not recommend changing this value. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Licensing </td> 
   <td colname="col2"> <p>Optional. You need to modify the parameters in this vector only if you contact Adobe's license server through a proxy server. </p> <p>Section identifier for parameters you set to contact Adobe's license server through a proxy server. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> The address of a proxy server that <span class="keyword"> Report Server </span> must use to access Adobe's license server. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> Optional. The password associated with the <span class="wintitle"> Proxy User Name </span>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> The port of the proxy server. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> Optional. The user name used to access the proxy server. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Network Location </td> 
   <td colname="col2"> The network location that <span class="keyword"> Report Server </span> uses to resolve the server's common name to an IP address. Network locations are defined in the address file located in the Addresses directory on the data workbench server machine. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Servers </td> 
   <td colname="col2"> <p>Section identifier for parameters you set to configure which data workbench server machines <span class="keyword"> Report Server </span> must connect to generate reports. This includes a number indicating how many items are listed in this vector. </p> <p>For each server, add a serverInfo entry and complete the parameters as necessary. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Address </td> 
   <td colname="col2"> IP address of the data workbench server machine to which <span class="keyword"> Report Server </span> must connect to generate reports. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> The name that <span class="keyword"> Report Server </span> uses internally to identify the data workbench server. This is simply an internal label, so you can use any name you like. For consistency, we suggest that you use the common name as listed on the server's digital certificate. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> Port through which <span class="keyword"> Report Server </span> communicates with the data workbench server. For secure connections, this value is usually 443. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Address </td> 
   <td colname="col2"> The address of a proxy server that <span class="keyword"> Report Server </span> must use to access the data workbench server. This parameter is needed only when a proxy server is required to connect to your server machines. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Password </td> 
   <td colname="col2"> The password to the proxy server. This parameter is needed only when a proxy server is required to connect to your data workbench server machines. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy Port </td> 
   <td colname="col2"> The port of the proxy server. The default value is 8080. This parameter is needed only when a proxy server is required to connect to your data workbench server machines. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Proxy User Name </td> 
   <td colname="col2"> The user name to the proxy server. This parameter is needed only when a proxy server is required to connect to your data workbench server machines. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SSL Client Certificate </td> 
   <td colname="col2"> Name of the SSL certificate file for the <span class="keyword"> Report Server </span> machine. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SSL Server Common Name </td> 
   <td colname="col2"> <span class="wintitle"> Server Common Name </span> listed on data workbench server's digital certificate. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Use SSL </td> 
   <td colname="col2"> Indicates whether SSL is used for secure communication between the data workbench server and <span class="keyword"> Report Server </span>. The options are true or false. The default value is true. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Result Memory Limit (KB) </td> 
   <td colname="col2"> <p>The amount of memory (in KB) that you want to make available for reports and alerts. The default value is 50000. </p> <p>When running reports, <span class="keyword"> Report Server </span> checks this value first, then checks the value in the Maximum Slice Size parameter. For example, if you set this parameter to 50,000 and the Maximum Slice Size to 50, <span class="keyword"> Report Server </span> runs only 50 workspaces at a time even if space is available to run more workspaces. </p> <p> <p>Note:  This limit should never exceed the value set in the data workbench server's Query Memory Limit parameter, and, ideally, should be set a little lower than the <span class="wintitle"> Query Memory Limit </span> to provide some leeway to other users who may be running reports at the same time. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Maximum Slice Size </td> 
   <td colname="col2"> The maximum number of report workspaces that <span class="keyword"> Report Server </span> can run at one time. The default value is 50. For more information about how <span class="keyword"> Report Server </span> uses this setting, see the <span class="wintitle"> Result Memory Limit (KB) </span> parameter description. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Update Software </td> 
   <td colname="col2"> <p>Indicates whether to allow this <span class="keyword"> Report Server's </span> software to be updated by the data workbench server. The options are true or false. The default value is true. </p> <p>Following is an example of this parameter that you can use a model: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Use OpenGL Hardware Rendering </td> 
   <td colname="col2"> <p>Controls whether <span class="keyword"> Report Server </span> uses hardware rendering (such as the machine's graphics card) to produce report output. The options are true or false. The default value is true. </p> <p>This parameter should be set to false only when you are experiencing problems with your graphics card. When set to false, <span class="keyword"> Report Server </span> does not attempt to use hardware rendering and uses software rendering by default. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Reporting </td> 
   <td colname="col2"> Section identifier for parameters you set to configure reporting. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Completion Message Interval </td> 
   <td colname="col2"> <p>The frequency (in seconds) with which <span class="keyword"> Report Server </span> prints completion status messages when queries are being run during report or alert generation. The default value is 120 seconds. </p> <p>Example: Workspace queries are 62.145672% complete. </p> <p>Completion messages are written to the <span class="filepath"> reportserver.log </span> and are synched to the server. This setting controls the <span class="filepath"> status.txt </span> files that are sent back and forth for each report set, so that the percent complete can be shown with thumbnails. The messages are sent whenever a report set completes or when the interval is reached, whichever comes first. Setting this higher does not effect the rate at which you see report generated in the client interface by the thumbnails, but does effect how many interim messages you see. Specifying a low value can cause the system to spend a large amount of time synchronizing data, because data is synched from <span class="keyword"> Report Server </span> server to the profile, across all the DPUs and to all connected clients each time a <span class="filepath"> status.txt </span> message changes. </p> <p>The system always sends a <span class="filepath"> status.txt </span> file when a report set completes, regardless of the setting of this configuration parameter. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Profiles </td> 
   <td colname="col2"> <p>Number indicating how many items are listed in this vector. For each profile for which reports are to be created, add a <span class="wintitle"> ReportProfile </span> entry in the Profiles vector and complete the Server and Profile parameters. </p> <p> <span class="wintitle"> Server </span> - The name which <span class="keyword"> Report Server </span> uses internally to identify the data workbench server. This name must be the server common name listed on data workbench server's SSL certificate. </p> <p> <span class="wintitle"> Profile </span> - Name of the profile for which reports are to be created. This name must match the named profile on the data workbench server machine. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SMTP Server for Errors </td> 
   <td colname="col2"> <p>The address of the SMTP server from which you want to send <span class="wintitle"> Report Server </span> errors via email. </p> <p>Example: <span class="filepath"> mail.mycompany.com </span> </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SMTP Server for Errors Password </td> 
   <td colname="col2"> <p>The password for logging in to SMTP server. This parameter is optional unless login is required to send mail. </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SMTP Server for Errors Send From </td> 
   <td colname="col2"> The email address from which you want to send <span class="wintitle"> Report Server </span> errors. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SMTP Server for Errors Send To </td> 
   <td colname="col2"> <p>The email address(es) to which alerts are sent. </p> <p>Example: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SMTP Server for Errors Username </td> 
   <td colname="col2"> <p>The user name for logging in to the SMTP server. This parameter is optional unless login is required to send mail. </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Status Interval </td> 
   <td colname="col2"> <p>The frequency (in seconds) with which <span class="wintitle"> Report Server </span> generates and sends status information to data workbench server to be displayed in <span class="wintitle"> Detailed Status </span>. </p> <p>The default value is 120 seconds. It is not recommended to set this to a small value, such as two minutes, because a reporting queue can take hours to run. In that case, you might consider a setting of 600 to 1200 seconds. </p> <p>For more information about <span class="wintitle"> Detailed Status </span>, see the Administrative Interfaces chapter of the <a href="http://marketing.adobe.com/resources/pdf/en/insight/insight_user_guide_client.pdf" format="http" scope="external"> Insight User Guide </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Update Interval </td> 
   <td colname="col2"> <p>The frequency (in minutes) with which <span class="keyword"> Report Server </span> monitors all of the profiles listed in the Profiles vector for new reports and alerts. The default value is 10 minutes. </p> <p>The time that you specify is divided among all of the profiles listed. For example, if your interval is set to 10 minutes and you are monitoring two profiles, each profile is monitored for 5 minutes. If a profile is being monitored when a new or modified report or alert is saved to the profile, the report or alert is immediately available for generation. </p> <p>If the <span class="wintitle"> Update Interval </span> is configured to monitor more than one profile, it is important that this setting is high enough to load all profiles within the configured time. In systems with many large dimensions configured, for example, where it might take several minutes to retrieve the initial data connection with all the element names, this setting must be long enough for that full synchronization to occur. Otherwise, the system issues a profile synch error. </p> </td> 
  </tr> 
 </tbody> 
</table>

