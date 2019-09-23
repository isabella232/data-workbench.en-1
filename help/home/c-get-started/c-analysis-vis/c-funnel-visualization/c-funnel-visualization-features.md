---
description: The Funnel visualization includes features to build a funnel with multiple dimensions, raw visitor numbers, percentage of visitors at each step, and separate scopes.
seo-description: The Funnel visualization includes features to build a funnel with multiple dimensions, raw visitor numbers, percentage of visitors at each step, and separate scopes.
seo-title: Funnel Features
solution: Analytics
title: Funnel Features
topic: Data workbench
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
---

# Funnel Features{#funnel-features}

The Funnel visualization includes features to build a funnel with multiple dimensions, raw visitor numbers, percentage of visitors at each step, and separate scopes.

Here are the basic features of the funnel visualization.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> First Element </td> 
   <td colname="col2"> First funnel step in the process. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Third Element </td> 
   <td colname="col2">Third funnel step in the process. <p><p>Note:  The selected elements do not have to be from the same dimension. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Fall-through Percentage </td> 
   <td colname="col2"> Percentage who completed the defined path displayed in three scopes. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Fallout Browser </td> 
   <td colname="col2">Fallout arrow. Right-click and select <span class="uicontrol"> Add Path Browser</span> to see what other path visitors took. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Percent Fallout </td> 
   <td colname="col2">Percentages that describe three scopes of fallout for users that did not complete the path. <p>Percentages are presented in three scopes: </p><p style="text-align: center;"><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" align="center" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> The percentage of fallout from the step previous to this step. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> The percentage of fallout from the first step in the funnel. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> The percentage of fallout based on the total number of visitors. </p></td> 
  </tr> 
 </tbody> 
</table>

## Funnel Steps {#section-96a6732558dd4740b73541844f06d3ef}

The disks in a funnel represent the steps in the navigation, the cones represent the fall-through from one step to the next, and the arrows represent the fallout. Clicking a cone will select the users who fell through at that point and include them in the current workspace filter. Clicking an arrow will select the visitors who fell out.

>[!NOTE]
>
>The Funnel visualization has a limit of eight steps that can be applied.

## Additional Funnel Features and Functionality {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Adjust the clip and level of the funnel**. Select the Funnel option from the Visualization menu. After the funnel is created, you can right-click on the title to adjust the clip and level to any countable metric in your system.

  ![](assets/funnel_path_browser_9.png)

* **Drag more elements**. Add more elements to your funnel by dragging and dropping them from the Dimension table to the funnel using the <Ctrl> + <Alt> keys. You can drag multiple steps at the same time from the Dimension table by selecting multiple items (using <Ctrl> + click) and then dragging them to the Funnel visualization using the <Ctrl> + <Alt> keys.. 
* **Delete a step**: Delete elements by right-clicking on the step in the visualization and clicking **Yes**.

  ![](assets/funnel_path_browser_4.png)

* **Rearrange the steps you have dragged to the funnel**. Simply click the step to select it and drag it to another position to rearrange the steps. 
* **Open a Path Browser**. You can see more detail about where customers fall through or fall out of the process through the [Add a Path Browser](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) feature. 

* **Add more steps**. You can add a maximum of eight steps to each funnel visualization. 
* **Change the metric**. The metric can be changed so the steps are counting visits or some other metric at each step. Available options vary by dataset. 
* **Display in a tabular view**. Right-click the title to display the Funnel Visualization menu and click **[!UICONTROL Show Tabular View]**. Once in tabular view, you can select **[!UICONTROL Show Graph View]** to return to graphic representation of the funnel. To open the Tabular View, right-click on the title and select Show Tabular View from the menu. 

* **Compare sequences**. An efficient way to compare two similar sequences is to display their two visualizations side-by-side. You can also display both the tabular view and the graph view side-by-side using the Duplicate feature. To open, right-click on the title and select Duplicate from the menu.

