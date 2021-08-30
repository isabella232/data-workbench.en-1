---
description: Identify minimum requirements and recommendations for Data Workbench (formerly [!DNL Insight]) server components before planning and implementing your system.
title: Server System Requirements
uuid: c4487c76-03b9-4755-893b-555d451b1e69
exl-id: 6dd78331-8370-400e-b580-9b9bad13e62c
---
# Server System Requirements{#server-system-requirements}

Identify minimum requirements and recommendations for Data Workbench server components before planning and implementing your system.

## DPU Requirements{#dpu-requirements}

The server Data Processing Unit (DPU) is the main data processing component of Data Workbench. It listens for network connections from Data Workbench, reads raw source data from the File Server Unit (FSU) and uses substantial computational and storage resources.

### Licensed Capacity {#section-71850e13783443798b3df9eb22cc63dc}

Please refer to the Services Description in the *Adobe [!DNL Data Workbench (Insight)] Service Agreement* for license capacity information.

>[!NOTE]
>
>For *MS System Center Endpoint Protection* in Windows 2012 Servers, these executables need to be added to the ***Excluded Processes:*** >
>* [!DNL InsightServer64.exe] 
>* [!DNL ReportServer.exe] 
>* [!DNL ExportIntegration.exe] 
>

### DPU System Recommendations and Requirements {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe provides recommendations regarding a Data Workbench design that meets your business needs. However, the following guidelines are useful when selecting the operating system (OS) and hardware, because the optimized nature of the DPU software places specific requirements on the OS/hardware platform.

If a single dataset is limited by the capacity or speed of a single DPU, you can cluster them. For example, suppose you have three licensed copies of the DPU software that are used together to more quickly run a larger dataset. As the data is divided between the machines evenly, the licensed capacity of the dataset is multiplied by three. In addition, the processing speed per row becomes three times faster than a single DPU.

