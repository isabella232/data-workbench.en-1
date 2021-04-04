---
description: The Log Processing.cfg file controls the log processing phase of dataset construction, during which unordered data is read from the data sources (referred to as log sources), and filters and transformations are applied to the data.
solution: Analytics
title: About the Log Processing Configuration File
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
---
# About the Log Processing Configuration File{#about-the-log-processing-configuration-file}

The Log Processing.cfg file controls the log processing phase of dataset construction, during which unordered data is read from the data sources (referred to as log sources), and filters and transformations are applied to the data.

You must edit the [!DNL Log Processing.cfg] file to perform any of the following dataset configuration tasks:

* Specifying log sources. See [Log Sources](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md). 
* Determining which log entries enter the dataset during log processing. See [Data Filters](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) and [Log Entry Condition](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md). 

* Enabling the splitting of tracking IDs with large amounts of event data. See [Key Splitting](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md). 
* Configuring a data workbench server to run as a file server unit. See [Configuring an Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md). 
* Configuring a data workbench server to run as a centralized normalization server. See [Configuring an Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] files can contain additional instructions for the log processing phase of dataset construction. These files exist within the Dataset\Log Processing directory for any inherited profile. They typically define application-specific parameters (such as web-specific configuration parameters for the Site application). For information about [!DNL Log Processing Dataset Include] files, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). For information about web-specific configuration parameters for Site, see [Configuration Settings for Web Data](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
