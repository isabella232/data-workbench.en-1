---
description: Instructions to configure administrative alerts for Insight Server, Repeater, or Transform.
seo-description: Instructions to configure administrative alerts for Insight Server, Repeater, or Transform.
seo-title: Administrative Alerts Configuration Settings
solution: Insight
title: Administrative Alerts Configuration Settings
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
---

# Administrative Alerts Configuration Settings{#administrative-alerts-configuration-settings}

Instructions to configure administrative alerts for Insight Server, Repeater, or Transform.

Complete the parameters in the following file:

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Category </td> 
   <td colname="col2"> The name of the category. A category of Default is required. See Error Categories in this table. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Categories </td> 
   <td colname="col2"> Lets you categorize errors in conjunction with the Error Categorization File. Each Error Category can have its own set of Recipients and its own Throttle Delay. For example, you might create a Critical category with a throttle delay of 0, so that every critical error is emailed immediately to the recipients specified in the Recipients list. Errors that do not match a substring in the Error Categorization File are assigned to the Default category. To add a new category, right-click on a number and click <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Error Category </span>. You can also copy or remove them using the right-click action. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Categorization File </td> 
   <td colname="col2"> <p>The name of the file you want to use to categorize each alert. You create this file using Notepad. This file should have three columns on each line, separated by tabs. The first column is a string to match in errors. A ^ sign matches the beginning and a $ matches the end of the string; all other characters are matched literally. The second column is a category for errors that match, which is in Error Categories. The third is an alternate message, which is prepended to the actual error message in emails that are sent. If no file is specified, all errors categorize as Default. </p> <p>To see an example of this file, see the <span class="filepath"> Error Categories.txt </span> file in the Lookups directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> From </td> 
   <td colname="col2"> <p>Address that appears in the “from” parameter of the email message. </p> <p>Example: <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minimum Disk Space (MB) </td> 
   <td colname="col2"> The server generates an email alert when available disk storage in any directory used by the server drops below this value. The default value is 1000. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sensor Alert Timeout (min) </td> 
   <td colname="col2"> <p>The server generates an email alert when it has received no data from a configured and previously connected <span class="wintitle"> Sensor </span> within this time window. The default value is 15. </p> <p> <p>Note:  <span class="wintitle"> Sensor </span> Alert Timeout works only if an existing connection to a <span class="wintitle"> Sensor </span> is dropped. If the server’s service is stopped and restarted and the <span class="wintitle"> Sensors </span> do not connect, the server does not generate email alerts. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server Address </td> 
   <td colname="col2"> <p>The address of the SMTP server for outgoing email. </p> <p>Example: <span class="filepath"> mail.mycompany.com </span></p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server Password </td> 
   <td colname="col2"> <p>The password for logging in to the SMTP server. This parameter is optional unless login is required to send mail. </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server User </td> 
   <td colname="col2"> <p>The user ID/name for logging in to the SMTP server. This parameter is optional unless login is required to send mail. </p> <p>An SMTP server is required for use of the described capabilities. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Throttle Delay (secs) </td> 
   <td colname="col2"> The minimum number of seconds that must elapse between two errors in that category for an email to be sent. A value of 0 sends the email immediately. </td> 
  </tr> 
 </tbody> 
</table>

