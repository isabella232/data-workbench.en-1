---
description: Dataset include files provide a flexible way to configure your dataset.
seo-description: Dataset include files provide a flexible way to configure your dataset.
seo-title: Working with Dataset Include Files
solution: Analytics
title: Working with Dataset Include Files
topic: Data workbench
uuid: 258226c4-22e5-4d9d-9044-8312709e0460
---

# Working with Dataset Include Files{#working-with-dataset-include-files}

Dataset include files provide a flexible way to configure your dataset.

 Within each file, you can define as few or as many fields, transformations, or dimensions as you desire, and you can organize the include files based on the inherited profile to which they belong. When configuring your dataset, you have the option of editing the dataset include files provided with the internal profiles for your Adobe application or creating new dataset include files for any inherited profiles that you create.

When you edit the parameters of a dataset include file for an internal profile and save the updated file to your dataset profile or an inherited profile that you create, you are, in effect, overriding the file's original settings. Adobe recommends editing a dataset include file for an internal profile whenever you need to make minor changes to the dataset's contents, such as changing a Condition parameter or a parameter's default setting. See [Editing Existing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). However, when you want to specify a new field to be passed from log processing to transformation, update or create new fields using transformations, or define extended dimensions, it is best to create a new dataset include file. See [Creating New Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e). You can edit the file that you create whenever or however you see fit. 
