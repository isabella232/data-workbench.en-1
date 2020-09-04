---
description: Data Workbench 6.2 release notes include new features, upgrade requirements, bug fixes, and known issues.
title: Data Workbench 6.2 Release Notes
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
---

# Data Workbench 6.2 Release Notes{#data-workbench-release-notes}

Data Workbench 6.2 release notes include new features, upgrade requirements, bug fixes, and known issues.

## New Features {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2 includes these new features:

| Features | Description |
|--- |--- |
|Decision Trees|Decision trees are a predictive analytics visualization used to evaluate visitor characteristics and relationships. The Decision Tree Builder generates a decision tree visualization based on a specified positive case and a set of inputs.|
|Update to Binary Filter in Correlation Matrix|The Binary Filter has been updated with new features, requiring you to rebuild any Correlation Matrix with a Binary Filter built in previous versions.|
|Density Map|The density map is a visualization that displays elements as shaded rectangles within a square map.|
|Attribution Profile|To quickly analyze attribution values (events to attribute responsibility for a successful conversion or sale), Data Workbench provides a rules-based Attribution profile with features for the Architect to set up the Attribution reports and the Analyst to run the reports.|
|Analytic Reports|Report templates standardize Adobe Analytics' reports for users of the data workbench who utilize the Adobe SC profile. These reports are identical to reports employed in Marketing Reports & Analytics (formerly SiteCatalyst).|
|3D Scatter Plots|A 3D Scatter Plot graphs the elements of a data dimension (such as Days or Referral Site) on a three-dimensional grid where the x, y, and z axes represent various metrics.|


## Data Workbench Client UI Updates{#data-workbench-client-ui-updates}

Data Workbench 6.2 includes new user interface updates to the bookmarks panel, new icons in the workspace toolbar, the ability to drag the workspace within a screen, new quick keys, and updates to the pie chart visualization.

## New Bookmark Features {#section-e361b605441540ca8213c3fddb5e0718}

You can now bookmark significant workspaces to quickly move between visualizations and reports employed in your workflow.

**Working with Bookmarks**

1. Bookmark a workspace by clicking the Bookmark icon ![](assets/bookmark_icon.png) in the upper right corner of the toolbar. 
1. Click **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** in the left pane to open a list of bookmarks.

   ![](assets/bookmarks_panel.png)

1. To open a bookmarked workspace, click a workspace name in the **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   The selected workspace will open. When you click another bookmarked workspace, the previous workspace will close and the newly selected workspace will open, allowing you to quickly navigate through your workflow.

**To delete a bookmark:**

* In the Bookmark Panel, right-click and select **Remove `<bookmark title>`** to delete a selected bookmark, or select **[!UICONTROL Clear All Bookmarks]** to delete all bookmarks. 

* You can also right-click on the workspace in the thumbnail view within the worktop and select **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* 25 bookmarks can be saved. 
>* If you add a bookmark and then move the location of the workspace, the bookmark will be invalid and must be deleted from the Bookmark Panel and reset. 
>

## New Icons in Workspace {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 now replaces the text in the workspace with icons. You can still hover over and see the tool tip message identifying the icon, including **[!UICONTROL File]**, **[!UICONTROL Add]**, and **[!UICONTROL Export]**.

![](assets/new_icons.png)

A new **[!UICONTROL Help]** icon is added to access the documentation and other knowledge centers, including the following links: 

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Documentation links </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Marketing Reports &amp; Analytics </td> 
   <td colname="col2">Open to the <span class="uicontrol"> Adobe Marketing Reports &amp; Analytics</span> help page. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">Open to the <span class="uicontrol"> Idea Exchange login</span>. This online portal allows users to provide update changes and enhancement ideas to data workbench. These customer-focused ideas can then be voted on by all users. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Help </td> 
   <td colname="col2">Open the <span class="uicontrol"> Data Workbench documentation</span>. <p>You can also press <span class="uicontrol"> &lt;F1&gt;</span> to open help within a workspace. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> About </td> 
   <td colname="col2">Open to identify the <span class="uicontrol"> client version</span> of data workbench. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>You can also press `<F1>` to open the documentation from a workspace.

