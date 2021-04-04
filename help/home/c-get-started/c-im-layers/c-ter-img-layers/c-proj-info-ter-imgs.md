---
description: Data workbench supports both latitude-longitude projections and Universal Transverse Mercator (UTM) projections for all terrain image layer sources.
solution: Analytics
title: Specify projection information for terrain images
topic: Data workbench
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
---
# Specify projection information for terrain images{#specify-projection-information-for-terrain-images}

Data workbench supports both latitude-longitude projections and Universal Transverse Mercator (UTM) projections for all terrain image layer sources.

 Projection information is required for raw unprojected bitmaps and general images, unprojected. You can specify projection information for images with embedded projection information, though it is usually not required because the parameters of the projection are determined automatically from geodetic data embedded in the image itself. The following sections provide details about specifying these projection formats in the [!DNL Terrain Images.cfg] file.

## Latitude-Longitude Projections {#section-6e335357ec28462ba39c565e0a5986c7}

The latitude-longitude projection format (LatLonProjection) in the [!DNL Terrain Images.cfg] file is defined by four parameters for latitude and longitude.

To specify a LatLonProjection for unprojected images (raw unprojected bitmaps and general images, unprojected), you can enter settings for the LatLonProjection within the [!DNL Terrain Images.cfg] window in Data Workbench.

To specify a LatLonProjection for images with embedded projection information, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to LatLonProjection, and add settings for the [!DNL LatLonProjection].

**To specify a LatLonProjection for unprojected images**

1. Open the [!DNL Terrain Images.cfg] file in Data Workbench and add a terrain image layer source as described in [To define a terrain image layer](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f). 
1. Edit the Projection Info parameters using the following parameters table as a guide:

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>The latitude of the top edge of the image, in degrees, where 90 is the North Pole and -90 is the South Pole. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>The latitude of the bottom edge of the image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>The longitude of the left-hand edge of the image, in degrees, where positive numbers are east and negative numbers are west longitudes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>The longitude of the right-hand edge of the image. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**. 
1. To save the locally made changes to the Data Workbench server computer, in the [!DNL Server Files Manager], right-click the check mark for [!DNL Terrain Images.cfg] in the [!DNL Temp] column, then click **[!UICONTROL Save to]** > *< **[!UICONTROL server name]**>*.

**To specify a LatLonProjection for images within embedded projection information**

In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. The [!DNL Terrain Images.cfg] file is located within this directory.

Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg].

Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] file appears in a Notepad window.

Edit the Projection Info parameters using the following sample file fragment as a guide. Be sure to specify the projection type as highlighted below. For descriptions of the parameters, see the LatLonProjection Parameters table in the previous procedure.

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## Universal Transverse Mercator Projections {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

The Universal Transverse Mercator (UTM) projection is defined by eight parameters. When specifying a Universal Transverse Mercator projection for a terrain image layer, your terrain image files must be aligned with false (projected) north towards the top of the image, and false east to the right of the image.

To specify a UTM projection for any terrain image source, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to “TransverseMercatorProjection”, and add settings for the UTM projection.

**To specify a Universal Transverse Mercator projection**

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. The [!DNL Terrain Images.cfg] file is located within this directory. 
1. Right-click the check mark in the server name column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg.] 
1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg] file appears in a Notepad window. 
1. Edit the Projection Info parameters using the following sample file fragment and parameters table as guides. Be sure to specify the projection type as highlighted below.

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axis </p> </td> 
   <td colname="col2"> <p>The parameters of the ellipsoid used for the projection. The semimajor axis is specified in meters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Easting </p> </td> 
   <td colname="col2"> <p>The false easting of the central meridian of the projection, in meters. For UTM, this is always 500,000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Northing </p> </td> 
   <td colname="col2"> <p>The false northing of the equator in the projection, in meters. For UTM, this is 0 for northern hemisphere zones and 10,000 for southern hemisphere zones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Northwest Corner Coordinates, Southeast Corner Coordinates </p> </td> 
   <td colname="col2"> <p>The coordinates (in projected meters) of the top left and bottom right corners of the image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>The longitude of the central meridian of the projection, specified in degrees east of Greenwich. Negative numbers may be used to specify degrees west. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scale Factor </p> </td> 
   <td colname="col2"> <p>The ratio of the radius of the projection cylinder to the semimajor axis of the ellipsoid. For Universal Transverse Mercator (UTM) projections, this is always 0.9996. </p> </td> 
  </tr> 
 </tbody> 
</table>
