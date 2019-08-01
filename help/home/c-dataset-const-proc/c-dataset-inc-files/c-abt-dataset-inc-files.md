---
description: Many of the internal profiles that you received with your Adobe application come with their own dataset configuration files.
seo-description: Many of the internal profiles that you received with your Adobe application come with their own dataset configuration files.
seo-title: About Dataset Include Files
solution: Analytics
title: About Dataset Include Files
topic: Data workbench
uuid: 9daea47d-a1cf-41d6-945a-fd068f2eea10
index: y
internal: n
snippet: y
---

# About Dataset Include Files{#about-dataset-include-files}

Many of the internal profiles that you received with your Adobe application come with their own dataset configuration files.

 Because the internal profiles are sub-profiles of the dataset profile, their dataset configuration files contain rules that provide additional parameters for the log processing or transformation phases of dataset construction. The dataset configuration files for internal profiles and for any inherited profiles that you create are called dataset include files.

A dataset include file contains a subset of the parameters contained in the main dataset configuration files ( [!DNL Log Processing.cfg] or [!DNL Transformation.cfg]) for the dataset profile. Dataset include files containing parameters associated with log processing are called [!DNL Log Processing Dataset Include] files (see [Log Processing Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), while dataset include files associated with transformation are called [!DNL Transformation Dataset Include] Files. See [Transformation Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). You can create multiple dataset include files for use in the dataset construction process. The complete dataset includes all of the fields, transformations, and extended dimensions defined in all of the dataset configuration files for the dataset profile and any inherited profiles. 
