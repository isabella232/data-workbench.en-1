---
description: The data service profiles (IP Geo-intelligence and IP Geo-location) are internal profiles that provide additional functionality to your Adobe application.
solution: Analytics
title: Installing the Data Service Profile
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
---
# Installing the Data Service Profile{#installing-the-data-service-profile}

The data service profiles (IP Geo-intelligence and IP Geo-location) are internal profiles that provide additional functionality to your Adobe application.

 As with all other internal profiles provided by Adobe, these profiles should not be changed. All customization must occur in your dataset or role-specific profiles or other profiles that you create.

The data service profiles include the following dataset include files to be installed on a data workbench server:

* **Profiles\*profile name*\Dataset\Log Processing\Traffic\IP.cfg:** Lists the c-ip field to be passed from log processing to transformation. 
* **Profiles\*profile name*\Dataset\Transformation\Geography\IPLookup.cfg:** Defines an IPLookup transformation that produces several fields of geographical data using the provided IP Geo-intelligence or IP Geo-location lookup file.

For information about transformation dataset include files, see the *Dataset Configuration Guide*.

In addition, each data service profile provides you with an element point layer file named [!DNL IP Coordinates.layer]. This layer file enables you to map locations in your dataset on the globe dynamically using IP addresses. After installation, the layer is stored in the Profiles\*data service name*\Maps folder within the data workbench server installation directory.

The [!DNL IP Coordinates.layer] file references the Coordinates dimension, which is defined in the [!DNL Coordinates.cfg] file provided with the [!DNL Geography] profile and located in the Dataset\Transformation\Geography folder. Each element of the Coordinates dimension defined in your dataset is mapped on the globe using the latitude and longitude information contained in that element. For more information about element point layers that use dynamic points, see [Defining Element Point Layers Using Dynamic Points](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

>[!NOTE]
>
>If you installed the IP Geo-intelligence and IP Geo-location data service prior to version 5.1, your element point layer file references a lookup file instead of using dynamic points. Each layer file references the IP Geocodes lookup file and the IP Geocode dimension. The IP Geocodes lookup file contains a list of IP geocodes (geographical locations based on IP address) and the latitude and longitude for each. Each element of an IP Geocode dimension defined in your dataset is mapped on the globe using the latitude and longitude listed for that IP geocode in the IP Geocodes lookup file.

The name of the layer file and the files that it references differ for each data service:

* The [!DNL IP Geocodes D.layer] file is installed with the IP Geo-intelligence (Digital Envoy) profile. This element point layer references the [!DNL IP Geocodes D yyyymmdd.txt] lookup file (which you need to update periodically) and the IP Geocode D dimension. 

* The [!DNL IP Geocodes Q.layer] file is installed with the IP Geo-location (Quova) profile. This element point layer references the [!DNL IP Geocodes Q yyyymmdd.txt] lookup file (which you need to update periodically) and the IP Geocode Q dimension.

For more information about element point layers that use lookup files, see [Defining Element Point Layers Referencing Lookup Files](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f).

## To install the IP Geo-intelligence or IP Geo-location profile {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>The following installation instructions assume that you have installed data workbench and established a connection between data workbench and the data workbench Server on which you are installing data workbench [!DNL Geography]. If you have not done so, see the *Data Workbench User Guide*.

1. Open the Profiles folder from the [!DNL .zip] file that you received from Adobe. 
1. Copy the IP Geo-intelligence or IP Geo-location folder to the Profiles folder in your data workbench server installation directory. You want to end up with a ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. The names of the other folders within the [!DNL Profiles] folder may differ from the ones shown.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Use the following steps to update the [!DNL profile.cfg] file for each profile with which you want to use the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] profile.

    1. Open the **[!UICONTROL Profile Manager]**. 
    1. Right-click the check mark next to [!DNL profile.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 
    
    1. Right-click the newly created check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL profile.cfg] window appears. 
    
    1. In the [!DNL profile.cfg]window, right-click **[!UICONTROL Directories]** and click **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

       To add the new directory to the end of the list of directories, right-click the number or name of the last directory in the list and click **[!UICONTROL Add new]** > **[!UICONTROL Directory]**. 
    
    1. Type the name of the new directory: [!DNL IP Geo-intelligence] or I [!DNL P Geo-location]. 
    
    1. Right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**. 
    
    1. In the [!DNL Profile Manager], right-click the check mark for [!DNL profile.cfg] in the [!DNL User] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.
