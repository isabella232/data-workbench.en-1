---
description: You can use the Profile Manager to download files that you want to modify.
solution: Analytics
title: Modify local files in the user profile
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
---
# Modify local files in the user profile{#modify-local-files-in-the-user-profile}

You can use the Profile Manager to download files that you want to modify.

 You might want to download a file to overwrite your existing, local file with the original version of the file or open, view, and modify files that cannot be accessed from the workspace menus.

**To download a file**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to download. 
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuration ( [!DNL .cfg]), dimension ( [!DNL .dim]), and metric ( [!DNL .metric]) files can be edited directly in a profile folder and saved to the server without making them local and separately saving them to the server. Simply right-click the check mark next to the name of the file and click **[!UICONTROL Open]** > **in workstation**.

After the file has been downloaded to the local computer, a check mark appears in the [!DNL User] column, which indicates that a local copy of the file resides in the User\*profile name* folder on your computer. Note that the check mark is the same color as the check mark in the *profile name* column. This indicates that the local file has the same Modified date and time as the file in the *profile name* folder.

**To modify the file**

1. Right-click the check mark next to the file name in the [!DNL User] column. 
1. Click one of the following menu options, depending on how you want to edit the file:

    * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** if you are editing a [!DNL .vw] file or a [!DNL .cfg] file in a workspace. 
    
    * **Open** > **in vw. Editor **if you are editing a .vw file to add new parameters. 
    
    * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** if you are opening a text file or need to add new parameters to a [!DNL .cfg] file. 
    
    * **[!UICONTROL Open]** > **[!UICONTROL folder]** if you want to open the folder in which the file is located on your computer

1. Edit the file as desired, then save the file.

In the [!DNL Profile Manager], note that the check mark in the [!DNL User] column for the file you edited has changed color. This indicates that the local file is now different from the version in the *profile name* folder. If necessary, you can publish the revised version of the file to the profile for use by other users working with this profile.