## Drag Workspace Views {#section-9129c340c21d45a3864c923884cd4382}

If a workspace is larger than the viewable screen, you can move the view to see all elements within the workspace. You can click in the background (outside of the visualizations and tables) and drag the screen to move the viewable area within the workspace. The cursor will change to a hand icon when dragging the view within the workspace frame.

![](assets/drag_workspace.png)

## Quick Keys to Change Workspace Views {#section-d8322f72423f437aa2e34f2188b1341c}

New quick keys let you resize and refit workspaces between window and full page views. 

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Commands </th> 
   <th colname="col2" class="entry"> Quick Keys </th> 
   <th colname="col3" class="entry"> Combined menu commands </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Full screen view</b>. Workspace fills the screen and refits to the new size. </td> 
   <td colname="col2"><b>Ctrl plus</b> <p>Ctrl + (on keypad) </p> <p><i>or</i> </p> <p>Ctrl Shift + (on keyboard) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">File &gt; Page Size &gt; Fill Screen <p><i>followed by</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">File &gt; Refit Workspace </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Window view</b>. Workspace displays in a standard window view and refits to the new size. </td> 
   <td colname="col2"><b>Ctrl minus</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">File &gt; Page Size &gt; Standard <p><i>followed by</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">File &gt; Refit Workspace </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Bug Fixes {#section-8704a9ac358246cd81233dd0982d534f}

* Updated the Visual Site lookup file to address search engine changes to the query search term. 
* Fixed inaccurate error message, "Failed to import workspace", when importing a workspace in the client workstation even though the import was successful. 
* Workstation connection error displaying "412 Configuration Conflict" message is now replaced with user friendly message that identifies system action. 
* The "post" command can now be executed in Report Server. 
* Fixed user interface errors in client user interface for Simplified Chinese. 
* Adobe Analytics updated the data feed that powers Data Workbench to take advantage of Profiles and Audiences that integrates with the Adobe Experience Cloud. All Data Workbench users were required to prepare their environment for this transition by April 21, 2014.

  Profiles and Audiences was introduced to provide a complete view of customers across Adobe Analytics. This new service is available within the Adobe Experience Cloud to drive further value across analytics tools to start establishing the foundation for these features within Analytics. The new Experience Cloud visitor identifier will be added to the data feed, along with other enhancements and improvements to adapt to the new data feed and global visitor identifier. 
* When importing a workspace, an error message is displayed even though the import was successful.

## Upgrade Requirement {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* The Attribution profile is configured for users who have implemented the Adobe SC profile to employ the Analytics (SC/Insight) data feed. By default, the Marketing and Conversion events are employed as the default interactions evaluated in the rules-based models.  
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. This will only be an issue if you have modified the configuration file from the default configuration. 

* If you have deleted unused fields in the **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile.

## Known Issues {#section-dbb307639835493a83409f5f461932b8}

* When 3D Scatter Plot Visualization includes callouts, the zoom may display plots outside the border of the visualization.

  Workaround: Zoom the 3D Scatter Plot first and then add callouts to your visualization. 
* Dragging metric from Finders panel to Metric Legend outside of the metric column will delete the Metric Legend from the workspace.

  Workaround: Users that wish to drag metrics to the Metric Legend should drop in the first column (metrics column). 
* Print Workspace using Sidebar and Both options will not include the Copyright information on the printed page. 
* Using Workstation in remote desktop session will crash when renaming workspaces. 
* (In Simplified Chinese version) Actual report outputs are valid in Report Server but email subject lines and attachment file names are garbled. 
* (In Simplified Chinese version) When using word wrap in the Worksheet visualization, localized words are not being wrapped correctly resulting in junk characters added to the string. 
* (In Simplified Chinese version) Unable to launch Insight.exe if the installation directory is named with non-English characters.

  Workaround: Keep default names or rename using only English characters in the folder path to launch executables.

