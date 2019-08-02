---
description: Formatting information about the element point layer file.
seo-description: Formatting information about the element point layer file.
seo-title: Element Point Layer File Format
solution: Analytics
title: Element Point Layer File Format
topic: Data workbench
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
index: y
internal: n
snippet: y
---

# Element Point Layer File Format{#element-point-layer-file-format}

Formatting information about the element point layer file.

Each element point layer [!DNL .layer] file that references a lookup file must be formatted using the following template: 

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <desc> 
  <b>Element Point Layer Parameters: Lookup Files </b> 
 </desc> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Data Paths </td> 
   <td colname="col2"> Path to the lookup file containing latitude and longitude data. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Longitude Column </td> 
   <td colname="col2"> The name of the column in the lookup file containing the longitude data. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Latitude Column </td> 
   <td colname="col2"> The name of the column in the lookup file containing the latitude data. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Name Column </td> 
   <td colname="col2"> Optional. The name of the column in the lookup file containing the names of the locations represented by the latitude and longitude data. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Key Column </td> 
   <td colname="col2"> <p>The name of the column in the lookup file containing the common key data, which enables the data workbench server to integrate the data in the lookup file into the dataset. This must be the first column in the lookup file. </p> <p>Each row in this column is an element of a dimension. This dimension must be defined in the <span class="filepath"> Transformation.cfg</span> file or a transformation dataset include file and specified in the Dimension parameter of this file. For more information about transformation configuration files, see the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">The name of the dimension (defined in a transformation configuration file) containing elements that correspond to the data rows in the <span class="wintitle"> Key</span> column. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Metric </td> 
   <td colname="col2"> The name of the metric that is evaluated over the dimension specified in the Dimension parameter. </td> 
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
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">Rendering Mode 1. Points size is defined in screen space (points stay a constant size relative to the computer screen). Points are rendered using polygons, so there is no upper limit on point size. This is the default rendering mode. </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">Rendering Mode 2. Point size is defined in world space (points stay a constant size relative to the globe). Points are rendered using polygons, so there is no upper limit on point size. </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">Rendering Mode 3. Point size is defined in screen space. Points are rendered using OpenGL smooth points. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

The [!DNL Zip Points.layer] file is formatted as follows:

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```

