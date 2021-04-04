---
description: Within the Workspaces folder of your Data Workbench installation directory, a folder.lock file specifies whether the workspaces in that particular folder are locked, while a workspace name.lock file specifies whether a particular workspace is locked.
solution: Analytics
title: Folder.lock and workspace.lock files
topic: Data workbench
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
---
# Folder.lock and workspace.lock files{#folder-lock-and-workspace-lock-files}

Within the Workspaces folder of your Data Workbench installation directory, a folder.lock file specifies whether the workspaces in that particular folder are locked, while a workspace name.lock file specifies whether a particular workspace is locked.

When locking entire folders, you can lock them at the Workspaces folder level or at the sub-folder (tab) level. You also can lock or unlock all of your folders (at the Workspaces folder level), then specify the exceptions for particular sub-folders (using [!DNL folder.lock] files) or particular workspaces (using *workspace name*.lock files).

The following example of the [!DNL Profile Manager] highlights three elements:

* A [!DNL folder.lock] file for the main Workspaces folder 
* A [!DNL Monthly Numbers.lock] file for the [!DNL Monthly Numbers.vw] workspace file 

* A [!DNL folder.lock] file for the Workspaces\Custom sub-folder

![](assets/wsp_Locking_lockFiles.png)

In this example, the [!DNL Workspaces folder.lock] file is set to locked, which locks all of the workspaces in this instance of Data Workbench. The Workspaces\Custom sub-folder [!DNL folder.lock] file is set to unlocked, which unlocks all of the workspaces on the [!DNL Custom] tab. Finally, the [!DNL Monthly Numbers.lock] file is set to locked, which locks the Monthly Numbers workspace.

## Creating .lock Files {#section-c4f78b4b43c347368a376904effb41d2}

You can create a [!DNL new folder.lock] file using the [!DNL Create menu] option in the [!DNL Profile Manager] or the [!DNL Workspaces Manager]. You also can create a [!DNL folder.lock] or *workspace name*.lock file by copying and pasting an existing [!DNL .lock] file to the appropriate folder, changing the name of the file (for *workspace name*.lock files only), and changing the setting in the file if necessary.

**To create a new folder.lock file**

1. In Data Workbench, open the [!DNL Workspaces Manager] by right-clicking within a workspace and clicking **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**. 
1. Click the folder for which you want to create a [!DNL folder.lock] file. 
1. In the [!DNL User] column for that folder, right-click in the cell and click **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] file appears. [!DNL New folder.lock] files are set to [unlocked] by default. 
1. (Optional) If you need to change the setting in the file:

    1. Right-click the check mark for the file. 
    1. Click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL folder.lock] file opens. 
    
    1. Change the setting to [locked]. 
    1. Save and close the file.

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

The workspaces in this folder are now locked or unlocked according to the setting in the new file.

**To create a .lock file from an existing file**

1. In the [!DNL Profile Manager] or [!DNL Workspaces Manager], right-click the check mark for an existing [!DNL .lock] file and click **[!UICONTROL Copy]**. 
1. In the [!DNL User] column for the folder into which you want to paste the [!DNL .lock] file, right-click in the cell and click **[!UICONTROL Paste]**. 
1. If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock.

   For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].”If this file is used to lock an individual workspace, right-click the check mark for the [!DNL .lock] file in the [!DNL User] column and change its name in the [!DNL File] field to match the name of the workspace that you want to lock. For example, to lock the [!DNL Monthly Numbers.vw] workspace, you would name the file “ [!DNL Monthly Numbers.lock].” 

1. To change the setting in the file:

    1. Right-click the check mark for the file. 
    1. Click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL .lock] file opens. 
    
    1. Change the setting to [locked] or [unlocked]. 
    1. Save and close the file.

1. To make this the setting for all users working with the same working profile, right-click the check mark for the file and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

The selected workspaces is now locked or unlocked according to the setting in the new file.
