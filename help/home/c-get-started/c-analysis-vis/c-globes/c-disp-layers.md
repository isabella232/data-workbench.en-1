---
description: The Geography profile stores a collection of imagery layers and files.
title: Display layers
uuid: ebc7025d-e619-43dd-88da-7452ada3226b
exl-id: 12ec913f-c7e5-49b5-8792-db0881cb5cfe
---
# Display layers{#display-layers}

The Geography profile stores a collection of imagery layers and files.

 When you display a globe, you can select which of the available layers to display for a particular analysis task:

* **Blue Marble 2km:** This layer displays the globe. When this layer is not selected, the globe is not visible. 
* **IP Coordinates:** This element point layer displays the latitude and longitude of locations in your dataset based on visitor IP addresses. 
* **Zip Points:** This layer displays the latitude and longitude of locations in your dataset based on a list of United States ZIP Codes provided by Adobe. The [!DNL Zip Points.txt] lookup file contains the ZIP Code, latitude, and longitude data to be displayed, while the [!DNL Zip Points.layer] file contains the configuration parameters needed to display this data on the globe. Both of these files are stored in the Profiles\Geography\Maps folder within the Data Workbench server installation directory. 

* ***Other available layer names:*** Each layer name represents a [!DNL .layer] file stored in the Profiles\Geography\Maps folder, Profiles\IP Geo-location\Maps folder, or Profiles\IP Geo-intelligence\Maps folder within the Insight Server installation directory.

>[!NOTE]
>
>To have the IP Geo-location or IP Geo-intelligence profile, you must subscribe to either the IP Geo-location or IP Geo-intelligence data service, respectively.

To control the order in which your layers display, you can use an [!DNL order.txt] file. See [Customizing Menus Using Order.txt Files](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

**To toggle layers in a globe**

* Right-click within the visualization and click the desired layer name. An X to the left of the layer indicates that the layer is visible.
