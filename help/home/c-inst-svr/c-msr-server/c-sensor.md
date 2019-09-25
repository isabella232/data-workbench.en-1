---
description: Data Workbench Sensor collects event data from web, application, and data collection servers to be transmitted to any server.
seo-description: Data Workbench Sensor collects event data from web, application, and data collection servers to be transmitted to any server.
seo-title: Sensor Requirements
solution: Analytics
title: Sensor Requirements
uuid: 3a4acadd-3725-4652-9776-4fb5035e66d0
---

# Sensor Requirements{#sensor-requirements}

Data Workbench Sensor collects event data from web, application, and data collection servers to be transmitted to any server.

 [!DNL Sensor’s] instrumentation ensures consistently accurate measurement of events that occur in your Internet channel. [!DNL Sensor] supports many combinations of Web server software and operating system.

## Sensor System Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

The following table describes system recommendations for [!DNL Sensor]:

<table id="table_A132E06D6B8146C1B199B82464EA0898"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Features </th> 
   <th colname="col2" class="entry"> Recommended </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Disk Storage </p> </td> 
   <td colname="col2"> <p>512 MB minimum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>32 MB of RAM must be available to <span class="wintitle"> Sensor </span> on the HTTP or other server computer that is its host. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Performance </p> </td> 
   <td colname="col2"> <p>1 Mbps or greater network connection to a repeater server or <span class="keyword"> data workbench server </span>. <span class="wintitle"> Sensor </span> typically consumes far less bandwidth than one (1) Mbps. Your Adobe consultants will help you estimate the actual amount of bandwidth that would be required on a routine basis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Ports and Firewalls </p> </td> 
   <td colname="col2"> <p> <span class="wintitle"> Sensor </span> connects to the <span class="keyword"> data workbench server </span> using HTTPS (typically port 443, though this is configurable) or HTTP (typically port 80, though this is configurable). </p> <p>The appropriate port on any firewall that resides between a <span class="wintitle"> Sensor </span> and the target <span class="keyword"> data workbench server </span> or repeater server should be opened only between the respective <span class="wintitle"> Sensor </span> hosting computer and the <span class="keyword"> data workbench server </span> or repeater server before beginning the <span class="wintitle"> Sensor </span> installation process. <span class="wintitle"> Sensor </span> makes a uni-directional HTTPS or HTTP connection to an <span class="keyword"> data workbench server </span> or repeater server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Management Systems </p> </td> 
   <td colname="col2"> <p>Existing network management systems should monitor the health of the underlying computer hardware (for example, disk space, network service) and network connectivity as well as the Windows Event Log or UNIX syslog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server Time Synchronization </p> </td> 
   <td colname="col2"> <p>Ensure that the computer system time is continuously synchronized across every computer that hosts a <span class="wintitle"> Sensor </span>. The Web server applications and computers that are monitored by <span class="wintitle"> Sensor </span> must have synchronized system times for the event data collected from them to be accurate. Please refer to your operating system's documentation for steps to synchronize system times on an ongoing basis with NTP or other such time synchronization facility. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DNS Name Usage </p> </td> 
   <td colname="col2"> <p>Adobe recommends that <span class="wintitle"> Sensors </span> use a DNS name (instead of an IP address) to resolve the network address of a <span class="keyword"> data workbench server </span> or repeater server. When a <span class="wintitle"> Sensor </span> uses a DNS name, the host web server's DNS or local hosts file needs to be configured to resolve the name of the <span class="keyword"> data workbench server </span> or repeater server. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Support Server Software {#section-d6071706539f49d9a861d87b98e6f382}

The following table lists the most common combinations that [!DNL Sensor] supports: 

<table id="table_99EA23BBC1A148B49643F4B5E4341C08"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Web Server Software </th> 
   <th colname="col2" class="entry"> Operating System </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Apache Server / IBM HTTP Server 2.2 </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 or later; RedHat Enterprise Linux 6.x or later; Sun Solaris 8.x or later; IBM AIX 5.1x or later. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apache Server 2.4 </p> </td> 
   <td colname="col2"> <p>RedHat Enterprise Linux 6.x or later </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Microsoft IIS </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 or later </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Java Application Servers (Tomcat, JBoss, iPlanet, Weblogic) </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2003 or later; RedHat Enterprise Linux 6.x or later; Sun Solaris 8.x or later; IBM AIX 5.1x or later. </p> </td> 
  </tr> 
 </tbody> 
</table>

For other server and operating system combinations, please consult Adobe regarding availability. Not all features of [!DNL Sensor] are available with all combinations of web/application server and operating system. For more information about particular [!DNL Sensor] releases, please contact Adobe Support. 
