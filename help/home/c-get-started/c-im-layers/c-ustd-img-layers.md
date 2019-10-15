---
description: Conceptual information about imagery layers.
seo-description: Conceptual information about imagery layers.
seo-title: About imagery layers
solution: Analytics
title: About imagery layers
topic: Data workbench
uuid: a8b00bda-c5b2-4f27-8c15-2d319b3bfa70
---

# About imagery layers{#about-imagery-layers}

Conceptual information about imagery layers.

## Types of imagery layers {#section-891cbf61e8334690bd203a2bb9761b25}

You can view the following types of imagery layers in Data Workbench:

* **[!UICONTROL Terrain image layer]:** This type of layer displays terrain imagery of the Earth, over which geographical data can be displayed. The globe visualization in is an example of a terrain image layer. See [Working with Terrain Image Layers](../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f). 

* **[!CONTROLNL Element point layer]:** This type of layer displays one point on the globe for each element of a dimension. See [Working with Element Point Layers](../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-layers.md#concept-7c93c54552844a20bd6014ae8446b3fd). 

* **[!UICONTROL Vector layer]:** This type of layer displays vector data (line art) on the globe. See [Working with Vector Layers](../../../home/c-get-started/c-im-layers/c-vctr-layers/c-vctr-layers.md#concept-a9b9cb7fc33b4aa5ae1646fab202dcc9).

* **[!UICONTROL Presentation layer]** Annotate and clarify visualizations using a presentation overlay. Add text call-outs, arrows, images, and color coding to highlight and clarify your data, and then share with others.

In Data Workbench, you can select which of the these layers you want to display for a particular analysis task.

## Geography profile layers {#section-d04ab9f1a8cd4c6580e48ce44ac51898}

The [!DNL Geography] profile provides you with a set of default imagery layers, which are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory:

* **[!UICONTROL Blue Marble 2km]:** This terrain image layer creates a 3-D map of the world, which is what displays when you add the globe visualization to a workspace. When this layer is not selected, the globe is not visible but the other layers still display. The [!DNL Blue Marble 2km.layer] file references the [!DNL Blue Marble 2km.tsi] file. 

* **[!UICONTROL Zip Points]:** This element point layer enables you to map locations in your dataset using a United States ZIP Code. The [!DNL Zip Points.txt] lookup file (provided by Adobe) contains a list of all United States ZIP Codes and each ZIP Code’s latitude and longitude. The [!DNL Zip Points.layer] file references the [!DNL Zip Points.txt] file and the [!DNL Zipcode.dim] file and contains the configuration parameters needed to display the locations on the globe. Each element of the ZIP Code dimension ( [!DNL Zipcode.dim]) that you define within your dataset is mapped on the globe using the latitude and longitude listed for that ZIP Code in the [!DNL Zip Points.txt] lookup file.

  For information about defining dimensions, see the *Dataset Configuration Guide*. 

* **[!UICONTROL Boundaries]:** This vector layer provides the major world political boundaries, such as countries, as well as the boundaries of natural physical features of the Earth, such as lakes and islands. The [!DNL Boundaries.layer] file references one or more of the [!DNL mwcoast.vec], [!DNL mwisland.vec], [!DNL mwlake.vec], [!DNL mwnation.vec], [!DNL mwriver.vec], [!DNL mwstate.vec], [!DNL US states.vec], and [!DNL world boundaries.vec] files. 

* **[!UICONTROL IP Coordinates]:** This element point layer uses dynamic points to enable you to map locations in your dataset using IP addresses. The [!DNL IP Coordinates.layer] file references the Coordinates dimension ( [!DNL Coordinates.dim]) and specifies the Visitors metric as the metric to use to determine the size of the points on the globe for each coordinate.

Your [!UICONTROLNL Geography] profile or other profiles in your installation may contain additional imagery layers that Adobe provided or your company created.

## Create a new layer {#section-b5313773316c4e0fa748f7376a8e7f0b}

You can create new imagery layers by copying the appropriate type of layer file included in the [!DNL Geography] profile into any Profiles\*profile name*\Maps folder, then renaming and editing the file as appropriate. All new layers must meet the following requirements:

* The [!DNL .layer] file must adhere to the format of one of the supported layer types. 
* The [!DNL .layer] file must reference the appropriate lookup and dimension files, if necessary. 
* The referenced lookup file also must be stored within the Data Workbench server installation directory, and its path must be specified accurately in the [!DNL .layer] file.

For more information about the format and parameters for each type of layer file and its associated files, see the section in this chapter for the appropriate layer type. 
