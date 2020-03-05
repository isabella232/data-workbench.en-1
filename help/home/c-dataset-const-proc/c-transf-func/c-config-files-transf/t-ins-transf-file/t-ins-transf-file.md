---
description: The data workbenchTransform.cfg file contains the parameters that define the log sources, data transformations, and exporters.
solution: Analytics
title: The Transform.cfg File
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
---

# The Transform.cfg File{#the-transform-cfg-file}

The data workbenchTransform.cfg file contains the parameters that define the log sources, data transformations, and exporters.

The transformations that you define manipulate raw data collected by Sensors ( [!DNL .vsl] files) or contained in text files, XML files, or ODBC-compliant databases and output them either into existing fields, overwriting the current data, or into newly defined fields.

To configure transformation functionality, you edit the data workbench [!DNL Transform.cfg] file within the Dataset folder for the profile for which you want to export event data. Typically, this profile is dedicated to transformation functionality (that is, you perform no other data processing than what is defined in the data workbench [!DNL Transform.cfg] file). It is important to note that any processing instructions specified in the [!DNL Log Processing Dataset Include] files for any inherited profiles are applied in addition to those specified in the data workbench [!DNL Transform.cfg] file.

For information about dataset include files, see [Dataset Include Files](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

If the data that you want to export is processed by a data workbench server cluster, each of the processing servers (DPUs) in the cluster processes the data, but only the first DPU (processing server #0 in the [!DNL profile.cfg] file) will write the output data to its local file system.

**To edit the data workbench Transform.cfg file** 

1. While working in the profile for which you want to export data, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.
1. Right-click the check mark next to data workbench [!DNL Transform.cfg], then click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The data workbench [!DNL Transform.cfg] window appears.
1. Edit the parameters in the configuration file using the table below as a guide:

  <table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> End Time </td> 
    <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps up to, but not including, this time. Adobe recommends using one of the following formats for the time: 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> January 1 2013HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> For example, specifying July 29 2013 00:00:00 EDT as the <span class="wintitle"> End Time </span> includes data through July 28, 2013, at 11:59:59 PM EDT. </p> <p> You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by the data workbench server, see <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Time Zone Codes </a>. </p> <p> The Use Start/End Times parameter for Sensor and log file sources is related to this parameter. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Exporters </td> 
    <td colname="col2"> <p>The subfields of an exporter specify how the output data is processed and/or formatted. You can define multiple exporters for a set of log sources. Each exporter type creates output independently. </p> <p> Three types of exporters exist: 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> For more information about exporter types, see <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> Defining Exporters </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Hash Threshold </td> 
    <td colname="col2"> Optional. A sampling factor for random sub-sampling of rows. If set to a number n, then only one out of each n tracking IDs are selected for exporting, reducing the total number of rows exported by a factor of n. To export all rows, you would set Hash Threshold to 1. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Log Entry Condition </td> 
    <td colname="col2"> Optional. Defines the rules by which log entries are considered for export. For more information about the <span class="wintitle"> Log Entry Condition </span>, see <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Log Processing Configuration File </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Log Sources </td> 
    <td colname="col2"> <p>The sources of data. <span class="wintitle"> Log sources </span> can be <span class="filepath"> .vsl </span> files, log files, or XML files or data from ODBC-compliant databases. For information about <span class="wintitle"> log sources </span>, see <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> Log Processing Configuration File </a>. </p> <p> <span class="wintitle"> Transform </span> expects all source data to be in chronological order within lexicographically ordered input files. If this requirement is not satisfied, As Of calculations are incorrect, and additional input data may be processed after the output files are closed. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Offline Mode </td> 
    <td colname="col2"> <p>Optional. True or false. If true, <span class="wintitle"> Transform </span> assumes that all of the input files are present when it starts processing the data. When all of the input data has been read, <span class="wintitle"> Transform </span> closes all of the output files without waiting for additional data to be received. The default value is false. </p> <p> <p>Note:  If <span class="wintitle"> Offline Mode </span> is set to true, <span class="wintitle"> Transform </span> expects all source data to be present before processing starts. A warning message is generated in the <span class="filepath"> VisualServer.log </span> file if additional data is received after the output files are closed. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Reprocess </td> 
    <td colname="col2"> <p>Optional. Any character or combination of characters can be entered here. Changing this parameter and saving the file to the <span class="wintitle"> Transform </span> machine initiates data reprocessing. </p> <p> For information about reprocessing your data, see <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Reprocessing and Retransformation </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Stages </td> 
    <td colname="col2"> <p>Optional. The names of the processing stages that can be used in <span class="wintitle"> Log Processing Dataset Include </span> files that are executed in addition to the data workbench <span class="filepath"> Transform.cfg </span> file. Processing stages provide a way to order the transformations that are defined in <span class="wintitle"> Log Processing Dataset Include </span> files. This parameter is very helpful if you have defined one or more transformations within multiple <span class="wintitle"> Log Processing Dataset Include </span> files and you want specific transformations to be performed at specific points during the export process. </p> <p> The order in which you list the stages here determines the order in which the transformations in the <span class="wintitle"> Log Processing Dataset Include </span> files are executed during data export. <span class="wintitle"> Preprocessing </span> and <span class="wintitle"> Postprocessing </span> are built-in stages; <span class="wintitle"> Preprocessing </span> is always the first stage, and <span class="wintitle"> Postprocessing </span> is always the last stage. By default, there is one named stage called <span class="wintitle"> Default </span>. </p> <p> <b>To add a new processing stage</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> In the data workbench <span class="filepath"> Transform.cfg </span> window, right-click <span class="uicontrol"> Stages </span>, then click <span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> Enter a name for the new stage. </li> 
      </ul> <p> <b>To delete an existing processing stage</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> Right-click the number corresponding to the stage that you want to delete and click <span class="uicontrol"> Remove </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>Note:  When you specify a Stage in a <span class="wintitle"> Log Processing Dataset Include </span> file the name of the stage must match exactly the name that you enter here. For more information about dataset include files, see <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Start Time </td> 
    <td colname="col2"> <p>Optional. Filter data to include log entries with timestamps at or after this time. Adobe recommends using one of the following formats for the time: </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> January 1 2013 HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> Jan 1 2013 HH:MM:SS GMT </li> 
      </ul> <p> For example, specifying July 29 2013 00:00:00 EDT as the Start Time includes data starting from July 29, 2013, at 12:00:00 AM EDT. </p> <p> You must specify a time zone. The time zone does not default to GMT if not specified. For a list of time zone abbreviations supported by the data workbench server, see <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Time Zone Codes </a>. </p> <p> <p>Note:  The Use Start/End Times parameter for Sensor and log file sources is related to this parameter. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Transformations </td> 
    <td colname="col2"> <p>Optional. Defines the transformations that are to be applied to the data. For information about the available transformation types, see <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Data Transformations </a>. </p> <p> <p>Note:  The following transformation types do not work when defined in the data workbench <span class="filepath"> Transform.cfg </span> file: </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

  >[!NOTE]
  >
  >If additional data is received after the output files are closed (see [!DNL Log Sources] and [!DNL Offline Mode] in the preceding table), [!DNL Transform] creates new output files with the additional data. The names of the new output files are generated from the original output file's name with the addition of a parenthesized version number just before the extension. For example, if the original output file is [!DNL 20070701-ABC.vsl], subsequent versions of this file will be named [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl], and so on. Note that using the versioned files as input to the data workbench server may result in processing errors. 
  >
  >
  >Adobe recommends avoiding the creation of versioned output files by making sure that all source data is in chronological order within lexicographically ordered input files and, if [!DNL Offline Mode] is set to true, that all source data is present before processing starts. For more information, see the [!DNL Log Sources] and [!DNL Offline Mode] entries in the preceding table.

1. Add transformations by right-clicking **[!UICONTROL Transformations]** and clicking **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. Complete the transformation fields.

   See [Data Transformations](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) for descriptions and examples of the transformations that you can use with transformation functionality. 

1. Right-click **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for data workbench [!DNL Transform.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, where profile name is the name of the profile for which you are exporting data. Reprocessing of the data begins after synchronization of the profile.

   >[!NOTE]
   >
   >For information about reprocessing your data for export, see [Reprocessing and Retransformation](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
