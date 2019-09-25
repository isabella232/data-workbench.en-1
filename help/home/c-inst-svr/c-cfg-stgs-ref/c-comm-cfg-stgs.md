---
description: Instructions to configure communications for Insight Server or Repeater.
seo-description: Instructions to configure communications for Insight Server or Repeater.
seo-title: Communications Configuration Settings
solution: Insight
title: Communications Configuration Settings
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
---

# Communications Configuration Settings{#communications-configuration-settings}

Instructions to configure communications for Insight Server or Repeater.

Complete the parameters in the following file:

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>Before modifying any parameters not listed in this table, please contact Adobe.

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <desc> 
  <b>Communications Configuration Settings </b> 
 </desc> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Access Control File </td> 
   <td colname="col2"> <p>Location of the <span class="filepath"> Access Control.cfg </span> file. The default location is the <span class="filepath"> Access Control </span> folder within the <span class="keyword"> Insight Server </span> or <span class="wintitle"> Repeater </span> installation directory. </p> <p>Example: <code> 
      <filepath>
        Access&nbsp;Control&nbsp;File&nbsp;=&nbsp;Path:&nbsp;Access&nbsp;Control\\Access 
       &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Control.cfg 
      </filepath> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Access Log Directory </td> 
   <td colname="col2"> <p>Folder to which you want to map the audit logs. </p> <p>Example: <code> 
      <filepath>
        Access&amp;nbsp;Log&amp;nbsp;Directory&amp;nbsp;=&amp;nbsp;string:&amp;nbsp;Audit\\ 
      </filepath> </code> </p> <p> <p>Note:  You can map audit logs to another local drive (example: <span class="filepath"> string: P:\\Audit\\ </span>), but do not map audit logs to a network drive. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Access Log Verbose </td> 
   <td colname="col2"> This parameter can be set to true or false. It is used to enable and disable audit log filtering. To ensure that every request is logged, set the parameter to True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP Interface </td> 
   <td colname="col2"> <p>IP address to use when two network cards are available for accessing two different networks. </p> <p>Example: I <code> 
      <filepath>
        P&amp;nbsp;Interface&amp;nbsp;=&amp;nbsp;string: 
      </filepath> </code><i>&lt; <span class="filepath"> IP Address </span>&gt;</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Port </td> 
   <td colname="col2"> <p>Non-secure (HTTP) port on which the <span class="keyword"> Insight Server </span> or <span class="wintitle"> Repeater </span> listens. The default port is 80. Entering a value of 0 disables non-secure connections. </p> <p>Example: <code> 
      <filepath>
        Port&amp;nbsp;=&amp;nbsp;int:&amp;nbsp;80 
      </filepath> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Ciphers </td> 
   <td colname="col2"> Some environments require stronger communication security than others. If you want to use a specific SSL cipher suite, you can specify it with this parameter. <p>Example: <code> 
      <filepath>
        SSL&amp;nbsp;Ciphers&amp;nbsp;=&amp;nbsp;string:&amp;nbsp;AES256-SHA256 
      </filepath> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL Port </td> 
   <td colname="col2"> <p>Secure (via SSL) port on which the <span class="keyword"> Insight Server </span> or <span class="wintitle"> Repeater </span> listens. The default port is 443. Entering a value of 0 disables secure connections. </p> <p>Example: <span class="filepath"></span> </p> <code> 
     <filepath>
       SSL&amp;nbsp;Port&amp;nbsp;=&amp;nbsp;int:&amp;nbsp;443 
     </filepath> </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> Heading for Logging Server settings. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Customer Name </td> 
   <td colname="col2"> <p>Customer name to appear for Unspecified customers in administrative alerts, as in the following example: </p> <p>“No data received from sensor XYZ for customer 'Unspecified' in 15.” </p> <p>Example: <code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>Using the example above, administrative alerts for Unspecified customers would now read as follows: </p> <p>“No data received from sensor XYZ for customer ‘CompanyAB’ in 15.” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string: Logs\\ </p> </td> 
   <td colname="col2"> <p>Folder in which you want to store the log files. </p> <p>Example: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>To be able to access this folder from the <span class="wintitle"> Server Files Manager </span>, the location specified in this parameter must match the location that you specify in the Log Paths parameter in the <span class="filepath"> Log Processing.cfg </span> file. For more information about modifying the Logs directory in the <span class="filepath"> Log Processing.cfg </span> file, see Log Processing Configuration File chapter of the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> Local Path = string: Audit\\ </p> </td> 
   <td colname="col2"> <p>Folder to which you want to map the audit logs. </p> <p>Example: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>Note:  <p>You can map audit logs to another local drive (example: <span class="filepath"> string: P:\\Audit\\ </span>), but do not map audit logs to a network drive. </p> <p>To be able to access this folder from the <span class="wintitle"> Server Files Manager </span>, the location specified in this parameter must match the location that you in the Access Log Directory parameter in this file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>This parameter applies only to <span class="keyword"> Insight Server </span>. </p> <p>For more information about specifying the Centralized Normalization Server for your <span class="keyword"> Insight Server </span> cluster, see Log Processing Configuration File chapter of the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI = string: /ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>This parameter applies only to <span class="keyword"> Insight Server </span>. </p> <p>Enables you to view <span class="keyword"> Report’s </span> status in the Detailed Status interface for <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

