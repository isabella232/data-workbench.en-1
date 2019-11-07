---
description: These steps apply only to creating submenus and menu items for the Workspace Window menu.
solution: Analytics
title: Create a workspace menu and menu item
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
---

# Create a workspace menu and menu item{#create-a-workspace-menu-and-menu-item}

These steps apply only to creating submenus and menu items for the Workspace Window menu.

You can customize the metric and dimension menus by creating new folders and new derived metrics and dimensions. For more information, see [Creating and Editing Derived Metrics](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) and [Creating and Editing Derived Dimensions](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**To create a new workspace window menu**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
1. In the [!DNL User] column for the Menu directory, click **[!UICONTROL Create]** > **[!UICONTROL Folder]**. A folder named New Folder appears in the [!DNL File] column for [!DNL Menu].

   >[!NOTE]
   >
   >You also can create a new folder for any subdirectory within the Menu directory.

1. Rename the new folder by right-clicking in the [!DNL User] column for the folder and typing the new name in the Dir parameter. 
1. Add the desired files to the new folder. 
1. (Optional) In the [!DNL User] column for the new folder, click **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   An [!DNL order.txt] file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column. 

1. (Optional) Edit the [!DNL order.txt] file as needed. See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999). 
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for the folder in the [!DNL User] column and click **[!UICONTROL Save Directory to]** > *< **[!UICONTROL working profile name]**>*.

**To add a new menu item to an existing menu**

1. Complete one of the following steps:

    * Create a new item (visualization, annotation, and so on) to add to a menu:

        1. Open a workspace in Data Workbench and create the desired item. 
        1. Save the item to the following directory:

           *Data workbench installation directory*\User\*working profile name*\Work 
        
        1. In the [!DNL Profile Manager], click the **[!UICONTROL Work]** directory to view its contents. 
        1. In the [!DNL User] column, right-click the check mark for the desired file and click **[!UICONTROL Copy]**. 
        1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**.

           A copy of the file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column.

    * Copy and paste an existing item from one menu (folder) to another:

        1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents. 
        1. In the *working profile name* column, right-click the check mark for the desired file and click **[!UICONTROL Make Local]**. 
        1. Right-click the check mark for the file in the [!DNL User] column and click **[!UICONTROL Copy]**. 
        1. In the [!DNL User] column for the desired folder, click **[!UICONTROL Paste]**. A copy of the file appears in the [!DNL File] column for the new folder, and a check mark for the new file appears in the [!DNL User] column.

1. (Optional) Edit the [!DNL order.txt] file as needed. See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999). 
1. (Optional) To make the changes available to all users of the working profile, right-click the white check mark for each file in the [!DNL User] column and click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*. 
1. (Optional) To avoid having a menu item appear in multiple menus, you should delete the corresponding file from its original folder by right-clicking the check mark for the file in the *working profile name* column and clicking **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Repeat this step for the file’s check mark in the [!DNL User] column.

