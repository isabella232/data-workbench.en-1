---
description: When creating an element point layer that references a lookup file to obtain latitude and longitude data, the location of the point is obtained by retrieving each element and its associated latitude and longitude from the lookup file.
seo-description: When creating an element point layer that references a lookup file to obtain latitude and longitude data, the location of the point is obtained by retrieving each element and its associated latitude and longitude from the lookup file.
seo-title: Defining Element Point Layers Referencing Lookup Files
solution: Analytics
title: Defining Element Point Layers Referencing Lookup Files
topic: Data workbench
uuid: 99d08d43-bdbb-42e1-927a-edf320686c79
index: y
internal: n
snippet: y
---

# Defining Element Point Layers Referencing Lookup Files{#defining-element-point-layers-referencing-lookup-files}

When creating an element point layer that references a lookup file to obtain latitude and longitude data, the location of the point is obtained by retrieving each element and its associated latitude and longitude from the lookup file.

Instead of using a lookup file, you can use the [!DNL Dynamic Points] functionality, which embeds the latitude and longitude of a location in the name of each element of a dimension. See [Defining Element Point Layers Using Dynamic Points](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3).

To define an element point layer that references a lookup file, you must create or already have available the following:

* **A dimension** defined in the [!DNL Transformation.cfg] file or a transformation dataset include file. For information about transformation configuration files, see the *Dataset Configuration Guide*. 

* **A lookup file** containing the data used to plot each data point. This file must contain at least three columns of data for each data point: the key, the longitude, and the latitude. For more information about the required format of the lookup file, see [Element Point Lookup File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lkp-file-frmt.md#concept-c059121019ea4dbcb1c17129567f4121). 

* **A layer file** that specifies the location of the lookup file and identifies the related dimension and metric as well as the key, longitude, and latitude column names in the lookup file. For more information about the required format of the layer file, see [Element Point Layer File Format](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>The [!DNL Zip Points.layer] file, provided with the [!DNL Geography] profile, is an element point layer that identifies the [!DNL Zipcode.dim] file, the [!DNL Sessions.metric] file, the [!DNL Zip Points.txt] lookup file, and the names of the key, longitude, latitude, and name columns in the lookup file.

