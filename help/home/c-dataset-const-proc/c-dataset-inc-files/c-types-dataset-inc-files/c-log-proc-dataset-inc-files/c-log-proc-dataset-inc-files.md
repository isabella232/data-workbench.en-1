---
description: The Log Processing Dataset Include file for an inherited profile contains parameters associated with the log processing phase of dataset construction.
solution: Analytics
title: Log Processing Dataset Include Files
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
---

# Log Processing Dataset Include Files{#log-processing-dataset-include-files}

The Log Processing Dataset Include file for an inherited profile contains parameters associated with the log processing phase of dataset construction.

 The first line of a [!DNL Log Processing Dataset Include] file defines a type [!DNL LogProcessingInclude] that supports the Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage, and Transformations parameters. All other parameters for log processing must be defined in the [!DNL Log Processing.cfg] file in the dataset profile's Dataset directory. You can name a [!DNL Log Processing Dataset Include] file anything you want, but its file extension must be [!DNL .cfg]. The file must be stored within the *inherited profile name*\Dataset\Log Processing directory. Because the files are loaded recursively during the log processing phase of dataset construction, you can store the [!DNL Log Processing Dataset Include] files at any level within the directory (for example, *inherited profile name*\Dataset\Log Processing\*folder name*\*include file name*.cfg).

>[!NOTE]
>
>Many web-specific configuration parameters for Site are defined in [!DNL Log Processing Dataset Include] files. For information about these parameters, see [Configuration Settings for Web Data](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Decoder Groups </td> 
   <td colname="col2"> <p>Required if you have defined log file or XML file log sources in the <span class="filepath"> Log Processing.cfg</span> file. The text file or XML decoders that you define to extract fields of data from log file and XML log sources. </p> <p> <b>To add a new decoder group</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Right-click <span class="uicontrol"> Decoder Group</span> and click <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> or <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> In the Name parameter for the new group, enter the desired name of the decoder group. </li> 
     </ul> </p> <p> <p>Note:  When you specify a Decoder Group in the <span class="filepath"> Log Processing.cfg</span> file for the dataset profile, the name must match exactly the name that you enter here. For more information, see <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </p> </p> <p> For information about the decoders that you can define for each group, see <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Text File Decoder Groups</a> or <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML Decoder Groups</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fields </td> 
   <td colname="col2"> <p>Lists fields that are defined in <span class="wintitle"> Log Sources</span> or <span class="wintitle"> Transformations</span> in a <span class="wintitle"> Log Processing Dataset Configuration</span> file but used in transformations, conditions, or extended dimensions in a <span class="wintitle"> Transformation Dataset Configuration</span> file must be listed here. </p> <p> Each field below must be listed in some <span class="wintitle"> Log Processing Dataset Include</span> file: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Log Entry Condition </td> 
   <td colname="col2"> <p>Optional. Defines the rules by which log entries are considered for inclusion in the dataset. See <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Log Entry Condition</a>. </p> <p> <p>Note:  To be included in the dataset, a log entry must satisfy the <span class="wintitle"> Log Entry Condition</span> in the <span class="filepath"> Log Processing.cfg</span> file and in every <span class="wintitle"> Log Processing Dataset Include</span> file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parameters </td> 
   <td colname="col2"> Optional. A variable that you can reference in other configuration parameters. For more information, see <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Defining Parameters in Dataset Include Files</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reprocess </td> 
   <td colname="col2"> <p>Optional. Any character or combination of characters can be entered here. Changing this parameter and saving the file to the data workbench server initiates data reprocessing. </p> <p> For information about reprocessing your data, see <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessing and Retransformation</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Optional. The name of the processing stage that applies to this <span class="wintitle"> Log Processing Dataset Include</span> file. The processing stages are defined in the Stages parameter in the <span class="filepath"> Log Processing.cfg</span> file. </p> <p> <p>Note:  When you specify a Stage, the name of the Stage must match exactly the name that is listed in the Stages parameter in the <span class="filepath"> Log Processing.cfg</span> file for the dataset profile. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Transformations </td> 
   <td colname="col2"> Optional. Defines the data transformations that need to be applied during log processing. For information about the available transformation types, see <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>For descriptions of the parameters in the [!DNL Log Processing.cfg] file, see [Log Processing Configuration File](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

You should keep the following points in mind whenever you are working with [!DNL Log Processing Dataset Include] files:

* Changing any of the parameters in this file requires reprocessing of all of the data. 
* You can add any of the parameters described above to the [!DNL Log Processing Dataset Include] file by opening and editing the file in Notepad. Any changes you make and save appear when you reopen the file in data workbench. When adding a new parameter, use the Space key (not the Tab key) to indent two (2) spaces to the right of the previous heading level.

