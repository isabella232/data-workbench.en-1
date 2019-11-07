---
description: You can define data transformations to be applied during either the log processing or transformation phase of dataset construction.
solution: Analytics
title: Defining a Transformation
topic: Data workbench
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
---

# Defining a Transformation{#defining-a-transformation}

You can define data transformations to be applied during either the log processing or transformation phase of dataset construction.

>[!NOTE]
>
>Adobe recommends defining transformations in either [!DNL Log Processing] or [!DNL Transformation Dataset Include] files instead of in [!DNL Log Processing.cfg] or [!DNL Transformation.cfg].

The following transformations work only when defined in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file:

* [AppendURI](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)I 
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2) 
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f) 
* [ODBC Data Sources](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3) 
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**To define a transformation** 

1. Use the [!DNL Profile Manager] to open the dataset configuration file in which you want to define the transformation.

    * (Recommended) To open a dataset include file, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df). 
    * To open the [!DNL Log Processing.cfg] file, see [Editing the Log Processing Configuration File](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5). 
    
    * To open the [!DNL Transformation.cfg] file, see [Editing the Transformation Configuration File](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Right-click **[!UICONTROL Transformations]**, then click **[!UICONTROL Add new]** > *< **[!UICONTROL Transformation type]**>*.
1. Input the appropriate information for your transformation. For descriptions of the transformation types and information about their parameters, see the following sections:

    * [Standard Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886) 
    * [URI Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125) 
    * [Integrating Lookup Data](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. After you have defined your transformation(s) in the configuration file, save the file locally and save it to your dataset profile on the data workbench server.

       Tips for defining and editing transformations:

    * When editing the configuration of a transformation within a data workbench window, you can use shortcut keys for basic editing features, including cut (Ctrl+x ), copy (Ctrl+c) , paste (Ctrl+v ), undo (Ctrl+z ), redo (Ctrl+Shift+z ), select section (click+drag), and select all (Ctrl+a ). In addition, you can use the shortcuts to copy and paste text or entire transformation definitions from one configuration file ( [!DNL .cfg]) to another. 
    * For any transformation that you define, you can add one or more comment lines to the Comments parameter to further describe the transformation or add notes about its use. To add a comment using data workbench, right-click the **[!UICONTROL Comments]** label, then click **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**. 
    
    * You can open the configuration of any transformation from a [!DNL Transformation Dependency Map]. After you open the configuration, you can edit it and save your changes. For information about [!DNL Transformation Dependency Maps], see [Dataset Configuration Tools](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5). 
    
    * An empty string output from a transformation can overwrite a non-empty string in the output field.

