---
description: Data Workbench 6.2 release notes include new features, upgrade requirements, bug fixes, and known issues.
seo-description: Data Workbench 6.2 release notes include new features, upgrade requirements, bug fixes, and known issues.
seo-title: Data Workbench 6.2 Release Notes
title: Data Workbench 6.2 Release Notes
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
---

# Data Workbench 6.2 Release Notes{#data-workbench-release-notes}

Data Workbench 6.2 release notes include new features, upgrade requirements, bug fixes, and known issues.

To view previous features and fixes based for each past release, see the [release note archives](https://marketing.adobe.com/resources/help/en_US/insight/insight_release_notes_prev.pdf).

## New Features {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2 includes these new features: 

<table id="table_E28A6D31E7D941F7A0C2048F0F0F7838"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Features </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><a href="../../../home/c-release-notes-insight/c-release-notes-insight-62/c-6-2-features/c-ui-upgrades-6-2.md#concept-56e61b50ffc44c57acceaee45a6efbfc"> Data Workbench Client UI updates </a> </td> 
   <td colname="col2">Data Workbench 6.2 includes new user interface features: 
    <ul id="ul_19CD7706B5C046178C8C496D5E05CA62"> 
     <li id="li_97A386C80ACF49878CBA5C81A3619BA3"><a href="http://marketing.adobe.com/resources/help/en_US/insight/client/?f=c_bookmark_about" format="http" scope="external"> New bookmarks panel </a> </li> 
     <li id="li_63CF3372E811495D91FA405F460CB020"><a href="../../../home/c-release-notes-insight/c-release-notes-insight-62/c-6-2-features/c-ui-upgrades-6-2.md#section-c108bbd1661249e79c146727ff3d2470"> New icons in the workspace toolbar</a> </li> 
     <li id="li_17CB20AC740242DB8D717E5260D52BA1"><a href="../../../home/c-release-notes-insight/c-release-notes-insight-62/c-6-2-features/c-ui-upgrades-6-2.md#section-9129c340c21d45a3864c923884cd4382"> Position objects in the workspace within a screen</a> </li> 
     <li id="li_B296EDDF9B8249F8A0A485EB41B6256D"><a href="../../../home/c-release-notes-insight/c-release-notes-insight-62/c-6-2-features/c-ui-upgrades-6-2.md#section-d8322f72423f437aa2e34f2188b1341c"> New quick keys to change workspace views</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="http://marketing.adobe.com/resources/help/en_US/insight/client/c_decision_trees.html"> Decision Trees</a> </td> 
   <td colname="col2"> Decision trees are a predictive analytics visualization used to evaluate visitor characteristics and relationships. The Decision Tree Builder generates a decision tree visualization based on a specified positive case and a set of inputs. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../home/c-release-notes-insight/c-release-notes-insight-62/c-6-2-features/c-query-panels.md#concept-8906c8e39d80495585928f29e0e88d01"> Finders</a> </td> 
   <td colname="col2">Use Finder panels in Data Workbench to select metrics, dimensions, and filters. These panels provide search support, sorting options, and drag and drop capabilities. <p> <p>Note:  With the new Finder panels, you can export a list of your Dimensions, Metrics, and Filters to an MS Excel spreadsheet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c"> Update to Binary Filter in Correlation Matrix </a> </td> 
   <td colname="col2"> The Binary Filter has been updated with new features, requiring you to rebuild any Correlation Matrix with a Binary Filter built in previous versions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="http://marketing.adobe.com/resources/help/en_US/insight/client/c_density_map.html"> Density Map</a> </td> 
   <td colname="col2"> The density map is a visualization that displays elements as shaded rectangles within a square map. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="http://marketing.adobe.com/resources/help/en_US/insight/client/c_rules_attrib.html"> Attribution Profile </a> </td> 
   <td colname="col2"> To quickly analyze attribution values (events to attribute responsibility for a successful conversion or sale), Data Workbench provides a rules-based Attribution profile with features for the Architect to set up the Attribution reports and the Analyst to run the reports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="../../../home/c-get-started/c-template-report-types.md#concept-f4346d6fb5c34484ad0eca95b7791e42"> Analytic Reports</a> </td> 
   <td colname="col2"> Report templates standardize Adobe Analytics' reports for users of the data workbench who utilize the Adobe SC profile. These reports are identical to reports employed in Marketing Reports &amp; Analytics (formerly SiteCatalyst). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><a href="http://marketing.adobe.com/resources/help/en_US/insight/client/c_3d_scatterplots.html"> 3D Scatter Plots </a> </td> 
   <td colname="col2"> A 3D Scatter Plot graphs the elements of a data dimension (such as Days or Referral Site) on a three-dimensional grid where the x, y, and z axes represent various metrics. </td> 
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

* The Attribution profile is configured for users who have implemented the Adobe SC profile to employ the Analytics (SC/Insight) data feed. By default, the Marketing and Conversion events are employed as the default interactions evaluated in the rules-based models. See [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy) for additional information. 
* For users of the Adobe SC profile upgrading to Data Workbench 6.2, if you are not using the default configurations, verify that the [!DNL x-bot_id] value in the [!DNL SC Fields.cfg] file is being decoded properly and that the [!DNL x-bot_id] field is listed properly in the [!DNL Decoding Instructions.cfg] and the [!DNL Exclude Hit.cfg] files. This will only be an issue if you have modified the configuration file from the default configuration. 

* If you have deleted unused fields in the [!DNL Dataset > Log Processing > SC Fields.cfg] file for the Adobe SC profile, you will need to update to accommodate updated field values used for the Attribution profile (see [Deploying the Attribution Profile](http://marketing.adobe.com/resources/help/en_US/insight/whatsnew/?f=c_attrib_profile_deploy)).

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

