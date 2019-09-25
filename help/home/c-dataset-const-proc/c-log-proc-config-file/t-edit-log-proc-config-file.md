---
description: Steps to edit the Log Processing.cfg file for a dataset profile.
seo-description: Steps to edit the Log Processing.cfg file for a dataset profile.
seo-title: Editing the Log Processing Configuration File
solution: Analytics
title: Editing the Log Processing Configuration File
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
---

# Editing the Log Processing Configuration File{#editing-the-log-processing-configuration-file}

Steps to edit the Log Processing.cfg file for a dataset profile.

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*.

   >[!NOTE]
   >
   >A Log Processing subdirectory may exist within the Dataset directory. This subdirectory contains the [!DNL Log Processing Dataset Include] files that have been created for one or more inherited profiles. See [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df).

1. Right-click the check mark next to [!DNL Log Processing.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. The [!DNL Log Processing.cfg] window appears.

   You also can open the [!DNL Log Processing.cfg] file from a [!DNL Transformation Dependency Map]. For information about transformation dependency maps, see [Dataset Configuration Tools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5). 

1. Edit the parameters in the configuration file using the following table as a guide.

   When editing the [!DNL Log Processing.cfg] file within a data workbench window, you can use shortcut keys for basic editing features, including cut ( Ctrl+x ), copy ( Ctrl+c) , paste ( Ctrl+v ), undo ( Ctrl+z ), redo ( Ctrl+Shift+z ), select section (click+drag), and select all ( Ctrl+a ). You can also use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another.

   >[!NOTE]
   >
   >A [!DNL Log Processing Dataset Include] file for an inherited profile contains a subset of the parameters described in the following table as well as some additional parameters. See [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df).

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Log Sources </td> 
      <td colname="col2"> The sources of data. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea" format="dita" scope="local"> Log Sources </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> End Time </td> 
      <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps up to but not including this time. Adobe recommends using one of the following formats for the time: </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">January 1 2013 HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p>For example, specifying July 29 2013 00:00:00 EDT as the End Time includes data through July 28, 2013, at 11:59:59 PM EDT. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d" format="dita" scope="local"> Data Filters </a>. </p> <p>You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by the data workbench server, see <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477" format="dita" scope="local"> Time Zone Codes </a>. </p> <p> <p>Note:  The Use Start/End Times parameter for <span class="wintitle"> Sensor </span>, log file, and XML sources is related to this parameter. See the sections of <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea" format="dita" scope="local"> Log Sources </a> that discuss these source types. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fields </td> 
      <td colname="col2"> Optional. Adobe recommends defining <span class="wintitle"> Fields </span> in one or more <span class="wintitle"> Log Processing Dataset Include </span> files. See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab" format="dita" scope="local"> Log Processing Dataset Include Files </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Group Maximum Key Bytes </td> 
      <td colname="col2"> <p>Maximum amount of event data that the Server can process for a single tracking ID. Data exceeding this limit is filtered from the dataset construction process. This value must be set to 2e6 when key splitting is active and 1e6 when key splitting is not active. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf" format="dita" scope="local"> Key Splitting </a>. </p> <p> <p>Note:  Do not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Hash Threshold </td> 
      <td colname="col2"> <p>Optional. A sampling factor for random sub-sampling of rows. If set to a number n, then only one out of each n tracking IDs enters the dataset, reducing the total number of rows in the dataset by a factor of n. </p> <p>To create a dataset that requires 100 percent accuracy (that is, to include all rows), you would set Hash Threshold to 1. </p> <p>Values: </p> <span class="filepath"> Hash Threshold = 1 </span> (100 percent of data including all rows.) <p> <span class="filepath"> Hash Threshold = 2 </span> (1/2 of data and includes half the rows.) </p> <p> <span class="filepath"> Hash Threshold = 3 </span>(1/3 of data and includes one of three rows, but rounds to 34% in Query Completion) </p> <p> <span class="filepath"> Hash Threshold = 4 </span>(1/4th of data and includes one out of four rows.) </p> <p> </p> <p> <p>Note:  Using a Using a <span class="filepath"> Hash Threshold = 8 </span> provides 1/8th of the data, which is 12.5%. However the <span class="uicontrol"> Query Completion </span> value in the rounds to 13% for this value. Additional examples include a <span class="filepath"> Hash Threshold = 6 </span> that results in 17% query resolution. A <span class="filepath"> Hash Threshold = 13 </span>results in 8% query resolution. </p> </p> <p>If <span class="wintitle"> Hash Threshold </span> is specified in both the <span class="filepath"> Log Processing.cfg </span> and <span class="filepath"> Transformation.cfg </span> files, it is not applied in sequence; the maximum value set in either configuration file applies. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d" format="dita" scope="local"> Data Filters </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Log Entry Condition </td> 
      <td colname="col2"> Optional. Defines the rules by which log entries are considered for inclusion in the dataset. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934" format="dita" scope="local"> Log Entry Condition </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Reprocess </td> 
      <td colname="col2"> <p>Optional. Any character or combination of characters can be entered here. Changing this parameter and saving the file to the data workbench Server machine initiates data reprocessing. </p> <p>See <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823" format="dita" scope="local"> Reprocessing and Retransformation </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bucket Space </td> 
      <td colname="col2"> <p>Parameter involved in key splitting. Its value should be 6e6 when key splitting is active. See <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split" format="dita" scope="local"> Key Splitting </a>. </p> <p> <p>Note:  Do not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Bytes </td> 
      <td colname="col2"> <p>Parameter involved in key splitting. Its value should be 1e6 when key splitting is active and 0 when key splitting is not active. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf" format="dita" scope="local"> Key Splitting </a>. </p> <p> <p>Note:  Do not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Split Key Space Ratio </td> 
      <td colname="col2"> <p>Parameter involved in key splitting. Its value should be 10 when key splitting is active. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf" format="dita" scope="local"> Key Splitting </a>. </p> <p> <p>Note:  Do not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stages </td> 
      <td colname="col2"> <p>Optional. The names of the processing stages that can be used in <span class="wintitle"> Log Processing Dataset Include </span> files. Processing stages provide a way to order the transformations that are defined in <span class="wintitle"> Log Processing Dataset Include </span> files. This parameter is very helpful if you have defined one or more transformations within multiple <span class="wintitle"> Log Processing Dataset Include </span> files and you want specific transformations to be performed at specific points during log processing. </p> <p>The order in which you list the stages here determines the order in which the transformations in the <span class="wintitle"> Log Processing Dataset Include </span> files are executed during log processing. Preprocessing and Postprocessing are built-in stages. Preprocessing is always the first stage, and Postprocessing is always the last stage. By default, there is one named stage called Default. </p> <p> <b>To add a new processing stage</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">In the <span class="filepath"> Log Processing.cfg </span> window, right-click <span class="uicontrol"> Stages </span> and click <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">Enter a name for the new stage. </li> 
      </ul> </p> <p> <b>To delete an existing processing stage</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">Right-click the number corresponding to the stage that you want to delete and click <span class="uicontrol"> Remove </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Note:  When you specify a <span class="wintitle"> Stage </span> in a <span class="wintitle"> Log Processing Dataset Include </span> files, the name of the stage must match exactly the name that you enter here. See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df" format="dita" scope="local"> Dataset Include Files </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Start Time </td> 
      <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps at or after this time. Adobe recommends using one of the following formats for the time: </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> January 1 2013 HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> For example, specifying "July 29 2013 00:00:00 EDT" as the Start Time includes data starting from July 29, 2013, at 12:00:00 AM EDT. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d" format="dita" scope="local"> Data Filters </a>. </p> <p> You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by the data workbench server, see <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477" format="dita" scope="local"> Time Zone Codes </a>. </p> <p> <p>Note:  The Use Start/End Times parameter for <span class="wintitle"> Sensor </span>, log file, and XML sources is related to this parameter. See the sections of <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea" format="dita" scope="local"> Log Sources </a> that discuss these source types. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Time Zone </td> 
      <td colname="col2"> <p>Optional. Time zone of the the data workbench server that is used for time conversions (such as the conversion represented by the x-local-timestring field) during log processing. </p> <p> <p>Note:  You must specify the Time Zone if you want to access the converted time field during the log processing phase of dataset construction. Otherwise, the data workbench server records an error in the event logs. </p> </p> <p>See <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956" format="dita" scope="local"> Time Zones </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Transformations </td> 
      <td colname="col2"> Optional. Adobe recommends defining transformations for log processing in one or more <span class="wintitle"> Log Processing Dataset Include </span> files. See <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab" format="dita" scope="local"> Log Processing Dataset Include Files </a>. </td> 
   </tr> 
   </tbody> 
   </table>

1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. In the [!DNL Profile Manager], right-click the check mark for [!DNL Log Processing.cfg]in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL dataset profile name]**>* to make the locally made changes take effect. Reprocessing of the data begins after synchronization of the dataset profile.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

   For more information about reprocessing your data, see [Reprocessing and Retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823). 
