---
description: During reprocessing, the data workbench server reconstructs your dataset as you have specified in the Log Processing and Transformation Dataset Configuration files.
solution: Analytics
title: Understanding Reprocessing and Retransformation
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
---

# Understanding Reprocessing and Retransformation{#understanding-reprocessing-and-retransformation}

During reprocessing, the data workbench server reconstructs your dataset as you have specified in the Log Processing and Transformation Dataset Configuration files.

 To do so, the data workbench server (InsightServer64.exe) must complete both the log processing phase and the transformation phase of dataset construction. When log processing finishes, it triggers transformation to occur automatically, but transformation also can occur independently of log processing.

During the log processing phase, data workbench users do not have access to the data in the dataset. During the transformation phase, data workbench users do have access to up-to-date data, but the data is sampled instead of complete. Data analysis can continue during transformation, but queries will complete only as quickly as the transformation is occurring.

## Reprocessing {#section-92f1e46bf1534b3dba39e9493190b8ab}

Each time you complete one of the following tasks, log processing, and therefore transformation, occurs automatically to reconstruct your dataset as you have specified in the dataset configuration files:

* Add a new data source. 
* Add a new data workbench server to your cluster in the [!DNL Profile.cfg] file. 
* Change the [!DNL Cluster.cfg] file. 
* Change the [!DNL Log Processing.cfg] file or a [!DNL Log Processing Dataset Include] file, including but not limited to the following:

  * Add a new parameter 
  * Change a transformation 
  * Change the Start Time or End Time parameters

* Upgrade your [!DNL Insight Server.exe] file.

You also can initiate reprocessing at any time by entering any character or combination of characters in the Reprocess parameter of the [!DNL Log Processing.cfg] file and saving the file.

>[!NOTE]
>
>For reprocessing to occur, the Pause parameter in the [!DNL Log Processing Mode.cfg] file must be set to false. This parameter's default value is false, so changing the parameter may not be required. For more information about [!DNL Log Processing Mode.cfg], see [Additional Configuration Files](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md). 

## Retransformation {#section-02446744549940ada8eba0573ec5575f}

Each time you change any information in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file, such as change a transformation or define a new dimension, transformation occurs automatically.

Each time you change lookup files that are referenced in the [!DNL Transformation.cfg] file or in a [!DNL Transformation Dataset Include] file (including lookup files for [!DNL Categorize], [!DNL FlatFileLookup], and [!DNL ODBCLookup] transformations), you must initiate transformation by entering any character or combination of characters in the Reprocess parameter of the [!DNL Transformation.cfg] file and saving the file. 
