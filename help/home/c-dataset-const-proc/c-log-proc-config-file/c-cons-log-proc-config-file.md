---
description: Conceptual information to consider when editing the Log Processing.cfg file.
seo-description: Conceptual information to consider when editing the Log Processing.cfg file.
seo-title: Considerations for the Log Processing Configuration File
solution: Analytics
title: Considerations for the Log Processing Configuration File
topic: Data workbench
uuid: cb10c5fc-fb08-458e-a77f-e91d53156da6
index: y
internal: n
snippet: y
---

# Considerations for the Log Processing Configuration File{#considerations-for-the-log-processing-configuration-file}

Conceptual information to consider when editing the Log Processing.cfg file.

* Data files should not be moved between directories after the sources for a dataset have been defined. The only additional files a directory should receive are newly created ones that result from the data workbench server receiving data from [!DNL Sensor](s). 
* Changing any of the parameters in this file requires reprocessing of all the data. The Pause parameter in the [!DNL Log Processing Mode.cfg] file must be set to false for reprocessing to occur. (Note that this parameter's default value is false, so changing the parameter may not be required.) For information about the [!DNL Log Processing Mode.cfg] file, see [Additional Configuration Files](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004). 

* If you reprocess the data, you can check the Log Processing Progress parameter in data workbench's [!DNL Processing Legend].

  For information about reprocessing your data, see [Reprocessing and Retransformation](../../../home/c-dataset-const-proc/c-reproc-retrans/c-reproc-retrans.md#concept-6d82a173e4ab4111b673e7c2477d0823). See [Processing Legend](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828). 

* The [!DNL Log Processing.cfg] file can be shared by multiple dataset profiles. Transformations defined in the [!DNL Log Processing.cfg] file are applied to all dataset profiles that share this configuration file.

  >[!NOTE]
  >
  >Adobe recommends defining transformations for the log processing in one or more log processing [!DNL dataset include] files. For information, see [Log Processing Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

* You can add any of the parameters described above to the [!DNL Log Processing.cfg] file by opening and editing the file in Notepad. Any changes you make and save appear when you reopen the file in data workbench. When adding a new parameter, use the Space key (not the Tab key) to indent two (2) spaces to the right of the previous heading level.

  Any errors that occur during the log processing phase of the dataset construction process for a dataset profile are shown in the [!DNL Profiles] node of the [!DNL Detailed Status] interface in data workbench. For information about the [!DNL Detailed Status] interface, see the *Data Workbench User Guide*.

