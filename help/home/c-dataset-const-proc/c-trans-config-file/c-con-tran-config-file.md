---
description: Important information to consider when editing the Transformation.cfg file.
seo-description: Important information to consider when editing the Transformation.cfg file.
seo-title: Considerations for the Transformation Configuration File
solution: Analytics
title: Considerations for the Transformation Configuration File
topic: Data workbench
uuid: d86a6307-1e17-4cbe-9f0e-07a5cb80beeb
index: y
internal: n
snippet: y
---

# Considerations for the Transformation Configuration File{#considerations-for-the-transformation-configuration-file}

Important information to consider when editing the Transformation.cfg file.

* Changing any of the parameters in this file requires retransformation of the data. 
* If you reprocess the data, you can check the [!DNL Transformation Progress] parameter in data workbench's [!DNL Processing Legend].

  For information about reprocessing your data or the [!DNL Processing Legend,] see [Reprocessing and Retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize], and [!DNL AppendURI] transformations work only when defined in a [!DNL Transformation Dataset Configuration] file. For information about these transformations, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-data-trans.md#concept-99c6f5e6e5194adb9e98afdc0e91cf38).

  >[!NOTE]
  >
  >Adobe recommends defining transformations for the transformation phase of dataset construction in one or more [!DNL Transformation Dataset Include] files. For information, see [Transformation Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* You can add any of the parameters described above to the [!DNL Transformation.cfg] file by opening and editing the file in Notepad. Any changes you make and save appear when you reopen the file in data workbench. When adding a new parameter, use the Space key (not the Tab key) to indent two (2) spaces to the right of the previous heading level.

  Any errors that occur during the transformation phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

