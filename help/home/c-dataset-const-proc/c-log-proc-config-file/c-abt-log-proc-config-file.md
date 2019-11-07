---
description: The Log Processing.cfg file controls the log processing phase of dataset construction, during which unordered data is read from the data sources (referred to as log sources), and filters and transformations are applied to the data.
solution: Analytics
title: About the Log Processing Configuration File
topic: Data workbench
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
---

# About the Log Processing Configuration File{#about-the-log-processing-configuration-file}

The Log Processing.cfg file controls the log processing phase of dataset construction, during which unordered data is read from the data sources (referred to as log sources), and filters and transformations are applied to the data.

You must edit the [!DNL Log Processing.cfg] file to perform any of the following dataset configuration tasks:

* Specifying log sources. See [Log Sources](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea). 
* Determining which log entries enter the dataset during log processing. See [Data Filters](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d) and [Log Entry Condition](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934). 

* Enabling the splitting of tracking IDs with large amounts of event data. See [Key Splitting](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf). 
* Configuring a data workbench server to run as a file server unit. See [Configuring an Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d). 
* Configuring a data workbench server to run as a centralized normalization server. See [Configuring an Insight Server File Server Unit](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] files can contain additional instructions for the log processing phase of dataset construction. These files exist within the Dataset\Log Processing directory for any inherited profile. They typically define application-specific parameters (such as web-specific configuration parameters for the Site application). For information about [!DNL Log Processing Dataset Include] files, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-dataset-inc-files.md#concept-a9b6a30edfc942b0b2a2888a0a8989df). For information about web-specific configuration parameters for Site, see [Configuration Settings for Web Data](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

