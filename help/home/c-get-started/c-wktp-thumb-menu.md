---
description: How to export, copy, and bookmark from the Worktop.
title: Using the Worktop thumbnail menu
uuid: bada2260-3ae7-4fb6-938a-40b7acb1ffa7
exl-id: 2220051d-5c53-48ed-8e13-62883819f22a
---
# Using the Worktop thumbnail menu{#using-the-worktop-thumbnail-menu}

How to export, copy, and bookmark from the Worktop.

Right-click a Workspace to export, copy, and bookmark functions from the Worktop.

![](assets/thumbnail_menu.png)

## Interface descriptions {#section-fd027dd94b7d4cb6b933d70c08ccd3e2}

The following elements are available in the [!DNL Worktop] thumbnail menu:

**Server workspace:** *name*

Appears only for unedited server workspaces. Identifies the named workspace as the same as the workspace stored on the server.

**Date:** *day and time*

The date and time the workspace was last opened.

**Local version of:** *name*

Appears only for local versions of server workspaces. Identifies the named workspace as an edited, local version of a workspace stored on the server.

**User workspace:** *name*

Appears only for user workspaces. Identifies the named workspace as a workspace that exists only on the local machine.

**Compute in Background**

Appears only when working online. Keeps the queries in the selected workspace running in the background while you continue working. When selected, the thumbnail displays the following information, which indicates the progress of the queries:

* Working: *n%* - indicates that the query is processing and the percentage of the processing that is complete. 
* *n* MB Query Load - total size of the query result. Query Load is proportional to the total memory load of your Data Workbench server, but does not correlate directly. As a guideline, a 10 MB or higher query load may strain your system. The query load listed does not take clustering into account.

  >[!NOTE]
  >
  >If Compute in Background remains selected, the queries in the selected workspace becomes standing queries, continuing to be updated and use memory load. Make sure to deselect Compute in Background when you are finished working in the workspace.

**Export to Excel**

Export workspace data to table in Microsoft Excel (.xls and .xslx files). When exporting a workspace to Excel, Data Workbench exports data from certain visualizations, dimension and value legends, and text annotations to a new Excel workbook with one visualization per worksheet.

**Export to Excel Template**

Export to an Excel template (.xltx).

**Copy**

Copies the workspace. For more information about pasting a copied workspace, see [Copying and Pasting Existing Workspaces](../../home/c-get-started/c-work-worksp/c-create-worksp.md#section-f91ae89b845640c9a4a52820a6110e65).

**Revert to server version**

Appears only for local versions of server workspaces. Deletes the local copy of this workspace. The original remains on the server.

**Delete**

Appears only for user workspaces. Deletes the user workspace, which exists only on the local machine. For information about deleting workspaces from the connected Data Workbench server, see [Deleting Files from Your Working Profile](../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b).

**Save to server**

Appears only for local versions of server workspaces and user workspaces and works only for those users with the appropriate permissions. Saves the local copy of the workspace to the server. By default, workspaces are saved to the appropriate working `<profile name>\Workspaces\<tab name>` folder.

**Bookmark**

Bookmark a workspace to quickly retrieve later.

A bookmark icon ![](assets/bookmark_icon.png) will appear above the workspace on the worktop and the name of the workspace will appear in the Bookmark panel. ![](assets/bookmark_worktop.png)
