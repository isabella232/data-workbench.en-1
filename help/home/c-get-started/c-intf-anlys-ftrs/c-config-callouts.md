---
description: Callouts bring attention to a particular dimension element by creating a new visualization with a virtual selection of a particular dimension element in a visualization.
title: Configure a callout
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
---
# Configure a callout{#configure-a-callout}

Callouts bring attention to a particular dimension element by creating a new visualization with a virtual selection of a particular dimension element in a visualization.

 You can add or edit callouts by configuring the callout files stored in a Profiles\*profile name*\Context\Callout folder of the [!DNL Server] installation folder. Callouts that bring attention to a particular metric in a worksheet visualization are called metric callouts. Metric callout files are stored in the Profiles\*profile name*\Context\Metric Callout folder.

For instructions to add a callout or metric callout to a visualization, see [Adding Callouts to a Workspace](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**To create a new type of callout**

1. In any workspace, create a visualization containing the data that you want to appear in the new callout type. For example, if you want your callout to be a table, you create a table visualization showing the desired metric and dimension. 
1. Right-click the top border of the callout window and click **[!UICONTROL Save]**. 
1. In the [!DNL Save] window, click ![](assets/btn_folder_up.png), double-click **[!UICONTROL Context]**, then double-click **[!UICONTROL Callout]**. In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. The callout file is saved to the User\*working profile name*\Context\Callout folder.

   >[!NOTE]
   >
   >When naming your callout, choose a descriptive name that reflects the visualization type and the metric and dimension that it shows. For example, if you want to create a callout from a table visualization showing the Sessions metric over the Day dimension, you could name the callout “Sessions by Day Table.”

1. (Optional) To make this change available to all users of the working profile:

    1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types. 
    
    1. Right-click the check mark next to the file name of the new callout in the [!DNL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

**To change a callout to a metric callout**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. This folder contains all of the visualization files ( [!DNL .vw]) that define the existing callout types. 

1. Right-click the check mark next to the file name of the type of callout that you want to change and click **[!UICONTROL Make Local]**. After the file has been downloaded to the local computer, a check mark appears in the [!DNL User] column. 

1. Right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**. 

1. Locate the [!DNL metric_y = ref:] entry in the callout file and replace the existing value with the word Metric. The highlighted text in following file fragment shows where you insert this word. 

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Click **[!UICONTROL File]** > **[!UICONTROL Save As]**. In the **[!UICONTROL Save As]** window, click once, then double-click **[!UICONTROL Metric Callout]**. In the [!DNL File Name] field, type a name for the file and click **[!UICONTROL Save]**. The metric callout file is saved to the User\*working profile name*\Context\Metric Callout folder. 

1. (Optional) To make this metric callout available to all users of the working profile, in the [!DNL Profile Manager], right-click the check mark next to the file name in the [!DNL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.
