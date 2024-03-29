---
description: If you do not have permission to delete files from a profile or you do not want to delete a file permanently, you can use empty (zero-byte) files to hide files.
title: Hide a file by emptying it (zero-byte)
uuid: 82c1a5c9-1bbb-41c7-bee7-704f0a9ef87d
exl-id: d5841fb5-afae-4352-aded-01b0b2eb9f85
---
# Hide a file by emptying it (zero-byte){#hide-a-file-by-emptying-it-zero-byte}

If you do not have permission to delete files from a profile or you do not want to delete a file permanently, you can use empty (zero-byte) files to hide files.

In the [!DNL Profile Manager], a hyphen (-), instead of a check mark, in a column identifies a zero-byte file.

![](assets/vis_ProfMgr_Zero-byte.png)

Unlike the other methods of hiding files (such as [!DNL order.txt], the Show parameter, and the Hidden parameter), Data Workbench treats zero-byted files as non-existent. For example, if you zero-byte a dimension that has been used in a visualization or a metric definition, Data Workbench produces an error for that visualization or metric, respectively.

This functionality is useful for a number of reasons, including when you want to do the following:

* **Make a file unusable** in Data Workbench without needing the profile permissions required to delete the file. 
* **Move a metric, dimension, or filter** to another location without needing the profile permissions required to delete the file from the original location. 
* **Hide menu items.** For example, the [!DNL Base] profile has a [!DNL Metric Legend] defined in the [!DNL Metric.vw] file. Say your company has created three metric legends that you want to appear on a Add Legend > Metric submenu. You can zero-byte the [!DNL Base] profile [!DNL Metric.vw] file so that only your new submenu and three new metric legends appear.

**To hide a file**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to zero-byte. 
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**. 
1. Open the local file and delete its contents. 
1. Save and close the file.
