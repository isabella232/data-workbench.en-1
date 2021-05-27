---
description: You can use either the Hidden parameter or the Show parameter to hide extended dimensions so they do not show on the dimension menu in data workbench.
title: Hiding Extended Dimensions
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
---
# Hiding Extended Dimensions{#hiding-extended-dimensions}

You can use either the Hidden parameter or the Show parameter to hide extended dimensions so they do not show on the dimension menu in data workbench.

 When you enter the appropriate setting for either parameter, the dimension name is not listed in the menu in data workbench, but it is still in the profile and available to be used. Any data workbench user can temporarily unhide hidden dimensions by setting the Unhide All parameter in the [!DNL Insight.cfg] file to true.

For more information about the Unhide All parameter, see the appendix on data workbench configuration parameters in the *Data Workbench User Guide*.

The following sections describe how to use the Hidden and Show parameters to hide extended dimensions.

* [Hiding Extended Dimensions Using the Hidden Parameter](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf) 
* [Hiding Extended Dimensions Using the Show Parameter](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## Hiding Extended Dimensions Using the Hidden Parameter {#section-7167a6f6241a4bc78f2f322e048d65cf}

The Hidden parameter is an optional parameter that you can use when defining extended dimensions in [!DNL Transformation Dataset Configuration] files.

1. Open [!DNL Transformation Dataset Configuration] files in which the extended dimension that you want to hide is defined. See [Editing Existing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077). 

1. Locate the Hidden parameter for the desired dimension in the configuration window and type *true*. 
1. Save the file locally, then save it to the appropriate profile on the server. See [Editing Existing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077).

The dataset retransforms, after which the extended dimension does not appear on the dimension menu in data workbench. For more information about the Hidden parameter, see [Extended Dimensions](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

If you change the Hidden parameter's setting, you must retransform the dataset for the change to take effect.

## Hiding Extended Dimensions Using the Show Parameter {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

The Show parameter is not one of the parameters available for defining extended dimensions in [!DNL Transformation Dataset Configuration] files. Instead, the parameter is defined in the [!DNL .dim] files for any derived dimensions that you create. Therefore, to use the Show parameter to hide an extended dimension, you first must create a derived dimension that is based on the extended dimension as described in the following procedure:

1. Use a text editor such as Notepad to create an empty file called <*dimension name*>.dim The file name should match the name of the dimension that you want to hide. For example, to hide the Next Page dimension, you would create a [!DNL Next Page.dim] file. 

1. Add the following text to the file:

    * entity = ref: wdata/model/dim/Parent/+name 
    * show = bool: false

1. Save the file to the profile's Dimensions directory. You can save the file to a subdirectory if desired.

When you use the Show parameter to hide an extended dimension, you do not have to retransform your dataset to make the change take effect. You can choose to hide or show the dimension in your local version of the profile (that is, you can save the [!DNL .dim] file to your User folder), or you can save the [!DNL .dim] file to the server for use by other users of the profile.

You also can use the Show parameter to hide metrics and filters. For information, see the Configuring Interface and Analysis Features chapter in the *Data Workbench User Guide*.
