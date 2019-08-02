---
description: Steps for editing the Transformation.cfg file for a dataset profile.
seo-description: Steps for editing the Transformation.cfg file for a dataset profile.
seo-title: Editing the Transformation Configuration File
solution: Analytics
title: Editing the Transformation Configuration File
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
index: y
internal: n
snippet: y
---

# Editing the Transformation Configuration File{#editing-the-transformation-configuration-file}

Steps for editing the Transformation.cfg file for a dataset profile.

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

   >[!NOTE]
   >
   >A Transformation subdirectory may exist within the Dataset directory. This subdirectory contains the [!DNL Transformation Dataset Include] files that have been created for one or more inherited profiles. For information about [!DNL Transformation Dataset Include] files, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df).

1. Right-click the check mark next to [!DNL Transformation.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. The [!DNL Transformation.cfg] window appears.

   You also can open the [!DNL Transformation.cfg] file from a [!DNL Transformation Dependency Map]. For information about [!DNL transformation dependency maps], see [Dataset Configuration Tools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5). 

1. Edit the parameters in the configuration file using the following table as a guide.

       When editing the [!DNL Transformation.cfg] file within a data workbench window, you can use shortcut keys for basic editing features, including cut (Ctrl+x ), copy (Ctrl+c) , paste (Ctrl+v ), undo (Ctrl+z ), redo (Ctrl+Shift+z ), select section (click+drag), and select all (Ctrl+a ). In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

       >[!NOTE]
       >
       >A [!DNL Transformation Dataset Include] files for an inherited profile contains a subset of the parameters described in the following table as well as some additional parameters. For information about [!DNL Transformation Dataset Include] files, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df)

    <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
 <desc> 
  <b> <b> Transformation.cfg</b> </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> End Time </td> 
   <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps up to, but not including, this time. Adobe recommends using one of the following formats for the time: 
     <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
      <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> January 1 2013 HH:MM:SS EDT </li> 
      <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> Jan 1 2013 HH:MM:SS GMT </li> 
     </ul> </p> <p> For example, specifying "July 29 2013 00:00:00 EDT" as the End Time includes data through July 28, 2013, at 11:59:59 PM EDT. </p> <p> You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by the data workbench server, see <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477" format="dita" scope="local"> Time Zone Codes </a>. </p> <p> <p>Note:  If you specify a value for End Time, a parameter named End Time is set and applied throughout the transformation phase of dataset construction. For information about parameters, see <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50" format="dita" scope="local"> Defining Parameters in Dataset Include Files </a>. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Extended Dimensions </td> 
   <td colname="col2"> Optional. Adobe recommends defining extended dimensions in one or more <span class="wintitle"> Transformation Dataset Include </span> files. For information, see <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace" format="dita" scope="local"> Transformation Dataset Include Files </a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Hash Threshold </td> 
   <td colname="col2"> <p>Optional. A sampling factor for random sub-sampling of rows. If set to a number n, then only one out of each n tracking IDs enters the dataset, reducing the total number of rows in the dataset by a factor of n. To create a dataset that requires 100 percent accuracy (that is, to include all rows), you would set Hash Threshold to 1. </p> <p> If Hash Threshold is specified in both the <span class="filepath"> Log Processing.cfg </span> and <span class="filepath"> Transformation.cfg </span> files, it is not applied in sequence; the maximum of the values set in either configuration file applies. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Log Entry Condition </td> 
   <td colname="col2"> Optional. Defines the rules by which log entries output from log processing are considered for inclusion in the dataset profile. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934" format="dita" scope="local"> Log Entry Condition </a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> New Visitor Condition </td> 
   <td colname="col2"> Optional. For use with web data. Defines the rules by which visitors are considered for inclusion in the data. The <span class="wintitle"> New Visitor Condition </span> defines the first log entry for a visitor (ordered by time) that is to be used in the dataset. All subsequent log entries for this visitor are included in the dataset regardless of whether they meet this condition. See <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3" format="dita" scope="local"> New Visitor Condition </a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>Optional. Any character or combination of characters can be entered here. Changing this parameter and saving the file initiates data retransformation. </p> <p> For information about reprocessing your data, see <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823" format="dita" scope="local"> Reprocessing and Retransformation </a>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Schema Checking </td> 
   <td colname="col2"> True or false. If true, then the data workbench server identifies dataset corruption problems and records information about the problems in log files in the data workbench server's Trace directory. The default value is true. Adobe recommends leaving this parameter set to true at all times. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Stages </td> 
   <td colname="col2"> <p>Optional. The names of the processing stages that can be used in <span class="wintitle"> Transformation Dataset Include </span> files. Processing stages provide a way to order the transformations that are defined in <span class="wintitle"> Transformation Dataset Include </span> files. This parameter is very helpful if you have defined one or more transformations within multiple <span class="wintitle"> Transformation Dataset Include </span> files and you want specific transformations to be performed at specific points during transformation. </p> <p> The order in which you list the stages here determines the order in which the transformations in the <span class="wintitle"> Transformation Dataset Include </span> files are executed during transformation. <span class="wintitle"> Preprocessing </span> and <span class="wintitle"> Postprocessing </span> are built-in stages; <span class="wintitle"> Preprocessing </span> is always the first stage, and <span class="wintitle"> Postprocessing </span> is always the last stage. By default, there is one named stage called <span class="wintitle"> Default </span>. </p> <p> <b>To add a new processing stage</b> </p> <p> 
     <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
      <li id="li_80627E7A89CE4E57A4228C4F5496533F"> In the <span class="filepath"> Transformation.cfg </span> window, right-click <span class="uicontrol"> Stages </span> and click <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
      <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Enter a name for the new stage. </li> 
     </ul> </p> <p> <b>To delete an existing processing stage</b> </p> <p> 
     <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
      <li id="li_3B3829DA34FD4774B3F9F94074099794"> Right-click the number corresponding to the stage that you want to delete and click <span class="uicontrol"> Remove </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
     </ul> </p> <p> <p>Note:  When you specify a Stage in a <span class="wintitle"> Transformation Dataset Include </span> files the name of the stage must match exactly the name that you enter here. For more information about dataset include files, see <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df" format="dita" scope="local"> Dataset Include Files </a>. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Start Time </td> 
   <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps at or after this time. Adobe recommends using one of the following formats for the time: 
     <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
      <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> January 1 2013 HH:MM:SS EDT </li> 
      <li id="li_CA1BB675C1244104915FB9ED96A3013D"> Jan 1 2013 HH:MM:SS GMT </li> 
     </ul> </p> <p> For example, specifying July 29 2013 00:00:00 EDT as the <span class="wintitle"> Start Time </span> includes data starting from July 29, 2013, at 12:00:00 AM EDT. </p> <p> You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by data workbench Server, see <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477" format="dita" scope="local"> Time Zone Codes </a>. </p> <p> <p>Note:  If you specify a value for Start Time, a parameter named Start Time is set and applied throughout the transformation phase of dataset construction. For information about parameters, see <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50" format="dita" scope="local"> Defining Parameters in Dataset Include Files </a>. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Optional. Adobe recommends defining transformations for the transformation phase of dataset construction in one or more <span class="wintitle"> Transformation Dataset Include </span> files. For information, see <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace" format="dita" scope="local"> Transformation Dataset Include Files </a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Time Zone </td> 
   <td colname="col2"> <p>Time zone of the dataset profile. Time zones are used for time conversions and for creating time dimensions. See <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956" format="dita" scope="local"> Time Zones </a>. </p> <p> <p>Note:  When defined in the <span class="filepath"> Log Processing.cfg </span> file, the Time Zone parameter is used for time conversions only. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. In the [!DNL Profile Manager], right-click the check mark for [!DNL Transformation.cfg]in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL dataset profile name]**>* to make the locally made changes take effect. Retransformation of the data begins after synchronization of the dataset profile.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

   For information about reprocessing or retransforming your data, see [Reprocessing and Retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823). 

