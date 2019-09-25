---
description: Information about the required Sensor txlogd.conf parameters.
seo-description: Information about the required Sensor txlogd.conf parameters.
seo-title: Required Parameters
solution: Insight
title: Required Parameters
uuid: 187f4199-ec7f-4d5a-93eb-64a62d51ec7b
---

# Required Parameters{#required-parameters}

Information about the required Sensor txlogd.conf parameters.

<table id="table_69CFE10A3707403F9793137B128E706A"> 
 <desc> 
  <b>Required Txlogd.conf Parameters </b> 
 </desc> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In this Parameter... </th> 
   <th colname="col2" class="entry"> Specify... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> SensorID </td> 
   <td colname="col2"> <p>A character string that uniquely identifies this <span class="wintitle"> Sensor</span>. </p> <p> <span class="wintitle"> Sensor</span> attaches the SensorID to each event record it sends to the <span class="keyword"> data workbench server</span>. The SensorID enables the event data from this web server to be distinguished from the event data captured by other <span class="wintitle"> Sensors</span>. </p> <p>Although a SensorID can consist of any string of characters, by convention, the name of the web server whose events the <span class="wintitle"> Sensor</span> is capturing is used. Using the server name as the SensorID makes it easy to determine the source of an event during the analysis stage. It also ensures that the SensorID is unique within the implementation. </p> <p>Example: <span class="filepath"> SensorID web001a</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerAddress </td> 
   <td colname="col2"> <p>The address of the <span class="keyword"> data workbench server</span> to which this <span class="wintitle"> Sensor</span> sends event data. </p> <p>Note:  <p>When working in a clustered environment, <span class="wintitle"> Sensor</span> should be configured to access the master <span class="keyword"> data workbench server</span> to avoid synchronization issues. In Data Workbench you can view information about the processing <span class="keyword"> data workbench servers</span> in your cluster using the Related Servers menu item in the <span class="wintitle"> Servers Manager</span>. For more information about the <span class="wintitle"> Servers Manager</span>, see the <i><span class="keyword"> Data Workbench</span><span class="wintitle"> Sensor</span> Guide</i>. </p> <p>If your web server can resolve server names through DNS, you can specify the server’s address by name. If not, you must specify the server’s numeric IP address. </p> <p>Example: <span class="filepath"> ServerAddress 10.1.0.7</span> or </p> <p> <span class="filepath"> ServerAddress vserver01.mycompany.com</span> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL </td> 
   <td colname="col2"> <p>Whether <span class="wintitle"> Sensor</span> communicates with <span class="keyword"> data workbench server</span> using HTTP or HTTPS. Set to “on” for HTTPS or “off” for HTTP. </p> <p>Example: <span class="filepath"> SSL on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ServerPort </td> 
   <td colname="col2"> <p>The port on which the <span class="keyword"> data workbench server</span> listens for event data. </p> <p>Example: <span class="filepath"> ServerPort 443</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertName </td> 
   <td colname="col2"> <p>Required only if the SSL parameter is set to “on.” </p> <p>The common name of the <span class="keyword"> data workbench server</span> to which this <span class="wintitle"> Sensor</span> sends event data. </p> <p>The value you specify must exactly match the common name that appears on the <span class="keyword"> data workbench server</span> license certificate. </p> <p>Example: <span class="filepath"> CertName vserver01.mycompany.com</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CertPath </td> 
   <td colname="col2"> <p>Required only if the SSL parameter is set to “on.” </p> <p>The directory in which the certificate authority (<span class="filepath"> trust_ca_cert.pem</span>) file is located </p> <p>Examples: </p> <p> <span class="filepath"> CertPath /usr/local/visualsensor</span> </p> <p> <span class="filepath"> CertPath C:\VisualSensor</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueFile </td> 
   <td colname="col2"> <p>Not needed for <span class="wintitle"> Sensor</span> installations on Microsoft Windows 2000 or 2003 Server machines running Internet Information Service (IIS) versions 5.x or 6.x. </p> <p>The fully qualified name of the disk queue file. </p> <p>Although you can assign any name to this file, by convention, the queue file is named <span class="filepath"> VisualSensor.dat</span>. </p> <p>For <span class="wintitle"> Sensor</span> installations on Unix, you can place this file anywhere. On Windows running a Java web server, you must place this file in the same directory as the transmitter. For all other web servers, this file should reside in the /var/queue directory. </p> <p>Example: <span class="filepath"> QueueFile /var/queue/VisualSensor.dat</span> </p> <p> <p>Note:  Make sure that the device to which you assign this file has enough free space to accommodate a queue of the size you need. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> QueueSize </td> 
   <td colname="col2"> <p>An integer that represents the size of the disk queue file in MB. </p> <p>For <span class="wintitle"> Sensor</span> installations on Microsoft Windows, the queue file itself is created in the same directory as the transmitter and is named <span class="filepath"> Diskq2000.log</span>. </p> <p>The following example sets the queue size to 200 MB: </p> <p>QueueSize 200 </p> <p>The following example sets the queue size to 2 GB: </p> <p>QueueSize 2000 </p> </td> 
  </tr> 
 </tbody> 
</table>

