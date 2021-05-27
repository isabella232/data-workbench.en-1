---
description: Steps to define extended dimensions.
title: Defining Extended Dimensions
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
---
# Defining Extended Dimensions{#defining-extended-dimensions}

Steps to define extended dimensions.

1. While working in your dataset profile, open the [!DNL Profile Manager] and click **[!UICONTROL Dataset]** to show its contents.
1. Open the [!DNL Transformation.cfg] file or the [!DNL Transformation Dataset Include] file in which you want to define the extended dimension.

    * (Recommended) To open a dataset include file, see [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

      >[!NOTE]
      >
      >Adobe recommends defining extended dimensions in one or more new [!DNL Transformation Dataset Include] files. For more information, see [Creating New Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e).

    * To open the [!DNL Transformation.cfg] file, see [Editing the Transformation Configuration File](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc).

1. Right-click **[!UICONTROL Transformations]** and click **[!UICONTROL Add new]** > *< **[!UICONTROL Extended dimension type]**>*.
1. Input the appropriate information for your extended dimension. For descriptions of the transformation types and information about their parameters, see the following sections:

    * [Countable Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8) 
    * [Simple Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181) 
    * [Many-to-Many Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998) 
    * [Numeric Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed) 
    * [Denormal Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489) 
    * [Time Dimensions](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

       For any extended dimension that you define, you can add one or more comment lines to the Comments parameter to further describe the dimension or add notes about its use. To add a comment, right-click the **[!UICONTROL Comments]** label and click **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**. 
    
1. After you have defined your extended dimension(s) in the configuration file, save the file locally and save it to your dataset profile on the data workbench server.
