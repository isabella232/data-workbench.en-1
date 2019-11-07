---
description: The configuration file Transform Mode.cfg enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which the data workbench server running transformation functionality saves its state files.
solution: Analytics
title: The Transform Mode.cfg File
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
---

# The Transform Mode.cfg File{#the-transform-mode-cfg-file}

The configuration file Transform Mode.cfg enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which the data workbench server running transformation functionality saves its state files.

Making changes to the [!DNL Transform Mode.cfg] file, including adding or removing sources, does not cause reprocessing of the data.

**To edit the Transform Mode.cfg file for a dataset profile** 

1. While working in the profile whose data you want to export, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.
1. Right-click the check mark next to [!DNL Transform Mode.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Transform Mode.cfg] window appears.
1. Edit the parameters in the configuration file using the following table as a guide:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parameter </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Offline Sources </td> 
    <td colname="col2"> <p>Mask of the offline log source. </p> <p> To specify an offline source: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Right-click <span class="uicontrol"> Offline Sources</span> and click <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> Source</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> In the parameter for the new source, enter the mask of the log sequence. For Sensor log sources with file names of the format <span class="filepath"> YYYYMMDD-SENSORID.vsl</span>, the mask is <i>SENSORID.SENSORID</i> is case-sensitive. For log file log sources, the mask is the string extracted by the <span class="wintitle"> Mask Pattern</span> (see <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>). </li> 
    </ul> <p> Adding or removing sources from <span class="wintitle"> Offline Sources</span> does not cause reprocessing of the dataset. </p> <p> As Of time measurements are maintained for the processing of the profile's online sources. When the offline source is again online, the processing of incoming log files for that source resumes. </p> <p> <p>Note: Whenever a source comes back online, you should remove it from <span class="wintitle"> Offline Sources</span>. If you do not do so, the data workbench server treats the source as an online source and updates the As Of time as long as the source is sending data. If the source goes offline again, the As Of time measurements stop. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Paused </td> 
    <td colname="col2"> True or false. If true, new data is not processed into the dataset. The default value is false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Save Interval (sec) </td> 
    <td colname="col2"> <p>Frequency at which the data workbench server on which transformation functionality is running saves its state files. The default value is 3600. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>    
    
    When editing the [!DNL Transform Mode.cfg] file within a data workbench window, you can use shortcut keys for basic editing features, including cut (Ctrl+x ), copy (Ctrl+c) , paste (Ctrl+v ), undo (Ctrl+z ), redo (Ctrl+Shift+z ), select section (click+drag), and select all (Ctrl+a ). In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another. 
    
1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the data workbench [!DNL Transform Mode.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, where profile name is the name of the profile for which you are exporting data. Reprocessing of the data begins after synchronization of the profile.

   For information about reprocessing your data for export, see [Reprocessing and Retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823). 
