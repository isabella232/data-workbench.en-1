---
description: The new dimensions that you create using Data Workbench (referred to as derived dimensions) are client-side dimensions.
solution: Analytics
title: Work with derived dimensions
topic: Data workbench
uuid: 3a955fdc-6666-40ab-aee0-bd23c260c009
exl-id: 5b7e3a2a-ac61-4186-ad6c-234edf68af3e
---
# Work with derived dimensions{#work-with-derived-dimensions}

The new dimensions that you create using Data Workbench (referred to as derived dimensions) are client-side dimensions.

 Instead of defining these dimensions during the dataset construction and update process (in the [!DNL Transformation.cfg] file) on your Data Workbench server computers, derived dimensions are created and stored individually as [!DNL .dim] files in a profile. As a result, you can change existing and create new derived dimensions without reprocessing your dataset.

>[!NOTE]
>
>For more information about dimensions than is provided in this section, see the appropriate Data Workbench application guide.

For more information about the dataset configuration and update process, see the *Dataset Configuration Guide*.

## Create a derived dimensions {#section-fd9b6ca13a8f4aa9bbc2fff3ef15cb76}

To create a derived dimension, you can either copy and modify an existing dimension or save a dimension from a visualization.

## Create a derived dimensions from an existing dimension {#section-f46c2d3ab0a5416c98d6e79d18d99fa1}

Users most often want to create new time dimensions from existing ones. For example, you can create a new “Last 5 Days” dimension from the existing “Last 7 Days” dimension.

1. In the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for a dimension that is similar to the dimension that you want to create and click **[!UICONTROL Copy]**.

   For example, to copy the [!DNL Last 7 Days.dim] from the Reporting folder of the [!DNL Traffic] profile, you right-click the check mark for the file name in the [!DNL Traffic] column and click **[!UICONTROL Copy]**.

   ![](assets/vis_ProfMgr_CopyDimension.png)

1. Right-click in the [!DNL User] column for the folder in which you want to store the copied dimension and click **[!UICONTROL Paste]**.

   The dimension appears in the selected Dimensions folder with a check mark in the [!DNL User] column. 

1. To rename the new dimension, right-click its check mark in the [!DNL User] column and type the new name in the [!DNL File] field. 
1. From the right-click menu, click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The defining parameters for the dimension appear. 
1. Modify the parameters as needed to define the new dimension.

   For time dimensions, you most likely need to modify only the Count and Range parameters. 

1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the dimension that you created, you must upload it to the profile using the [!DNL Profile Manager]. For more information, see [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

You now can use the new dimension throughout the current profile by selecting it as you would any built-in dimension.

## Save a dimension from a visualization {#section-84cfe5e9ccb640afa2ee4e2da2682757}

You can save extended dimensions from process maps and segments. For steps to save a dimension from a process map, see [Saving Dimensions from Process Maps](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051). For steps to save a segment dimension, see [Creating Segment Dimensions](../../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e) on page 82.

## Saving a segment as a dimension {#section-7c443cf1ac5a44659623cabb9e0c1ab8}

You also can save defined segments as a dimension. For steps, see [Reusing a Segment Visualization](../../../../home/c-get-started/c-analysis-vis/c-seg/c-reuse-seg-vis.md#concept-a8a607bd415d404a83c32a26b804cbdc).

## Edit an existing derived dimension {#section-3a82c604bf1c4d369770556d268808b2}

1. I

   n the [!DNL Profile Manager], in the *profile name* column, right-click the check mark for the dimension file that you want to edit and click **[!UICONTROL Make Local]**. 
1. Right-click the check mark for the dimension file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 
1. Complete the parameters as needed. For more information, contact Adobe Consulting Services. 
1. To save the file, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

   If you would like all users of a profile to use the modified dimension, you must upload it to the profile using the [!DNL Profile Manager]. For more information, see [Publishing Files to Your Working Profile](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
