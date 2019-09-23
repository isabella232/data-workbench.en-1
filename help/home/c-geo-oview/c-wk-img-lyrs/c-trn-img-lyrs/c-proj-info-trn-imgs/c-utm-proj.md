---
description: The Universal Transverse Mercator (UTM) projection is defined by eight parameters.
seo-description: The Universal Transverse Mercator (UTM) projection is defined by eight parameters.
seo-title: Universal Transverse Mercator Projections
solution: Analytics
title: Universal Transverse Mercator Projections
topic: Data workbench
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
---

# Universal Transverse Mercator Projections{#universal-transverse-mercator-projections}

The Universal Transverse Mercator (UTM) projection is defined by eight parameters.

 When specifying a Universal Transverse Mercator projection for a terrain image layer, your terrain image files must be aligned with false (projected) north towards the top of the image, and false east to the right of the image.

To specify a UTM projection for any terrain image source, you must open the [!DNL Terrain Images.cfg] file in a text editor such as Notepad, set the Projection Info parameter to “TransverseMercatorProjection”, and add settings for the UTM projection.

**To specify a Universal Transverse Mercator projection**

1. In the [!DNL Server Files Manager], click **[!UICONTROL Components]** to view its contents. The [!DNL Terrain Images.cfg] file is located within this directory. 

1. Right-click the check mark in the *server name* column for [!DNL Terrain Images.cfg], then click **[!UICONTROL Make Local]**. A check mark appears in the [!DNL Temp] column for [!DNL Terrain Images.cfg]. 

1. Right-click the newly created check mark in the [!DNL Temp] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. The [!DNL Terrain Images.cfg]file appears in a Notepad window. 

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

|  Parameter  | Description  |
|---|---|
|  Ellipsoid Inverse Flattening, Ellipsoid Semimajor Axis  | The parameters of the ellipsoid used for the projection. The semimajor axis is specified in meters.  |
|  False Easting  | The false easting of the central meridian of the projection, in meters. For UTM, this is always 500,000.  |
|  False Northing  | The false northing of the equator in the projection, in meters. For UTM, this is 0 for northern hemisphere zones and 10,000 for southern hemisphere zones.  |
|  Northwest Corner Coordinates, Southeast Corner Coordinates  | The coordinates (in projected meters) of the top left and bottom right corners of the image.  |
|  Prime Meridian  | The longitude of the central meridian of the projection, specified in degrees east of Greenwich. Negative numbers may be used to specify degrees west.  |
|  Scale Factor  | The ratio of the radius of the projection cylinder to the semimajor axis of the ellipsoid. For Universal Transverse Mercator (UTM) projections, this is always 0.9996.  |

