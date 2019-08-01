---
description: Conceptual Information about the Geography profile layers, types of imagery layers, and creating new layers.
seo-description: Conceptual Information about the Geography profile layers, types of imagery layers, and creating new layers.
seo-title: Understanding Imagery Layers
solution: Analytics
title: Understanding Imagery Layers
topic: Data workbench
uuid: 51af9314-559a-4e39-92f0-0abeda9fb50c
index: y
internal: n
snippet: y
---

# Understanding Imagery Layers{#understanding-imagery-layers}

Conceptual Information about the Geography profile layers, types of imagery layers, and creating new layers.

## Types of Imagery Layers {#section-ce25364651a04cd1b83f9ac7c231fa41}

Data workbench [!DNL Geography] enables you to view the following types of imagery layers in data workbench:

* **Terrain image layer:** This type of layer displays terrain imagery of the Earth, over which geographical data can be displayed. The globe visualization in data workbench is an example of a terrain image layer. See [Working with Terrain Image Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf). 

* **Element point layer:** This type of layer displays one point on the globe for each element of a dimension. See [Working with Element Point Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs.md#concept-52b3262ab4e042a18956be8809638af9). 

* **Vector layer:** This type of layer displays vector data (line art) on the globe. See [Working with Vector Layers](../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-wk-vctr-lyrs.md#concept-a2c9e8155f554cbe96ee3aaf44f2d620).

In data workbench, you can select which of the these layers you want to display for a particular analysis task.

## Geography Profile Layers {#section-4d9fb9b357764493a4d97d2b4068bb67}

The [!DNL Geography] profile provides you with a set of default imagery layers, which are stored in the Profiles\Geography\Maps folder within the data workbench server installation directory:

* **Blue Marble 2km:** This terrain image layer creates a 3-D map of the world, which is what displays when you add the globe visualization to a workspace. When this layer is not selected, the globe is not visible but the other layers still display. The [!DNL Blue Marble 2km.layer] file references the [!DNL Blue Marble 2km.tsi] file.

  For information about working with the globe visualization, see the *Data Workbench User Guide*. 

* **Zip Points:** This element point layer enables you to map locations in your dataset using a United States ZIP Code. The [!DNL Zip Points.txt] lookup file (provided by Adobe) contains a list of all United States ZIP Codes and each ZIP Code’s latitude and longitude. The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. Each element of the ZIP Code dimension ( [!DNL Zipcode.dim]) that you define within your dataset is mapped on the globe using the latitude and longitude listed for that ZIP Code in the [!DNL Zip Points.txt] lookup file.

  For information about defining dimensions, see the *Dataset Configuration Guide.* 

* **Boundaries:** This vector layer provides the major world political boundaries, such as countries, as well as the boundaries of natural physical features of the Earth, such as lakes and islands. The [!DNL Boundaries.layer] file references one or more of the [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec], and [!DNL world boundaries.vec] files. 

* **IP Coordinates:** This element point layer uses dynamic points to enable you to map locations in your dataset using IP addresses. The [!DNL IP Coordinates.layer] file references the Coordinates dimension ( [!DNL Coordinates.dim]) and specifies the Visitors metric as the metric to use to determine the size of the points on the globe for each coordinate.

Your [!DNL Geography] profile or other profiles in your installation may contain additional imagery layers that Adobe provided or your company created.

## Creating New Layers {#section-dc5a2f31d5fc46f58b865b9bb89fcfd4}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. All new layers must meet the following requirements:

* The [!DNL .layer] file must adhere to the format of one of the supported layer types. 
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary. 
* The referenced lookup file also must be stored within the data workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

For more information about the format and parameters for each type of layer file and its associated files, see the section in this chapter for the appropriate layer type. 
