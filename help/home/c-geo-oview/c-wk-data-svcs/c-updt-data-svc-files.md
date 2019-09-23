---
description: If you subscribe to either data service, you periodically must update the data service files provided by Adobe.
seo-description: If you subscribe to either data service, you periodically must update the data service files provided by Adobe.
seo-title: Updating Data Service Files
solution: Analytics
title: Updating Data Service Files
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
---

# Updating Data Service Files{#updating-data-service-files}

If you subscribe to either data service, you periodically must update the data service files provided by Adobe.

 To do so, you must have access to the files on the data workbench server.

To load [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] data files, you must complete the following procedures.

## Replacing the Data File {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. In data workbench, on the [!DNL Admin] > [!DNL Dataset and Profile] tab, click the **[!UICONTROL Servers Manager]** thumbnail to open the [!DNL Servers Manager] workspace. 

1. Within the [!DNL Servers Manager] window, right-click the icon of the data workbench server onto which you want to load the files and click **[!UICONTROL Server Files]**. 

1. In the [!DNL Server Files Manager], right-click in the **[!UICONTROL Temp]** column for **[!UICONTROL Lookups\IP Geo-location]** or **[!UICONTROL Lookups\IP Geo-intelligence]** and click **[!UICONTROL Open]** > *< **[!UICONTROL folder]**>*. 

1. Copy the [!DNL .bin] data file provided by Adobe to the Lookups\IP Geo-location or Lookups\IP Geo-intelligence folder window. 
1. Save the file to the data workbench server machine by right-clicking the [!DNL Temp] column for the data file and clicking **[!UICONTROL Save to]** > *< **[!UICONTROL server name]**>*.

   If you are running a cluster, upload the files to the master data workbench server in the cluster.

## Updating the IPLookup Transformation {#section-a8b99afe3eb04afabe88e15bd465f935}

1. In the [!DNL Profile Manager], click **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**, and **[!UICONTROL Geography]**. 

1. Right-click the check mark next to [!DNL IP Lookup.cfg] and click **[!UICONTROL Make Local]**. A check mark for this file appears in the [!DNL User] column. 

1. Right-click the new check mark and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. A transformation configuration window appears. 

1. In the window, click **[!UICONTROL Transformation]**, then click **[!UICONTROL Transformations]**. 

1. Locate and click either **[!UICONTROL IPLookup Quova]** or **[!UICONTROL IPLookup Digital Envoy]**. 

1. For the File parameter, update the name of the file to match the name of the new data ( [!DNL .bin]) file provided by Adobe. 
1. Save the transformation configuration file by right-clicking **[!UICONTROL (modified)]** at the top of the configuration window and clicking **[!UICONTROL Save]**. 

1. Save the modified configuration file to each profile that uses the data service by right-clicking the check mark next to [!DNL IP Lookup.cfg] in the [!DNL User] column and clicking **[!UICONTROL Save to]** > *< **[!UICONTROL profile name]**>*. Retransformation of the data begins after synchronization of the dataset profile.

   For information about retransformation of your dataset, see the Reprocessing and Retransformation chapter of the *Dataset Configuration Guide*.

   >[!NOTE]
   >
   >Do not save the modified configuration file to any of the internal profiles provided by Adobe (including the [!DNL IP Geo-location] or [!DNL IP Geo-intelligence] profile), as your changes are overwritten when you install updates to these profiles.

If you installed the [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data service for version 5.1 or later, you have completed the data service update. However, if you installed the [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data service prior to version 5.1, you must complete the following additional procedures.

## Replacing the Lookup File {#section-ced1efa38a76419d812edd35423dbff7}

You should complete the following steps only if you installed the [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data service prior to version 5.1.

1. In the [!DNL Server Files Manager], click either **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** or **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**, then click **[!UICONTROL Maps]** to view its contents. 

1. Right-click in the **[!UICONTROL Temp]** column for **[!UICONTROL Maps]** and click **[!UICONTROL Open]** > *< **[!UICONTROL folder]**>*. 

1. Copy the new [!DNL .txt] file provided by Adobe to the Maps folder window. 
1. Save the file to the data workbench server machine by right-clicking the check mark in the [!DNL Temp] column for the [!DNL .txt] file and clicking **[!UICONTROL Save to]** > *< **[!UICONTROL server name]**>*.

>[!NOTE]
>
>If you are running a cluster, upload the files to the master data workbench server in the cluster.

## Updating the Layer Files {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>You should complete the following steps only if you installed the [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data service prior to version 5.1.

Complete these steps for every layer ( [!DNL .layer]) file that references the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] lookup ( [!DNL .txt]) file.

1. In the Profiles\*data service name*\Maps folder within the data workbench server installation directory, open the [!DNL .layer] file in a text editor such as Notepad. 

1. In the [!DNL Data Paths] vector, update the name of the [!DNL .txt] lookup file to match the name of the new [!DNL .txt] file provided by Adobe, as shown highlighted in the following file sample: 

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. Save the updated layer file. 
1. Repeat Steps 2 and 3 for every [!DNL .layer] file that references the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] [!DNL .txt] file.

