---
description: The Transformation.cfg file controls the transformation phase of dataset construction during which additional data transformations are applied to data already processed during log processing to create extended dimensions for use in analysis.
solution: Analytics
title: About the Transformation Configuration File
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
---

# About the Transformation Configuration File{#about-the-transformation-configuration-file}

The Transformation.cfg file controls the transformation phase of dataset construction during which additional data transformations are applied to data already processed during log processing to create extended dimensions for use in analysis.

 You must edit the [!DNL Transformation.cfg] file to perform any of the following dataset configuration tasks:

* Filtering data from log processing by defining the [!DNL log entry condition] for transformation. 
* Setting the time zone to be used for creating time dimensions and making time conversions. See [Time Zones](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] files can contain additional instructions for the transformation phase of dataset construction. These files exist within the Dataset\Transformation directory for any inherited profile, and they typically define application-specific parameters (such as web-specific configuration parameters for the [!DNL Site] application). For information about [!DNL Transformation Dataset Include] files, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). For information about web-specific configuration parameters for Site, see [Configuration Settings for Web Data](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

