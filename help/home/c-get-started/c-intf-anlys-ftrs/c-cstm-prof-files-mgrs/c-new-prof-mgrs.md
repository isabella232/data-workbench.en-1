---
description: The Profile Manager displays all of the directories associated with your working profile.
solution: Analytics
title: Create a Profile Manager
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
---

# Create a Profile Manager{#create-a-profile-manager}

The Profile Manager displays all of the directories associated with your working profile.

You may want to access a subdirectory of the [!DNL Profile Manager] without having to navigate its entire directory structure. For example, the [!DNL Metrics] and [!DNL Workspaces] menu options available on the [!DNL Manage] menu of the workspace window menu enable you to open the Profile Manager Metrics and Workspaces folders, respectively.

For more information about the [!DNL Profile Manager], see [The Profile Manager](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-prof-mgr.md#concept-2c8f60cc84d044bfb57ddf947b1db263).

By default you have access to the following managers:

* **[!DNL Metrics Manager]:** Displays the contents of the Profile Manager’s Metrics folder. You can open, edit, remove, or copy the metrics defined within each profile. 
* **[!DNL Reports Manager]:** Displays the contents of the Profile Manager’s Reports folder. You can open, edit, remove, or copy report workspaces or [!DNL report.cfg] files. 

* **[!DNL Workspaces Manager]:** Displays the contents of the Profile Manager’s Workspaces folder. All of the files for configuring the [!DNL Worktop]’s tabs are located here. See [Customizing Worktop Tabs](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md#concept-0f1e6061b03949199326dc6df71a52bc).

Data Workbench enables you to create additional profile managers that display one subdirectory from the [!DNL Profile Manager]. Each manager that you create must have a [!DNL .vw] file that specifies the [!DNL Profile Manager] directory whose contents it shows and the properties of that window. You can use the [!DNL .vw] file for any of the provided managers as a template.

**To create a Profile Manager**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
1. Within the Menu directory, click the **[!UICONTROL Admin]** directory and then the **[!UICONTROL Profile]** directory. The [!DNL .vw] files for the existing managers are located here. 
1. In the *profile name* column, right-click the check mark for the one of the [!DNL .vw] files (for example, [!DNL Workspaces.vw]), then click **[!UICONTROL Make Local]**.

   A check mark for the file appears in the [!DNL User] column. 

1. Right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 
1. In the [!DNL Profile Path] field, type the [!DNL Profile Manager] directory for which you want to create a new manager. Be sure to include the slash (/) after the directory name.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the edited file to the *Data Workbench installation folder*\User\*working profile name*\Menu\Admin\Profile Management.

   Be sure to change the name of the [!DNL .vw] file to reflect the directory in the [!DNL Profile Manager] to which it corresponds. 

1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > < **[!UICONTROL working profile name]**>.

