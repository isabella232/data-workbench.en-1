---
description: When creating an element point layer that references a lookup file to obtain latitude and longitude data, the location of the point is obtained by retrieving each element and its associated latitude and longitude from the lookup file.
title: Define element point layers referencing lookup files
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
---
# Define element point layers referencing lookup files{#define-element-point-layers-referencing-lookup-files}

When creating an element point layer that references a lookup file to obtain latitude and longitude data, the location of the point is obtained by retrieving each element and its associated latitude and longitude from the lookup file.

>[!NOTE]
>
>Instead of using a lookup file, you can use the Dynamic Points functionality, which embeds the latitude and longitude of a location in the name of each element of a dimension. See [Defining Element Point Layers Using Dynamic Points](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

To define an element point layer that references a lookup file, you must create or already have available the following:

* **A dimension** defined in the [!DNL Transformation.cfg file] or a [!DNL transformation dataset include] file. For information about transformation configuration files, see the *Dataset Configuration Guide*. 

* **A lookup file** containing the data used to plot each data point. This file must contain at least three columns of data for each data point: the key, the longitude, and the latitude. For more information about the required format of the lookup file, see [Element Point Layer File Format](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2). 

* **A layer file** that specifies the location of the lookup file and identifies the related dimension and metric as well as the key, longitude, and latitude column names in the lookup file. For more information about the required format of the layer file, see [Element Point Layer File Format](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

  >[!NOTE]
  >
  >The [!DNL Zip Points.layer] file, provided with the [!DNL Geography] profile, is an element point layer that identifies the [!DNL Zipcode.dim] file, the [!DNL Sessions.metric] file, the [!DNL Zip Points.txt] lookup file, and the names of the key, longitude, latitude, and name columns in the lookup file.

## Element point lookup file format {#section-0bc8c652c1bd40eb84078f2af71a5c06}

The element point layer lookup file must contain at least the following three columns:

* **[!DNL Key] column:** This column should contain common key data, which enables the Data Workbench server to connect the data in the lookup file to that in the dataset. The [!DNL key] column must be the first column in the lookup file. Each row in this column identifies an element of the dimension. 

* **[!DNL Longitude] column:** This column should contain the longitude for each data point in the [!DNL Key] column. 

* **[!DNL Latitude] column:** This column should contain the latitude for each data point in the [!DNL Key] column. 

* **[!DNL Name] column (Optional):** If you want to specify a name to be displayed on the map for each data point, you can include a [!DNL Name] column in the lookup file.

Each row in the [!DNL Zip Points.txt] lookup file contains a ZIP Code in the first column followed by the longitude, latitude, and associated city name.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## Element point layer file format {#section-52d7e92be8354d979af9e7a2210b76f2}

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Data Paths </td> 
   <td colname="col2"> Path to the lookup file containing latitude and longitude data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude Column </td> 
   <td colname="col2"> The name of the column in the lookup file containing the longitude data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude Column </td> 
   <td colname="col2"> The name of the column in the lookup file containing the latitude data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name Column </td> 
   <td colname="col2"> Optional. The name of the column in the lookup file containing the names of the locations represented by the latitude and longitude data. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Key Column </td> 
   <td colname="col2"> <p>The name of the column in the lookup file containing the common key data, which enables the Data Workbench server to integrate the data in the lookup file into the dataset. This must be the first column in the lookup file. </p> <p>Each row in this column is an element of a dimension. This dimension must be defined in the <span class="filepath"> Transformation.cfg</span> file or a <span class="wintitle"> transformation dataset include</span> file and specified in the Dimension parameter of this file. For more information about transformation configuration files, see the <i>Dataset Configuration Guide</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimension </td> 
   <td colname="col2">The name of the dimension (defined in a transformation configuration file) containing elements that correspond to the data rows in the <span class="wintitle"> Key</span> column. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metric </td> 
   <td colname="col2"> The name of the metric that is evaluated over the dimension specified in the Dimension parameter. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scale </td> 
   <td colname="col2"> Optional. Value used to size the points in the layer. The default value is 100. Larger values make the points bigger, and smaller values make them smaller. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> Optional. The RGB color vector, which is expressed as (red,green,blue). For each color in the vector, you can enter a value from 0.0 to 1.0. For example, (1.0, 0.0, 0.0) is bright red, and (0.5, 0.5, 0.5) is gray. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rendering Mode </td> 
   <td colname="col2"> <p>Optional. Integer value representing the rendering mode to use for the layer. The three available modes are as follows: 
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">Rendering Mode 1. Points size is defined in screen space (points stay a constant size relative to the computer screen). Points are rendered using polygons, so there is no upper limit on point size. This is the default rendering mode. </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">Rendering Mode 2. Point size is defined in world space (points stay a constant size relative to the globe). Points are rendered using polygons, so there is no upper limit on point size. </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">Rendering Mode 3. Point size is defined in screen space. Points are rendered using OpenGL smooth points. </li> 
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
