---
description: To create a segment dimension, you begin by making a selection within a workspace and then adding the segment to a visualization.
title: Create a segment dimensions
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
---
# Create a segment dimensions{#create-a-segment-dimensions}

To create a segment dimension, you begin by making a selection within a workspace and then adding the segment to a visualization.

 **To create a segment dimension**

1. Add a segment visualization to the workspace. For example:

   ![](assets/vis_Segment.png)

1. Add visualizations to your workspace that you want to use to define your segment, then make the desired selections to define your segment. 
1. In the segment visualization, right-click the label of the segment after which you want the new segment to be added and click **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >To create a new first segment, right-click the **[!UICONTROL Segments]** label and click **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   A new segment (named New Segment) appears in the visualization. The Other segment represents all of the data not included in your defined segments: it is effectively the difference between your dataset data and your segment data. 

1. Right-click the newly created segment and click **[!UICONTROL Rename Segment]**. 
1. Type a descriptive name for your new segment in the name field.

   >[!NOTE]
   >
   >If a metric value, such as a particular visitor in [!DNL Site], meets the criteria of multiple segments, the metric value is included in only the first listed segment that it matches.

**To save the segment dimension**

1. Right-click the Segments label and click **[!UICONTROL Save Dimension]**. The [!DNL Save Dimension As] window appears. The default save location is the User\*profile name*\Dimensions folder. 
1. In the [!DNL File name] field, type a descriptive name for the segments that you are saving as a dimension and click **[!UICONTROL Save]**.

You can access the segment dimension whenever you are working with a visualization. You also can export data associated with the elements in your saved dimension using the segment export feature.

For more information about the segment export feature and instructions to configure it for your needs, see [Configuring Segments for Export](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
