---
description: List of files installed with Insight Server and the files present after it has been registered, and run for the first time.
seo-description: List of files installed with Insight Server and the files present after it has been registered, and run for the first time.
seo-title: Insight Server Directory Structure
solution: Insight
title: Insight Server Directory Structure
uuid: a913116d-e26b-492b-ad9d-1c03a6f68df3
index: y
internal: n
snippet: y
---

# Insight Server Directory Structure{#insight-server-directory-structure}

List of files installed with Insight Server and the files present after it has been registered, and run for the first time.

## Files Included in the Installation Package {#section-daec17dab3e34c3c9e1ef65842cb91f1}

The following directories are included in the [!DNL Insight Server] installation package:

<table id="table_CE713A3D671C453A87986E4CD4620EF3"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Description of Directory Contents </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Access Control </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> configuration file which specifies a list of Access Groups. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Addresses </td> 
   <td colname="col2"> Address(es) used for communication with <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Audit </td> 
   <td colname="col2"> Daily access logs containing details regarding all attempted connections to <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> bin </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> executable program files. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Certificates </td> 
   <td colname="col2"> SSL digital certificates. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Components </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> component configuration files. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Components for Processing Servers </td> 
   <td colname="col2"> <span class="keyword"> Insight Server </span> component configuration files for processing <span class="keyword"> Insight Servers </span> within an <span class="keyword"> Insight Server </span> cluster. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Events </td> 
   <td colname="col2"> Daily event logs containing detailed event status messages, including error messages. Events captured and logged by <span class="keyword"> Insight Server </span> are also displayed in Windows Event Viewer. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Logs </td> 
   <td colname="col2"> <p>Log files produced by <span class="wintitle"> Sensor </span>(s). </p> <p>“Logs” is the default logging directory, but an alternate directory may have been specified in the <span class="filepath"> communications.cfg </span> file. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Lookups </td> 
   <td colname="col2"> Lookup files, such as robot and search engine lists. <span class="keyword"> Insight Server </span> must load all lookup files into memory. The total size of all lookup files referenced in component configuration files, plus overhead (for example, 12 bytes per row for <span class="filepath"> FlatFileLookup </span> files), must not exceed the available physical or virtual memory that is available after all other software applications are loaded. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Profiles </td> 
   <td colname="col2"> <p>Files related to each profile (configuration, workspace, and visualization files). Profiles are populated by data from a dataset. Datasets include event data (“Log Data”); such data may be captured by installed <span class="wintitle"> Sensors </span>, transmitted by Web beacons or page tags, or input from data warehouses. <span class="keyword"> Insight </span> users with access to a given profile may use the set of processed data for that profile as well as the Workspaces and visualizations defined within that profile. </p> <p>Workspaces are work areas for system administration or analysis. A Workspace can contain multiple interfaces showing different details about system performance. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Software </td> 
   <td colname="col2"> <span class="keyword"> Insight </span> software updates. Report software updates are also stored here. </td> 
  </tr> 
 </tbody> 
</table>

## Directories and Files Created after Startup {#section-ef7408e8fae64454b326ec07453d4628}

The directories listed below are created after [!DNL Insight Server] is registered and run for the first time:

<table id="table_89CC9F3E568044C8A0072BF0A6EDCCEF"> 
 <desc> 
  <b> <span class="keyword"> Insight Server </span> Startup Files </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> State </td> 
   <td colname="col2"> Processing information generated by <span class="keyword"> Insight Server </span>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Temp </td> 
   <td colname="col2"> <p>Location of the temporary files used by <span class="keyword"> Insight Server </span> during reprocessing and operation. There is usually one file (named <span class="filepath"> temp.db </span> by default) per physical drive. </p> <p> <span class="keyword"> Insight Server </span> must be configured to write to this directory. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Trace </td> 
   <td colname="col2"> Log and event data about <span class="keyword"> Insight Server </span>. Useful for troubleshooting. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Users </td> 
   <td colname="col2"> Named ( <span class="keyword"> Insight </span>) users with access to the profiles on the Server. A directory for each authorized named user is created within the directory Users\ when the user first accesses <span class="keyword"> Insight Server </span> via <span class="keyword"> Insight </span>. The directory for each named user contains directories corresponding to all of the profiles that the user has accessed on that <span class="keyword"> Insight Server </span> as well as their local address files. </td> 
  </tr> 
 </tbody> 
</table>

