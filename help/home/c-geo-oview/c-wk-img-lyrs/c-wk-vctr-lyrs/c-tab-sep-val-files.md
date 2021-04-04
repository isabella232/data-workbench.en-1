---
description: When creating a vector layer that references a tab separated values (.tsv) file, the vector data is obtained by retrieving drawing instructions as well as longitude and latitude data from the .tsv file.
solution: Analytics
title: Vector layers referencing tab separated values files
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763,7b0b0286-072b-4b31-b6ec-ced322da5236
---
# Vector layers referencing tab separated values files{#vector-layers-referencing-tab-separated-values-files}

When creating a vector layer that references a tab separated values (.tsv) file, the vector data is obtained by retrieving drawing instructions as well as longitude and latitude data from the .tsv file.

To define a vector layer that references a [!DNL .tsv] files, you must have the following:

* **A [!DNL .tsv] file** that contains the data used to draw the vectors on the globe, including longitude and latitude data. For more information about the required format of the [!DNL .tsv] file, see [Vector TSV File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e). 

* **A layer file** that specifies the location of the [!DNL .tsv] file. For more information about the required format of the layer file, see [Vector Layer File Format](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Vector TSV file format {#section-a29012c9ff4444ac8a6d41c68482828e}

The [!DNL .tsv] file must contain the following three tab separated columns:

* **[!DNL Begin]:** This column should indicate whether to begin a new line. Values in this column can be either 0 (do not begin a new line) or 1 (begin a new line). 
* **[!DNL Longitude]:** This column should contain longitude values. 
* **[!DNL Latitude]:** This column should contain latitude values.

>[!NOTE]
>
>Any additional columns are ignored.

Following is a sample [!DNL .tsv] file that contains data for a vector layer:

![](assets/tsv_vectorlayer.png)

## Vector layer file format {#section-c430923f341f4c93852e9f24b61e82bf}

Each vector layer file referencing [!DNL .tsv] files must be formatted using the following template:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV Files </td> 
   <td colname="col2"> <p>Path(s) to the <span class="filepath"> .tsv</span> file(s) containing the vector data. </p> <p>Example: <span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Color </td> 
   <td colname="col2"> The RGB color vector, which is expressed as (red,green,blue). For each color in the vector, you can enter a value from 0.0 to 1.0. For example, (1.0, 0.0, 0.0) is bright red, and (0.5, 0.5, 0.5) is gray. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> Controls the transparency of the vectors shown on the globe. The range is 0 to 1, with 0 being the most transparent. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Width </td> 
   <td colname="col2"> Optional. Sets the width of the data in pixels. The recommended range is 1 to 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Error Factor </td> 
   <td colname="col2"> Controls how accurately the vectors are drawn. For larger values, the vectors are drawn less accurately but faster. The default value is 5. </td> 
  </tr> 
 </tbody> 
</table>
