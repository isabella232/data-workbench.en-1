---
description: The latitude-longitude projection format (LatLonProjection) in the Terrain Images.cfg file is defined by four parameters for latitude and longitude.
seo-description: The latitude-longitude projection format (LatLonProjection) in the Terrain Images.cfg file is defined by four parameters for latitude and longitude.
seo-title: Latitude-Longitude Projections
solution: Analytics
title: Latitude-Longitude Projections
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
index: y
internal: n
snippet: y
---

# Latitude-Longitude Projections{#latitude-longitude-projections}

The latitude-longitude projection format (LatLonProjection) in the Terrain Images.cfg file is defined by four parameters for latitude and longitude.

To specify a LatLonProjection for unprojected images (raw unprojected bitmaps and general images, unprojected), you can enter settings for the LatLonProjection within the [!DNL Terrain Images.cfg] window in data workbench. See [To specify a LatLonProjection for unprojected images](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

To specify a LatLonProjection for images with embedded projection information, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to “LatLonProjection”, and add settings for the LatLonProjection. See [To specify a LatLonProjection for images within embedded projection information...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [To Specify a LatLonProjection for Unprojected Images](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a) 
* [To Specify a LatLonProjection for Images Within Embedded Projection Information...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## To Specify a LatLonProjection for Unprojected Images {#section-26554eefe645481faba68396fa13756a}

1. Open the [!DNL Terrain Images.cfg] file in data workbench and add a terrain image layer source as described in [To define a terrain image layer](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf). 

1. Edit the Projection Info parameters using the following parameters table as a guide:

   |  Parameter  | Description  |
   |---|---|
   |  Lat0  | The latitude of the top edge of the image, in degrees, where 90 is the North Pole and -90 is the South Pole.  |
   |  Lat1  | The latitude of the bottom edge of the image.  |
   |  Lon0  | The longitude of the left-hand edge of the image, in degrees, where positive numbers are east and negative numbers are west longitudes.  |
   |  Lon1  | The longitude of the right-hand edge of the image.  |

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. 

1. To save the locally made changes to the data workbench server machine, in the [!DNL Server Files Manager], right-click the check mark for [!DNL Terrain Images.cfg] in the [!DNL Temp] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL server name]**>*.

## To Specify a LatLonProjection for Images Within Embedded Projection Information {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. The [!DNL Terrain Images.cfg] file is located within this directory. 

1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg]. 

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] file appears in a Notepad window. 

1. Edit the Projection Info parameters using the following sample file fragment as a guide. Be sure to specify the projection type as highlighted below. For descriptions of the parameters, see the LatLonProjection Parameters table in the previous procedure. 

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

