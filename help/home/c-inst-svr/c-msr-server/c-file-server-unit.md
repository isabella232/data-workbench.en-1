---
description: The server's File Serving Unit (FSU) is the main data storage and management component of Data Workbench.
seo-description: The server's File Serving Unit (FSU) is the main data storage and management component of Data Workbench.
seo-title: File Server Unit Requirements
solution: Analytics
title: File Server Unit Requirements
uuid: e5b73474-9f38-46f2-8c15-42eddecfb8a1
---

# File Server Unit Requirements{#file-server-unit-requirements}

The server's File Serving Unit (FSU) is the main data storage and management component of Data Workbench.

 The FSU acts as a file server for raw source data to the DPU, and, when appropriate, coordinates the clustering of DPUs. Each FSU is licensed to supply source data to up to five (5) DPUs.

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

