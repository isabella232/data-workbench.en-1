---
description: Information about working with filter conditions including creating a new filter and adding a condition to a new filter.
title: Working with filter conditions
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
---
# Working with filter conditions{#working-with-filter-conditions}

Information about working with filter conditions including creating a new filter and adding a condition to a new filter.

## Create a filter {#section-70ba51ae625e493fa3ca70b93ffba406}

* Open a filter editor in your workspace by right-clicking **[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**.

  -or- 

* If you already have a filter editor open and a filter loaded, right-click the current filter’s name and click **[!UICONTROL New Blank Filter]**.

## Add a condition to a new filter {#section-50986db80f1148c489630a8a63fe9f28}

1. Create a new filter. Make sure that Design Filter is highlighted (as opposed to Apply Filter), indicating that you are working in Design Filter mode. 
1. Right-click within the area marked **[!UICONTROL Right-click to build filter]** and select one of the following options:

    * To create an inclusion filter, click **[!UICONTROL Include group with]**. 
    * To create an exclusion filter, click **[!UICONTROL Exclude group with]**.

1. Select the type of condition to add to the filter.

   The following table provides descriptions of the available filter condition types:

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Condition Type </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>workspace selection </p> </td> 
   <td colname="col2"> <p>Defines a filter condition based on the selections in the workspace. This option is available only if one or more selections exist within the workspace. </p> <p>To view more information about the selection, right-click the condition and click <span class="uicontrol"> View Details</span>. A callout appears for the condition. </p> <p>If you make another selection in the workspace, you can add the selection as a subcondition of the first selection. The selections are grouped together as logical ANDs. Therefore, the data that is included or excluded by the condition must satisfy all of the workspace selections. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>at least one </p> </td> 
   <td colname="col2">Defines a filter condition based on the existence of at least one (any) element of a dimension that you choose. To edit the condition, right-click the condition and click <span class="uicontrol"> Change</span> condition to. Click one of the available dimensions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>formula </p> </td> 
   <td colname="col2"> <p>Defines a filter condition based on the formula that you enter. You must use the appropriate syntax for the filter to work. </p> <p> <p>Note: For information about the syntax for defining filters, see <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Syntax for Filter Expressions</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>metric value </p> </td> 
   <td colname="col2"> <p>Defines a filter condition based on a metric value that you specify. </p> <p>To define the condition, follow these steps: 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">Right-click <span class="uicontrol"> [choose level]</span> &gt; <span class="uicontrol"> Change level</span> to select the level and metric from a list of dimensions in your dataset. </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">Right-click <span class="uicontrol"> [choose metric]</span> &gt; <span class="uicontrol"> Change metric</span> to select the metric from a list of metrics in your dataset. </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">Right-click less than and click <span class="uicontrol"> Change comparison</span> to select one of the available comparison conditions (less than, more than, exactly, at least, or at most). </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">Type the desired value for the metric. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>Defines a filter that lets you include or exclude a level with a specified dimension. For example, you might specify a first/last filter to include (or exclude): </p> <p>Sessions whose last Page View has a Page of <span class="filepath"> /hme/rts/Our Rates</span>. </p> <p>To define a First/Last condition: 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">Choose <span class="uicontrol"> Include group with</span> or <span class="uicontrol"> Exclude group with</span> &gt; <span class="uicontrol"> first/last</span> as a new condition in the Filter Editor. </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">Right-click <span class="uicontrol"> [choose container]</span> &gt; <span class="uicontrol"> Change container</span> to select the container. </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">Right click <span class="uicontrol"> first</span> or <span class="uicontrol"> last</span> to specify the level. </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">Right click to specify a dimension, then type a value into the available field. </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">Click <span class="uicontrol"> Apply</span>. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

   The filter in this example defines a first/last filter for users whose last page view was [!DNL /hme/rts/Our Rates]:

   ![](assets/client-fil2.png)

1. (Optional) To add more conditions to your filter, right-click within the area of the window where you are building your filter and select the type of filter (see Step 2) and the condition rule (see Step 3).

   >[!NOTE]
   >
   >Multiple inclusion conditions are grouped together as logical ORs. Therefore, the data included by the filter must satisfy at least one of the defined inclusion conditions. Multiple exclusion conditions also are grouped as logical ORs. To be excluded, data must satisfy at least one of the exclusion conditions.

The filter in this example defines a subset of data consisting of movie viewers (users) who rated lots of movies but did not give any one movie a high score (4 or 5). This filter (appropriately named Very Hard to Please) consists of two conditions:

* **A metric value condition:** The condition includes users who have rated at least 500 movies. 
* **A workspace selection condition:** The condition excludes users who gave any one movie a score of 4 or 5. The callout tells you that 4 and 5 were the elements selected from the Score dimension.

![](assets/vis_FilterEditor_ExampleMovies.png)

## Delete a filter condition {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>You can delete conditions only when you are working in Design Filter mode. If you have applied a filter to your workspace, you must click Design Filter to return to Design Filter mode before you can delete one or more of the filter’s conditions.

* Click the **x** to the left of the condition to delete it.

## Edit a condition description {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

You can add descriptions to each of the conditions that you add to a filter. You can edit or remove the descriptions as desired.

>[!NOTE]
>
>Descriptions of conditions appear only when you are working in Design Filter mode.

* Right-click the condition and click **[!UICONTROL Edit description]**.

    * To add or edit a description, type the description in the [!DNL Edit condition description] field. The description appears in quotation marks above the condition in the filter editor window.

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* To remove a description, click **[!UICONTROL Remove description]**. The condition remains in the filter editor window.
