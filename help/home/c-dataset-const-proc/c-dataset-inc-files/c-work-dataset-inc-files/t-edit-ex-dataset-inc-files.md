---
description: Steps to editing existing dataset include files.
seo-description: Steps to editing existing dataset include files.
seo-title: Editing Existing Dataset Include Files
solution: Analytics
title: Editing Existing Dataset Include Files
topic: Data workbench
uuid: 049226dd-eb92-4a49-9496-d867682f4833
index: y
internal: n
snippet: y
---

# Editing Existing Dataset Include Files{#editing-existing-dataset-include-files}

Steps to editing existing dataset include files.

You open an existing dataset include file using the [!DNL Profile Manager] in data workbench.

For information about opening and working with the [!DNL Profile Manager], see the *Data Workbench User Guide*. 

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show the contents of the directory.

    * To open a [!DNL Log Processing Dataset Include] file, click **[!UICONTROL Log Processing]** to show the contents of the directory. 
    
    * To open a [!DNL Transformation Dataset Include] file, click **[!UICONTROL Transformation]** to show the contents of the directory.

1. Right-click the check mark next to the desired dataset include file and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column.
1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The configuration window appears.

   You can also open a dataset include file from a [!DNL Transformation Dependency Maps]. For information about [!DNL Transformation Dependency Maps], see [Reprocessing and Retransformation](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823). 

1. Edit the parameters in the configuration file as appropriate. See [Log Processing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) or [Transformation Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) for descriptions of the parameters.

   When editing a dataset include file within a data workbench window, you can use shortcut keys for basic editing features, including cut (Ctrl+x ), copy (Ctrl+c) , paste (Ctrl+v ), undo (Ctrl+z ), redo (Ctrl+Shift+z ), select section (click+drag), and select all (Ctrl+a ). In addition, you can use the shortcuts to copy and paste text from one configuration file ( [!DNL .cfg]) to another. 

1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.
1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs. Reprocessing or retransformation of the data begins after synchronization of the dataset profile.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

