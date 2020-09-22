---
description: By default, Insight Server writes its dataset (temp.db) to the same drive as the Insight Server program files.
solution: Analytics
title: Configuring the Location of the Dataset (temp.db)
uuid: a6884cad-70ed-4bc6-853c-700d301fb178
---

# Configuring the Location of the Dataset (temp.db){#configuring-the-location-of-the-dataset-temp-db}

By default, Insight Server writes its dataset (temp.db) to the same drive as the Insight Server program files.

For example, if you install [!DNL Insight Server] on drive C, it writes the dataset to drive C.

If you want [!DNL Insight Server] to maintain the dataset on a different drive, or if the amount of data you expect to collect requires the use of multiple drives, you must update the [!DNL Disk Files.cfg] file to specify where you want [!DNL Insight Server] to write the [!DNL temp.db] file.

**To configure the location of temp.db** 

1. Navigate to the [!DNL Components] folder in the directory where you installed [!DNL Insight Server].

   Example: [!DNL C:\Adobe\Server\Components]

1. Open the [!DNL Disk Files.cfg] file in a text editor such as Notepad.

   By default, this file contains a single entry in the Disk Files structure as shown below.

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 1 items
      0 = string: Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

1. To change the location of [!DNL temp.db], modify the Disk Files definition. The following example illustrates how you would edit the configuration to spread the [!DNL temp.db] file across drives C, D, and E:

   ```
   component = DiskSpaceManagerComponent:
     Disk Files = vector: 3 items
       0 = string: C:\\Temp\\temp.db
       1 = string: D:\\Temp\\temp.db
       2 = string: E:\\Temp\\temp.db
     Detect Disk Corruption = bool: true
   ```

   >[!NOTE]
   >
   >Note the use of the double backslashes in the file names above. In [!DNL Insight Server] configuration files, the backslash character is an escape character. It is used to express special control sequences (for example, \t for a tab character) in text. To represent an actual backslash character, you must type the backslash twice (for example, \\) to override the escape function. This applies only when editing configuration files in a text editor such as Notepad.

