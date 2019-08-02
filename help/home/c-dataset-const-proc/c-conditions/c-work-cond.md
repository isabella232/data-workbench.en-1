---
description: Information about adding, removing, or copying a condition.
seo-description: Information about adding, removing, or copying a condition.
seo-title: Working With Conditions
solution: Analytics
title: Working With Conditions
topic: Data workbench
uuid: b6f52b40-26aa-429b-9ff5-3f3b9c9d57a9
index: y
internal: n
snippet: y
---

# Working With Conditions{#working-with-conditions}

Information about adding, removing, or copying a condition.

* [To Add a Condition to a Dataset Configuration File](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-3e2a34db047b462585502f69722f6511) 
* [To Remove a Condition from a Dataset Configuration File](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-677270f93f1648c3a268ca2aea7d4540) 
* [To Copy a Condition](../../../home/c-dataset-const-proc/c-conditions/c-work-cond.md#section-00617bcf2c274f428686b2ec7f2d1db8)

## To Add a Condition to a Dataset Configuration File {#section-3e2a34db047b462585502f69722f6511}

1. While working in your dataset profile, use the [!DNL Profile Manager] to open the dataset configuration file that you want to edit.

    * To open the [!DNL Log Processing.cfg] file, see [Editing the Log Processing Configuration File](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5). 
    
    * To open the [!DNL Transformation.cfg] file, see [Editing the Transformation Configuration File](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc). 
    
    * To open a [!DNL Dataset Include] file, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df).

1. Within the dataset configuration file, locate the Log Entry Condition or Condition parameter that you would like to define. 
1. Right-click the parameter and click **[!UICONTROL Add new]**. Choose one of the following condition types:

    * [!DNL Not Empty] 
    * [!DNL String Match] 
    * [!DNL Regular Expression] 
    * [!DNL Range] 
    * [!DNL And] 
    * [!DNL Or] 
    * [!DNL Neither] 
    * [!DNL Compare]

1. Edit the parameters of the condition as desired. For descriptions of the parameters of each condition, see the appropriate section of this appendix. 
1. To save your changes, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 

1. To make the locally made changes take effect, in the [!DNL Profile Manager,] right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > <* **[!UICONTROL profile name]***>, where profile name is the name of the dataset profile or the inherited profile to which the file belongs.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe, as your changes are overwritten when you install updates to these profiles.

## To Remove a Condition from a Dataset Configuration File {#section-677270f93f1648c3a268ca2aea7d4540}

1. Right-click the name of the condition or the number corresponding to the condition that you want to remove. 
1. Click **[!UICONTROL Remove]** <* **[!UICONTROL #number]***>, where number is the number corresponding to the condition that you want to remove.

## To Copy a Condition {#section-00617bcf2c274f428686b2ec7f2d1db8}

You can copy a condition from one location to another location in the same file, or you can copy a condition from one dataset configuration file to another.

1. Right-click the name of the condition or the number corresponding to the condition that you want to copy and click **[!UICONTROL Copy]**. 
1. Right-click the name or number of the condition below which you want to place the copied condition and click **[!UICONTROL Paste]**.

