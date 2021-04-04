---
description: By default, newly created tabs display the subfolders within the associated directory as hierarchical, drop-down subdirectories instead of as subtabs.
solution: Analytics
title: Display subfolders as subtabs
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
---
# Display subfolders as subtabs{#display-subfolders-as-subtabs}

By default, newly created tabs display the subfolders within the associated directory as hierarchical, drop-down subdirectories instead of as subtabs.

You can display subfolders as subtabs (as shown in the following example) by placing an [!DNL empty folder.useTabs] file in the *working profile name*\Workspaces\*tab name folder* within the Data Workbench installation directory.

The following example shows the [!DNL Custom] tab with drop-down subdirectories.

![](assets/client-sub.png)

If you place an [!DNL empty folder.useTabs] file in the Workspaces\Custom folder, all of the subfolders within the Custom folder display in the [!DNL Worktop] as subtabs, as shown in the following example:

![](assets/client-sub2.png)

**To display subfolders as subtabs in the [!DNL Worktop]**

>[!NOTE]
>
>Each directory level must have a [!DNL Tab Name.useTabs] file for the contents of the subfolder to appear as subtabs instead of hierarchical, drop-down subdirectories.

1. In the [!DNL Profile Manager], click **[!UICONTROL Workspaces]** to view its contents. 
1. In the *working profile name* column, right-click the check mark for one of the [!DNL folder.useTabs] files and click **[!UICONTROL Copy]**. 
1. Right-click in the [!DNL User] column for the Workspaces\*tab name* folder and click **[!UICONTROL Paste]**. The subfolders within that tab now display as subtabs. 
1. (Optional) To make this change available to all users of the working profile, right-click the white check mark for the [!DNL new folder.useTabs] file in the [!DNL User] column and click **[!UICONTROL Save to]** > < **[!UICONTROL working profile name]**>.
