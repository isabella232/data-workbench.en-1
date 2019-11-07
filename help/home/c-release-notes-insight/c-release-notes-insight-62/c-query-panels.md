---
description: Use Finder panels in Data Workbench to select metrics, dimensions, and filters. These panels provide search support, sorting options, and drag and drop capabilities.
solution: Analytics
title: Finders
topic: Data workbench
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
---

# Finders{#finders}

Use Finder panels in Data Workbench to select metrics, dimensions, and filters. These panels provide search support, sorting options, and drag and drop capabilities.

A Finder panel can be opened in the left sidebar or within a workspace.

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimensions Finder </th> 
   <th colname="col2" class="entry"> Metrics Finder </th> 
   <th colname="col3" class="entry"> Filters Finder </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A list of all dimensions in your query model. </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>A list of all metrics in your query model. </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>A list of all filters created for your organization. </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**To open a Finder:**

* Right-click in a workspace and select **[!UICONTROL Tools]** > **[!UICONTROL Finder]**.

  The Finder pane with tabs for Metrics, Dimensions, and Filters will open in the workspace. 

* Right-click in the left sidebar and select **[!UICONTROL Add]** > **[!UICONTROL Finder]**.

  The Finder pane will open in the left panel.

The **Finder** includes the following features: 

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Finder Features </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Drag and drop</b> </td> 
   <td colname="col2"> <p> You can drag and drop dimensions or metrics from the panel to a visualization in the workspace to change the dimension or add new metrics. </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">Hold down the <span class="uicontrol"> &lt;Ctrl&gt;</span> and <span class="uicontrol"> &lt;Alt&gt;</span> keys and select the dimension or metric from the Finder panel. </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">Drag a new dimension from the pane and drop it to the visualization to change or add dimensions. </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">To add metrics, drag a new metric from the pane and drop it on the metric header of the selected visualization. </li> 
    </ol> <p>This will work for all relevant visualizations, including tables, visitor cluster, correlation matrix, scatter plots, and the 2-D bar graph (depending on the axis). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Search</b> </td> 
   <td colname="col2">A <span class="uicontrol"> Search</span> box in the Finder panels lets you filter names for Dimensions, Metrics, and Filters. 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>Pattern matching (simple glob search). Start typing the name of a required dimension, metric, or filter entity in the Search field and only matching strings contained anywhere in the name will be filtered and displayed in the Finders pane. </p> <p>For example, enter: </p> <code><b>Search:</b>click</code> <p>You could get the following results in the Dimensions Finder: </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>Standard pattern matching lets you use the wildcard characters, such as . (dot), "?" , and "*" (star). </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>Regular expressions. More complex regular expressions are also supported for added search capability. Add the prefix "re:" before your search term (no spaces) to interpret as a regular expression. </p> <p>For example, enter: </p> <code><b>Search:</b>re.*ip</code> <p>You could get the following results in the Dimensions Finder: </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>For in-depth search information, see <a href="http://marketing.adobe.com/resources/help/en_US/insight/dataset/c_reg_exp.html" format="http" scope="external"> regular expressions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Dimension Type</b> </td> 
   <td colname="col2">In the Dimension tab, you can right-click on the tab heading to sort by the type of dimension. <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">Attributes—Dimensions built based on characteristics of the visitor, products, geography, time, video, and other attributes. </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">Clusters—Dimensions built within the cluster builder. </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">Scores—Dimensions built within the propensity scoring. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Label</b> </td> 
   <td colname="col2">In each tab, you can right-click and select <span class="uicontrol"> Label</span> to rename the Finder pane. <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>The default Dimensions, Metrics, and Filters labels can be changed to a tab name that meets your organization's conventions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Add Item</b> </td> 
   <td colname="col2">In each tab, you can right-click and select <span class="uicontrol"> Add Item</span> to open a table and manually add Dimensions, Metrics and Filters. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Finders bar</b> </td> 
   <td colname="col2">Right-click in the <span class="uicontrol"> Finders</span> bar in the left sidebar to open a menu for additional features. <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">Right-click in the <span class="uicontrol"> Finders</span> bar and select <span class="uicontrol"> Close</span> to close a Finders pane. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Save</b> </td> 
   <td colname="col2">Save the list locally by right-clicking in the header bar and selecting the <span class="uicontrol"> Save</span> option. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Export</b> </td> 
   <td colname="col2">You can export a list of selected dimensions, metrics, or filters from the Finder panel by right-clicking in the Finders bar and selecting <span class="uicontrol"> Export</span> from the menu. <p> Add a name and export to Microsoft Excel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Copy</b> </td> 
   <td colname="col2"> Copy a list of Dimensions, Metrics, or Filters. You can copy as a file or as a graphic in Dark Background, Light Background, or Monochrome. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Minimize</b> </td> 
   <td colname="col2"> Minimize the Finder pane. Only the Finders bar will appear. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Borderless</b> </td> 
   <td colname="col2"> Displays a pane with no border lines for Finders in the workspace (but not in the left sidebar). </td> 
  </tr> 
 </tbody> 
</table>

