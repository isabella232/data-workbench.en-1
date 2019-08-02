---
description: The server Data Processing Unit (DPU) is the main data processing component of Data Workbench.
seo-description: The server Data Processing Unit (DPU) is the main data processing component of Data Workbench.
seo-title: DPU Requirements
solution: Analytics
title: DPU Requirements
uuid: 7c588378-5faa-468f-af27-8e19e5bdd8d3
index: y
internal: n
snippet: y
---

# DPU Requirements{#dpu-requirements}

The server Data Processing Unit (DPU) is the main data processing component of Data Workbench.

 It listens for network connections from Data Workbench, reads raw source data from the File Server Unit (FSU) and uses substantial computational and storage resources.

## Licensed Capacity {#section-71850e13783443798b3df9eb22cc63dc}

Please refer to the Services Description in the *Adobe [!DNL Data Workbench (Insight)] Service Agreement* for license capacity information.

>[!NOTE]
>
>For *MS System Center Endpoint Protection* in Windows 2012 Servers, these executables need to be added to the ***Excluded Processes:*** >
>* [!DNL InsightServer64.exe] 
>* [!DNL ReportServer.exe] 
>* [!DNL ExportIntegration.exe] 
>

## DPU System Recommendations and Requirements {#section-ae30555959bf4a309c76d0fd597b5162}

Adobe provides recommendations regarding a Data Workbench design that meets your business needs. However, the following guidelines are useful when selecting the operating system (OS) and hardware, because the optimized nature of the DPU software places specific requirements on the OS/hardware platform.

If a single dataset is limited by the capacity or speed of a single DPU, you can cluster them. For example, suppose you have three licensed copies of the DPU software that are used together to more quickly run a larger dataset. As the data is divided between the machines evenly, the licensed capacity of the dataset is multiplied by three. In addition, the processing speed per row becomes three times faster than a single DPU.

To achieve the best performance from your DPU investment, Adobe recommends the following high-performance components described in the following table:

<table id="table_DA0A60CFBA7D4EF98B5ED5A3D8D6777B"> 
 <desc> 
  <b> <span class="keyword"> Server </span> DPU Requirements </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Required </th> 
   <th colname="col3" class="entry"> Recommended </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Operating System </p> </td> 
   <td colname="col2"> <p>Microsoft Windows Server 2008 x64 </p> </td> 
   <td colname="col3"> <p>Microsoft Windows Server 2012 x64 </p> <p> Microsoft Windows Server 2016 x64 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>CPU </p> </td> 
   <td colname="col2"> <p>See recommendations. </p> </td> 
   <td colname="col3"> Latest-generation 4-core+ processors from Intel or AMD are recommended. For optimal performance, 8-cores; for a trade-off between speed and cost, 4-cores are recommended. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>RAM </p> </td> 
   <td colname="col2"> <p>8 GB </p> </td> 
   <td colname="col3"> <p>12 GB </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Working Data Storage </p> </td> 
   <td colname="col2"> <p>1TB+ of total logical temp storage. </p> <p>Low latency access to the disk sub-system </p> </td> 
   <td colname="col3"> <p>For temporary storage Adobe recommends either: </p> 
    <ul id="ul_F3D033B90CF94F44A2A773B3F6852283"> 
     <li id="li_B902CF7CC6A44F02838B285ADC725A75">(4 to 8) * (750GB or higher) SATA HDDs (3.5” spindle.) </li> 
     <li id="li_A378F4E1443F4BB2B54DC7E8372EE572">(6 to 10) * (300GB or higher) SATA HDDs (2.5” spindle.) </li> 
    </ul> <p>These should be configured in a JBOD array. Alternatively, when gross disk capacity exceeds 2TB, an array of 2-disk RAID1 volumes can be used. For example, configure six disks as a 3*(2*750GB RAID 1 pair.) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>System Data Storage </p> </td> 
   <td colname="col2"> <p>Additionally, Adobe requires high-availability storage of a modest size (20GB) for the OS, DPU software, and other system software. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>Clustering Hardware </p> </td> 
   <td colname="col2"> <p>See recommendations. </p> </td> 
   <td colname="col3"> <p>Use a homogenous set of servers. In a DPU cluster, the slowest server reduces the performance of the whole dataset. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Clustering Network Performance </td> 
   <td colname="col2"> A switched-gigabit Ethernet connection or greater. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

## Alternative Disk Subsystems {#section-6f984eabe8074759aa9deaf17e3a68b7}

When considering alternative disk subsystems for temp storage, consider the following factors and guidelines:

* The DPU is unusually demanding of a high performance disk system, so setting up an inadequate disk subsystem can cause performance bottlenecks. 
* The DPU software does its own performance-oriented data striping across a set of JBOD disks. Do not use RAID to increase speed. 
* Adobe recommends that the DPU has 400+ MB/s aggregate sustained bandwidth to the disks. 
* Average read sizes are very high (2MB+). For this reason 15K or 10K SAS disks often perform a little better (or worse) than SATA disks at a significant cost and capacity penalty. 
* Avoid using a SAN architecture. Experience shows that the cost to get a SAN to perform at the levels required is usually extreme. 
* The local disk subsystem is used as scratch space—no data is permanently lost from a HDD failure, so consider avoiding costly, slower, high-availability systems.

## Speed Considerations {#section-01330be232894e08a526d8d82b7c4eb2}

Adobe cannot provide a warranty or representation concerning the speed at which data is processed by a configured Data Workbench, because a variety of factors impact the data processing speed, including but not limited to the following:

* Number of rows of data 
* Number of dimensions (columns) of data 
* Number and complexity of custom processing steps 
* Use of clustering 
* Speed of hardware

