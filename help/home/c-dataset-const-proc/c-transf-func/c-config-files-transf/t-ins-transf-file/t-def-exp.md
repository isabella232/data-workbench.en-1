---
description: Exporters provide the instructions for outputting the event data.
seo-description: Exporters provide the instructions for outputting the event data.
seo-title: Defining Exporters
solution: Analytics
title: Defining Exporters
topic: Data workbench
uuid: 1cd00cb2-a75e-4d56-958c-635fd1580d4e
index: y
internal: n
snippet: y
---

# Defining Exporters{#defining-exporters}

Exporters provide the instructions for outputting the event data.

Transformation functionality provides three types of exporters for exporting [!DNL .vsl] files, log files, XML files, and ODBC data as [!DNL .vsl] files, text files, or delimited text files that can be used by DataWarehouse loading routines, auditing agencies, or other targets.

>[!NOTE]
>
>For an exporter to work properly, the log source must meet the appropriate requirements discussed in the [Log Sources](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) section of [Log Processing Configuration File](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-proc-config-file.md#concept-20e3148be47841a1b33ae55d23667d33).

**To define an exporter** 

1. Open [!DNL Transform.cfg] in data workbench. See [To edit the Insight Transform.cfg file](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. Right-click **[!UICONTROL Exporters]**, then click **[!UICONTROL Add New]**.
1. Select one of the following options:

    * **[!UICONTROL ExportTextFile]** 
    * **[!UICONTROL ExportDelimitedTextFile]** 
    * **[!UICONTROL ExportVSLFile]**

       >[!NOTE]
       >
       >For the [!DNL ExportVSLFile] option, all of the extended fields in the input file and all user-defined fields of the form cs(*header*) are always written to the VSL output file. If you overwrite an existing extended field, the new value is written to the output file, even if the field is blank.

1. Edit the Exporters parameters in the configuration file using the following table as a guide:

    <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
 <desc> 
  <b>Exporter Parameters </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Data Format </td> 
   <td colname="col2"> <p>For <span class="wintitle"> ExportTextFile</span> only. The format of each output line, consisting of field name escapes (expressed as %<i>fieldname</i>%) and any other desired fixed text. The format should include a line separator, typically [CR] [LF]. </p> <p> A literal percent sign (%) can be embedded in the format string by escaping the character as shown here: %% </p> <p> An example of an entry for the Data Format parameter is <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Fields </td> 
   <td colname="col2">For <span class="wintitle"> ExportDelimitedTextFile</span> only. Names of the fields to be output. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Delimiter </td> 
   <td colname="col2"> <p>Optional. For <span class="wintitle"> ExportDelimitedTextFile</span> only. Character that is used to separate the fields in the output file. </p> <p> The software can not escape delimiters that are included in the data's values. As a result, Adobe does not recommend using commas as delimiters. </p> <p> If you hold down the Ctrl key and right-click within the Delimiter parameter, an <span class="wintitle"> Insert</span> menu appears. This menu contains a list of special characters that often are used as delimiters. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Line Separator </td> 
   <td colname="col2">Optional. For <span class="wintitle"> ExportDelimitedTextFile</span> only. The character(s) used to separate lines in the output files. The default value is [CR] [LF]. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> <p>Optional. Identifier for the exporter. This name appears in the <span class="wintitle"> Detailed Status</span> interface. </p> <p> For information about the <span class="wintitle"> Detailed Status</span> interface, see the <i>Data Workbench User Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Comments </td> 
   <td colname="col2"> Optional. Notes about the exporter. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Output Path </td> 
   <td colname="col2"> <p>Path where output files are to be stored. The path is relative to the data workbench server installation folder. </p> <p> <p>Note: The data workbench server that stores output data is processing server #0 in the <span class="filepath"> profile.cfg</span> file. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> File Rotation Period </td> 
   <td colname="col2"> <p>Optional. The frequency at which data is exported to the output file. Each output file contains data related to a specific time period called the rotation period. All time calculations are in GMT: One day starts at midnight GMT and ends the following day at midnight GMT, even if the data written to the file includes a field which has been transformed to local time. </p> <p> Available values are as follows: </p> 
    <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
     <li id="li_E4985C7F56E443049AFF57B0270032D6"> YEAR. Each file contains data for one calendar year. </li> 
     <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MONTH. Each file contains data for one calendar month. Months are numbered 1 (January) through 12 (December). </li> 
     <li id="li_91831283616C48DA8C8086776D181751"> WEEK. Each file contains data for one week. A week starts on Monday. The week starting on one of the first seven days of the year is week 1, and the prior (partial) week, if any, is week 0. </li> 
     <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DAY. Each files contains data for one calendar day. </li> 
     <li id="li_018F4133E03C42F29073FED1DB082ED5"> HOUR. Each file contains data for one hour. </li> 
     <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. No rotation is performed. All of the data is written to the same file (or a set of files as determined by other parameter settings). See the <span class="wintitle"> File Name Format</span> parameter in this table. </li> 
    </ul> <p>The default file rotation period is DAY. </p> 
    <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
     <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Set the file rotation to NONE only when working in <span class="wintitle"> Offline Mode</span>. See the <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13" format="dita" scope="local"> Offline Mode</a> parameter description. </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> File Name Format </td> 
   <td colname="col2"> <p>Optional. The format of the output file name. </p> <p> Each log entry can be stored in a file whose name is derived from the start time of the rotation period, and optionally, from values of fields in the rows that it contains. The fields to use in the file name are embedded as field name escapes (expressed as %<i>fieldname</i>%). </p> <p>The file name components related to the rotation period are embedded in the format string using the following escape sequences: 
     <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
      <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy% (four-digit year) </li> 
      <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (two-digit year) </li> 
      <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (two-digit month, 01 - 12) </li> 
      <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (two-digit week, 01 - 52) </li> 
      <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (two-digit day, 01 - 31) </li> 
      <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (two-digit hour, 00 - 23) </li> 
     </ul> </p> <p> The default file name format is <span class="filepath"> %yyyy%%mm%%dd%-%x-mask%.txt</span> </p> 
    <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
     <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> The escape sequences are case-sensitive. </li> 
     <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> When File Rotation Period is set to NONE, an empty string is substituted for each of the escape sequences, if present. </li> 
     <li id="li_C64731961ED6402FB92210A42854BA72"> An error is generated if <span class="wintitle"> File Name Format</span> does not result in a unique file name for each rotation period (see the File Rotation Period parameter in this table). For example, when using the DAY rotation period, the %dd%, %mm%, and %yy% or %yyyy% escape sequences must be present in the pattern to avoid data loss. </li> 
     <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> If you are using field name escape sequences within the pattern and the given field has many distinct values, many output files are written for each rotation period. Note that this scenario may result in poor performance, so you should use this feature with caution. </li> 
     <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> All times calculations are in GMT. </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Execute at Rollover </td> 
   <td colname="col2"> <p>Optional. When each file is finalized, an external (Windows) command can be executed. The command line is derived from the final file name by substituting the following escape sequences into this parameter: </p> 
    <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
     <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. The directory part of the final file name, including the trailing backslash. </li> 
     <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. The file name (excluding the directory and extension) of the final file. </li> 
     <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. The extension (including the leading ".") of the final file name. </li> 
     <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%. The full path name of the file, equivalent to %dir%%file%%ext%. </li> 
    </ul> <p> By default, this parameter is empty (no command is executed). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Memory Limit </td> 
   <td colname="col2"> <p>Optional. The amount of memory in bytes used for buffering the exporter's output. The default value is 10,000,000 bytes. </p> <p> <p>Note:  If you have many output files that are open at the same time, you may want to increase this value, but you may decrease the amount of memory available for use by other components of the system. Decreasing this value, however, may slow down the export process. For assistance, contact Adobe. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Open Files Limit </td> 
   <td colname="col2"> <p>Optional. The maximum number of files that may be open at the same time for output from the exporter. If this number is exceeded, an error is recorded in the event log and the data workbench server stops running. The default value is 1000. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. After you have defined your exporter (and made changes to other parameters) in the [!DNL Transform.cfg]file, save the file locally and save it to the appropriate profile on the data workbench server machine.
