---
description: The Geography profile provided with data workbenchGeography is an internal profile that provides additional functionality to your Adobe application.
title: Installing the Geography Profile
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
---
# Installing the Geography Profile{#installing-the-geography-profile}

The Geography profile provided with data workbenchGeography is an internal profile that provides additional functionality to your Adobe application.

 As with all other internal profiles provided by Adobe, the [!DNL Geography] profile should not be changed. All customization must occur in your dataset or role-specific profiles or other profiles that you create.

The [!DNL Geography] profile includes several transformation dataset include files (located in the [!DNL Dataset\Transformation\Geography] folder) that define geographical dimensions. Following is a list of the transformation dataset include files provided with the [!DNL Geography] profile:

* [!DNL City.cfg] 
* [!DNL Coordinates.cfg] 
* [!DNL Country.cfg] 
* [!DNL DMA.cfg] 
* [!DNL Domain.cfg]

Each of the files is named for the extended dimension that it defines. An additional file, [!DNL IPLookup.cfg], defines several geographical data fields that are used to define dimensions in the other transformation dataset include files.

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

**To install the [!DNL Geography] profile on the data workbench server**

>[!NOTE]
>
>The following installation instructions assume that you have installed data workbench and established a connection between data workbench and the data workbench server on which you are installing data workbench [!DNL Geography]. If you have not done so, see the *Data Workbench User Guide*.

1. Open the Profiles folder from the [!DNL .zip] file provided to you by Adobe.
1. Copy the [!DNL Geography] folder to the Profiles folder in your data workbench server installation directory. You want to end up with a [!DNL ...\Profiles\Geography] folder on your data workbench server as shown in the following example. The names of the other folders within the Profiles folder may differ from the ones shown.

   ![Step Info](assets/Geo_installProfiles_dir.png)

1. Use the following steps to update the [!DNL profile.cfg] file for each profile with which you want to use data workbench [!DNL Geography].

    1. Open the [!DNL Profile Manager]. 
    1. Right-click the check mark next to [!DNL profile.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 
    
    1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] window appears. 
    
    1. In the [!DNL profile.cfg] window, right-click **[!UICONTROL Directories]** and click **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

       To add the new directory to the end of the list of directories, right-click the number or name of the last directory in the list and click **[!UICONTROL Add new]** > **[!UICONTROL Directory]**. 
    
    1. Type the name of the new directory: [!DNL Geography]. 
    1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
    
    1. In the [!DNL Profile Manager], right-click the check mark for [!DNL profile.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*.

       >[!NOTE]
       >
       >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL Geography] profile), as your changes are overwritten when you install updates to these profiles.