To achieve the best performance from your DPU investment, Adobe recommends the following high-performance components described in the following table:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Required </th> 
   <th colname="col3" class="entry"> Recommended </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Operating System </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>See recommendations. </p> </td> 
   <td colname="col3"> Latest-generation 4-core+ processors from Intel or AMD are recommended. For optimal performance, 8-cores; for a trade-off between speed and cost, 4-cores are recommended. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Working Data Storage </p> </td> 
   <td colname="col2"> <p>1TB+ of total logical temp storage. </p> <p>Low latency access to the disk sub-system </p> </td> 
   <td colname="col3"> <p>For temporary storage Adobe recommends either: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 to 8) * (750GB or higher) SATA HDDs (3.5” spindle.) </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 to 10) * (300GB or higher) SATA HDDs (2.5” spindle.) </li> 
    </ul> <p>These should be configured in a JBOD array. Alternatively, when gross disk capacity exceeds 2TB, an array of 2-disk RAID1 volumes can be used. For example, configure six disks as a 3*(2*750GB RAID 1 pair.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>System Data Storage </p> </td> 
   <td colname="col2"> <p>Additionally, Adobe requires high-availability storage of a modest size (20GB) for the OS, DPU software, and other system software. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clustering Hardware </p> </td> 
   <td colname="col2"> <p>See recommendations. </p> </td> 
   <td colname="col3"> <p>Use a homogenous set of servers. In a DPU cluster, the slowest server reduces the performance of the whole dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clustering Network Performance </td> 
   <td colname="col2"> A switched-gigabit Ethernet connection or greater. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

### Alternative Disk Subsystems {#section-6f984eabe8074759aa9deaf17e3a68b7}

When considering alternative disk subsystems for temp storage, consider the following factors and guidelines:

* The DPU is unusually demanding of a high performance disk system, so setting up an inadequate disk subsystem can cause performance bottlenecks. 
* The DPU software does its own performance-oriented data striping across a set of JBOD disks. Do not use RAID to increase speed. 
* Adobe recommends that the DPU has 400+ MB/s aggregate sustained bandwidth to the disks. 
* Average read sizes are very high (2MB+). For this reason 15K or 10K SAS disks often perform a little better (or worse) than SATA disks at a significant cost and capacity penalty. 
* Avoid using a SAN architecture. Experience shows that the cost to get a SAN to perform at the levels required is usually extreme. 
* The local disk subsystem is used as scratch space—no data is permanently lost from a HDD failure, so consider avoiding costly, slower, high-availability systems.

### Speed Considerations {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe cannot provide a warranty or representation concerning the speed at which data is processed by a configured Data Workbench, because a variety of factors impact the data processing speed, including but not limited to the following:

* Number of rows of data 
* Number of dimensions (columns) of data 
* Number and complexity of custom processing steps 
* Use of clustering 
* Speed of hardware

## File Server Unit Requirements{#file-server-unit-requirements}

The server's File Serving Unit (FSU) is the main data storage and management component of Data Workbench. The FSU acts as a file server for raw source data to the DPU, and, when appropriate, coordinates the clustering of DPUs. Each FSU is licensed to supply source data to up to five (5) DPUs.

<table id="table_45CF36583DFE4536BB31F6A1F6CC181E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> FSU Components </th> 
   <th colname="col2" class="entry"> Recommendations </th> 
   <th colname="col3" class="entry"> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Operating System, CPU, RAM </p> </td> 
   <td colname="col2"> <p>These requirements are the same as those of the DPU. However, for the FSU, Adobe recommends using the minimum requirements rather than following the recommendations. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Disk System </p> <p>The FSU requires highly-available, redundant storage for large volumes of data. Adobe will work with you to determine your exact requirements. </p> </td> 
   <td colname="col1"> <p>Adobe recommends: </p> 
    <ul id="ul_FFEEE5052FFD4876BA9A6476DD096539"> 
     <li id="li_F98750D509D640C68885D53FC691ED43">(12 or more) * (750GB or greater) SATA HDDs in a RAID 5/6 configuration. </li> 
     <li id="li_3F84F63F9541476987015C27FDE8251B">High-performance SAN connection supporting 100MB/s+ sustained bandwidth. </li> 
    </ul> <p>As the FSU holds the raw source data, any loss would be unrecoverable, and Adobe suggests backing up this data on a regular basis. </p> </td> 
   <td colname="col2"> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Network Performance </p> </td> 
   <td colname="col2"> <p>Adobe requires switched-gigabit Ethernet connections between FSUs and DPUs working together. </p> </td> 
   <td colname="col3"> </td>
  </tr> 
 </tbody> 
</table>

## Sensor Requirements{#sensor-requirements}

Data Workbench Sensor collects event data from web, application, and data collection servers to be transmitted to any server. [!DNL Sensor’s] instrumentation ensures consistently accurate measurement of events that occur in your Internet channel. [!DNL Sensor] supports many combinations of Web server software and operating system.

### Sensor System Recommendations {#section-0a981c3a47b644c1a1a56974ba033b9c}

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

### Support Server Software {#section-d6071706539f49d9a861d87b98e6f382}

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

## Report Server Requirements{#report-server-requirements}

Data workbench report server is the component that allows the output of scheduled reporting. The reports that are output can either be in the form of .PNG images or .XLS spreadsheets placed in a file system, or as emails. Its hardware requirements are identical to the [Data Workbench Client](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html).

The following requirements exist for [!DNL report server]:

* Access to file system for output of data (network share, or local drive). 
* Access to configured SMTP server. 
* Microsoft Excel 2003 or above installed on [!DNL report] server. See [Considerations for server-side Automation of Office](http://support.microsoft.com/kb/257757) for additional information.

## Network Management{#network-management}

Adobe recommends that existing network management systems monitor the hardware and network that the Data Workbench platform relies on.

 In addition, Adobe recommends monitoring the Windows event logs of the FSUs and DPUs, which are written to when an error occurs.

>[!NOTE]
>
>Any networked storage system hosting log files needs to provide at least 10MB per DPU of sustained bandwidth.

## Data Availability{#data-availability}

It is a normal and required practice for a server DPU to process and re-process data into new or refreshed dataset.

This may occur because of configuration changes, data source changes, hardware changes, inappropriate configuration, hardware failure, software failure, power failure, and so forth. When such processing or re-processing occurs, all dataset and system data is required to be immediately available to the DPU and FSU components. Failure to adhere to this requirement can lead to significant and unnecessary system down time. 

## DPU and FSU Network Issues{#dpu-and-fsu-network-issues}

Considerations to keep in mind when working with DPU and FSU networks.

* For networked log file distribution, any networked storage system hosting log files needs to provide at least 10MB per DPU of sustained bandwidth. 
* The DPU, FSU, and Data Workbench inter-communicate bi-directionally via HTTP or HTTPS on port 80 or 443 (by default; ports can be alternatively configured). 
* Data Workbench [!DNL Sensor(s)] must be able to connect (one-way) to the servers. 
* To allow the DPU to send alert messages via SMTP, it must be able to contact the configured SMTP server. 
* Adobe recommends that FSUs and DPUs be given network names such as FSU01.CLIENT.COM to avoid reconfiguration if the case of an IP-address change.
