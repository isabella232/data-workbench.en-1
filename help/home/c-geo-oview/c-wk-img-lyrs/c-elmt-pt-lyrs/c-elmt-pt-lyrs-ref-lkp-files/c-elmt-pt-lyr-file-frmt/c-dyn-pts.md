---
description: When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.
seo-description: When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.
seo-title: Defining Element Point Layers Using Dynamic Points
solution: Analytics
title: Defining Element Point Layers Using Dynamic Points
topic: Data workbench
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
---

# Defining Element Point Layers Using Dynamic Points{#defining-element-point-layers-using-dynamic-points}

When creating an element point layer using dynamic points, the latitude and longitude data is embedded in each element of the dimension.

To define an element point layer using dynamic points, you must create or already have available the following:

* **A dimension**, defined in the [!DNL Transformation.cfg] file or a transformation dataset include file, in which each element contains the string “latitude,longitude” or “latitude,longitude,name.”

  For steps to create a dimension, see the *Dataset Configuration Guide*. 

* **A layer file** that specifies the related dimension.

  For more information about the required format of the layer file, see [Element Point Layer File Format](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>When using [!DNL Dynamic Points], it is essential to ensure that the cardinality of the dimension specified in the layer file is reasonable. If every row of a dataset has a different latitude and longitude, the dimension quickly fills up and most rows fall into a Small Elements element. Because the Small Elements element does not have a latitude and longitude, it does not appear on the globe.

## Element Point Layer File Format {#section-bbcc2baa2f754dba81eba93339a97cbd}

Each element point layer file using dynamic points must be formatted using the following template: 

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <desc> 
  <b>Element Point Layer Parameters: Dynamic Points </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2"> <p>The name of the dimension (defined in a transformation configuration file), which must contain elements with the string “latitude,longitude” or “latitude,longitude,name” as shown in the following examples: 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126,Somewhere </li> 
     </ul> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Metric </td> 
   <td colname="col2"> The name of the metric that is evaluated over the dimension specified in the Dimension parameter. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dynamic Points </td> 
   <td colname="col2"> Enables Dynamic Points. Set to true. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> Optional. Value used to size the points in the layer. The default value is 100. Larger values make the points bigger, and smaller values make them smaller. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Optional. The RGB color vector, which is expressed as (red,green,blue). For each color in the vector, you can enter a value from 0.0 to 1.0. For example, (1.0, 0.0, 0.0) is bright red, and (0.5, 0.5, 0.5) is gray. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Rendering Mode </td> 
   <td colname="col2"> <p>Optional. Integer value representing the rendering mode to use for the layer. The three available modes are as follows: 
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">Rendering Mode 1. Points size is defined in screen space (points stay a constant size relative to the computer screen). Points are rendered using polygons, so there is no upper limit on point size. This is the default rendering mode. </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">Rendering Mode 2. Point size is defined in world space (points stay a constant size relative to the globe). Points are rendered using polygons, so there is no upper limit on point size. </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">Rendering Mode 3. Point size is defined in screen space. Points are rendered using OpenGL smooth points. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL IP Coordinates.layer] file is formatted as follows:

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```

