---
description: Open Best Fit Attribution from the Premium menu and follow these steps to build a Best Fit Attribution model.
title: Build a Best Fit Attribution Model
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
---

# Build a Best Fit Attribution Model{#build-a-best-fit-attribution-model}

Open Best Fit Attribution from the Premium menu and follow these steps to build a Best Fit Attribution model.

See an overview of [Best Fit Attribution](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1).

1. Open **Best Fit Attribution**.

   Open a workspace and click **[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**.

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >Best Fit Attribution is an Adobe Analytics Premium feature that requires you to enable Premium in your Profile. It requires you to update your certificate and add the Premium profile to your profile.cfg file. See [DWB Server upgrade: 6.2 to 6.3](https://docs.adobe.com/content/help/en/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html) for DWB 6.3.

1. Set the **[!UICONTROL Success]** metric. 

   >[!NOTE]
   >
   >You can either drag a metric from a **[!UICONTROL Finder]** table to the left pane of the Attribution visualization, or select from the **Inputs** menu.

   Click **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. The metric menu will open. ![](assets/attrib_set_success_metric.png)

   Select a metric that identifies a successful conversion. 

1. (optional) Set the **Revenue** metric.

   Set a metric to evaluate revenue across the conversion process. 

1. Set the **Touch** metric. 

   >[!NOTE]
   >
   >Setting a Touch Metric is only required if you are trying to build Success metrics automatically by dragging dimension elements onto the visualization.

   Click the **[!UICONTROL Inputs]** menu and select **Set Touch**, or drag a metric from the Finder. ![](assets/attrib_set_touch.png)

   This will be used to derive channel metrics when dimension elements are used as inputs. 

1. Set a **Success** window.

   Click [!DNL Inputs > Success Window]. Select a date range from a table and then name the Success window. Click **[!UICONTROL Workspace Selection]** and the selected dates will be assigned as the range of time for the Success metric. 

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >Since the Success window is a workstation selection, you can include any dimension(s) to your Success window.

1. Set a **[!UICONTROL Touch Window]**.

   Click [!DNL Inputs > Touch Window]. Select a date range from a table and then name the Touch window. Click **[!UICONTROL Workspace Selection]** and the selected dates will be assigned as the range of time for the Success metric.

   ![](assets/attrib_set_touch_window.png)

   By default, the **Touch** window will be set to the same time period as the **[!UICONTROL Success]** window. 

1. (optional) Set a Training Filter.

   You can also specify a **Training Filter** in the workspace to filter visitor data.

   >[!NOTE]
   >
   >In setting both the Success and Touch windows, you can apply the Training filter to the current workspace selections to further limit your data.

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >The training set is always drawn from visitors who satisfy the Success window. By filtering using the Filter Editor, you can create a subset of visitors reported in the Success window.

1. Specify channel metrics that represent touches.

   Either drag metrics to the visualization, or choose them from the [!DNL Inputs] > [!DNL Add Channel] menu. If you do not already have metrics defined for campaigns or channels, but do have dimensions representing channels, the visualization can build them for you automatically with the specification of a Touch metric.

   For example, with the Touch metric set to [!DNL Hits], and given a [!DNL dimension] called [!DNL Media Type] with elements that include things like [!DNL Email], [!DNL Press Release], [!DNL Print Ad], and [!DNL Social Media], the visualization will generate Channel metrics of the form [!DNL Hits where Media Type = Email] when you drag and drop the element(s) onto the visualization. 

1. Press **Go**.

   The Best Fit Analysis process will run, and a chart will display attributions per channel based on the selected inputs.

   >[!NOTE]
   >
   >Right-click **Model Complete** on the completed analysis to see statistics for the attribution model.

   ![](assets/attrib_visualization.png)

When complete, a graph will display an attribution model calculated per channel, and a distribution of the *Revenue* metric (if set). The model can be saved internally or exported to other systems.

>[!NOTE]
>
>**[!UICONTROL Streaming]**, **[!UICONTROL Online]** and **[!UICONTROL Offline]** modes produce different effects when building an attribution model based on the latency of the data being evaluated. In Streaming mode, the detail **[!UICONTROL Model Complete]** message will display. In Online and Offline modes, the detail **[!UICONTROL Local Model Complete]** will display.

## Options menu {#section-22288867f6c8483a8a38410f4b948346}

The **Options** menu provides advanced features to set up and display Best Fit Attribution analysis. 

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Options menu </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Set Training Filter </span> </td> 
   <td colname="col2"> The Training Filter is used with the Success Window to filter the population when building the attribution model. This will provide a subset of data that includes only the visitors that you want to analyze. <p>Note: Experienced users can also leverage the flexibility of filters to focus beyond the time line of the Success and Touch Windows. For example, in addition to selecting a time range, you can select a set of <i>Referring Domains</i> to only examine the attribution for users from those domains. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Show Complex Filter Description </span> </td> 
   <td colname="col2"> Displays the filter code for the Training Filter, Success Window, and Touch Window. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Save Model </span> </td> 
   <td colname="col2"> Saves the current attribution model for future use. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Load Model </span> </td> 
   <td colname="col2"> Opens a previously saved attribution model. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Presentation View </span> </td> 
   <td colname="col2"> Hides the top menu bar for presentation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Options &gt; Advanced</b> includes features to set the training set size and specify the approach to take in the case of a class imbalance. </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> Advanced &gt; Training Set Size </span> </td> 
   <td colname="col2"> <p>Sets the training set size. </p> <p>Note:  The default training size is Large for 250,000 visitors. </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Tiny = 50,000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">Small = 75,000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">Normal = 100,000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">Large = 250,00 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">Huge = 500,000 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Advanced &gt; Class Balance </b> </td> 
   <td colname="col2"> <p>Identifies and defines the number of input records to generate for a class imbalance issue based on dataset size. </p> </td> 
  </tr> 
 </tbody> 
</table>

|  Reset and Remove options  | Description  |
|---|---|
| **[!UICONTROL Reset Model]** |From the **[!UICONTROL Reset]** menu, select **[!UICONTROL Reset Model]** to clear the visualization but keep input metrics.  |
| **[!UICONTROL Reset All]** |From the **[!UICONTROL Reset]** menu, select **[!UICONTROL Reset All]** to clear the visualization and the input metrics.  |
| **[!UICONTROL Remove]** |Right-click on any input and select **[!UICONTROL Remove]** to clear the metric from the selected input.  |
| **[!UICONTROL Remove All]** |Right-click on *Channels* and select **[!UICONTROL Remove All]** to clear all input metrics.  |

