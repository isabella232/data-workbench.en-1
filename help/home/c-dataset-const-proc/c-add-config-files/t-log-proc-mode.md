---
description: The configuration file Log Processing Mode.cfg enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which data workbench server saves its state files.
seo-description: The configuration file Log Processing Mode.cfg enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which data workbench server saves its state files.
seo-title: Log Processing Mode.cfg
solution: Analytics
title: Log Processing Mode.cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

The configuration file Log Processing Mode.cfg enables you to pause processing of data into a dataset, specify offline sources, or specify the frequency at which data workbench server saves its state files.

 Making changes to the [!DNL Log Processing Mode.cfg] file, including adding or removing sources, does not cause reprocessing of the data.

**To edit the Log Processing Mode.cfg file for a dataset profile** 

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.

   >[!NOTE]
   >
   >If the [!DNL Log Processing Mode.cfg] file is not located in the directory for the desired profile, you need to copy this file from the Base directory on the data workbench server machine into the profile's directory.

   For information about opening and working with the [!DNL Profile Manager,] see the *Data Workbench User Guide*. 

1. Right-click the check mark next to the configuration file's name and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The configuration window appears.
1. Edit the parameters in the configuration file using the following table as a guide.

       >[!NOTE]
       >
       >Some of the parameters in the [!DNL Log Processing Mode.cfg] file have names that include [!DNL Fast Input] or [!DNL Fast Merge]. [!DNL Fast Input]refers to the log processing phase of dataset construction and is responsible for approximately half of the total dataset processing time. [!DNL Fast Merge] refers to the transformation phase of dataset construction only when preceded by log processing. [!DNL Fast Merge] does not occur during retransformation that results from modifying a [!DNL Transformation Dataset Configuration] file. Like [!DNL Fast Input], [!DNL Fast Merge] is also responsible for approximately half of the dataset processing time.

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <desc> 
   <b> <b> Log Processing Mode.cfg</b> </b> 
   </desc> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parameter </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Cloud Bytes </td> 
      <td colname="col2"> <p>A tuning parameter that affects the efficiency of data transformation. The default value is 128000000. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input Decision Ratio </td> 
      <td colname="col2"> <p>A tuning parameter that specifies the ratio of total to unread log bytes at which the system enters <span class="wintitle"> Fast Input</span> mode (and subsequently <span class="wintitle"> Fast Merge</span>) instead of processing data in real time. </p> <p> The default value is 200, meaning that the system enters <span class="wintitle"> Fast Input</span> mode from real-time mode when the unread log data is at 1/200th of the total data. A higher decision ratio makes the system enter <span class="wintitle"> Fast Input</span> mode more readily, while a lower ratio makes it less likely to enter <span class="wintitle"> Fast Input</span> mode. </p> <p> <p>Note: Setting the parameter to 0 prevents the system from entering <span class="wintitle"> Fast Input</span> mode at all, even for initial processing. Setting the parameter to 1.1 enables the system to enter <span class="wintitle"> Fast Input</span> during initial processing but not for subsequent processing. Adobe does not recommend using values between 0 and 1.1. For more information about setting this parameter, contact Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Input FIFO Bytes </td> 
      <td colname="col2"> <p>A tuning parameter that balances memory usage and system performance during data processing. The default value is 120000000. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fast Merge Buffer Bytes </td> 
      <td colname="col2"> <p>A tuning parameter that balances memory usage and system performance during data processing. The default value is 128000000. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Offline Sources </td> 
      <td colname="col2"> <p>Mask of the offline log source. </p> <p> <b> To specify an offline source</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
      <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> Right-click <span class="uicontrol"> Offline Sources</span>, then click <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> Source</span>. </li> 
      <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> In the parameter for the new source, enter the mask of the log sequence. For Sensor log sources with file names of the format YYYYMMDD-<i>SENSORID</i>.vsl, the mask is <i>SENSORID.SENSORID</i> is case-sensitive. For log file log sources, the mask is the string extracted by the <span class="wintitle"> Mask Pattern</span>. See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e" format="dita" scope="local"> Log Files</a>. </li> 
      </ul> </p> <p> Adding or removing sources from Offline Sources does not cause reprocessing of the dataset. </p> <p> As Of time measurements are maintained for the processing of the profile's online sources. When the offline source is again online, the processing of incoming log files for that source resumes. </p> <p> Whenever a source comes back online, you should remove it from Offline Sources. If you do not do so, data workbench server treats the source as an online source and updates the As Of time as long as the source is sending data. If the source goes offline again, the As Of time measurements stop. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Paused </td> 
      <td colname="col2"> True or false. If true, new data is not processed into the dataset. The default value is false. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time Delay </td> 
      <td colname="col2"> The amount of time in seconds that data workbench Server waits between intervals of processing data into the dataset. When this value is set to zero, the system attempts to keep up with incoming data in real time. The default value is zero (0), but you can increase this value to reduce CPU load. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Real Time FIFO Bytes </td> 
      <td colname="col2"> <p>The amount of memory in bytes used to store data that is waiting to be processed into the dataset. You may need to change this value based on the number of seconds that you specify for Real Time Delay. The default value is 16000000. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Save Interval (sec) </td> 
      <td colname="col2"> <p>Frequency at which the data workbench server saves its state files. The default value is 3600. </p> <p> <p>Note:  You should not change this value without consulting Adobe. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>
    
   When editing the [!DNL Log Processing Mode.cfg] file within a data workbench window, you can use shortcut keys for basic editing features, including cut (Ctrl+x ), copy (Ctrl+c) , paste (Ctrl+v ), undo (Ctrl+z ), redo (Ctrl+Shift+z ), select section (click+drag), and select all (Ctrl+a ). In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another. 
    
1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. In the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

