---
description: The Server Files Manager displays all of the directories in the Data Workbench server installation directory, including configuration and look-up files.
seo-description: The Server Files Manager displays all of the directories in the Data Workbench server installation directory, including configuration and look-up files.
seo-title: Create a Server Files Manager
solution: Analytics
title: Create a Server Files Manager
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
---

# Create a Server Files Manager{#create-a-server-files-manager}

The Server Files Manager displays all of the directories in the Data Workbench server installation directory, including configuration and look-up files.

 You may want to access a portion of the [!DNL Server Files Manager] without having to navigate its entire directory structure or display only a few of the subdirectories to address a particular need. For example, you might want to create a separate [!DNL Server Files Manager] that displays only the Access Control and Users subdirectories, enabling you to manage your users and their access.

Each manager that you create must have a [!DNL .vw] file. You can use the [!DNL Server Files.vw] file as a template.

For more information about the [!DNL Server Files Manager], see [The Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**To create a Server Files Manager**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory, then the **[!UICONTROL Admin]** directory. The [!DNL Server Files.vw] file is located here. 
1. In the *profile name* column, right-click the check mark for the [!DNL Server Files.vw] file and click **[!UICONTROL Make Local]**. A check mark for the file appears in the [!DNL User] column. 
1. Right-click the check mark for the [!DNL Server Files.vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Server Files.vw] file opens. 
1. To remove a directory, right-click the top border of the [!DNL Server Files Manager] and click **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *< **[!UICONTROL directory name]**>*. 
1. To add a directory, right-click the top border of the [!DNL Server Files Manager], click **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Type the directory’s URI in the URI field, and click **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >You can designate multiple directories in the URI field. For example, if you type [!DNL Profiles\Marketing\], the server files manager contain the Marketing subdirectory, but no other subdirectory within the Profiles directory.

1. Right-click the top the top border of the [!DNL Server Files Manager] and click **[!UICONTROL Save]**. 
1. To create a new manager, change the file name in the [!DNL File Name] field, then click **[!UICONTROL Save]**. To overwrite the existing manager, click **[!UICONTROL Save]**. 
1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column.

   Then, click **[!UICONTROL Save to]** > *< **[!UICONTROL working profile name]**>*.

