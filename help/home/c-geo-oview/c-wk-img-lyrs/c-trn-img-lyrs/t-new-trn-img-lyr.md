---
description: Steps to make a new terrain layer available to display on the globe visualization.
title: Making a New Terrain Image Layer Available
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
---
# Making a New Terrain Image Layer Available{#making-a-new-terrain-image-layer-available}

Steps to make a new terrain layer available to display on the globe visualization.

1. In the Profiles\*profile name*\Maps folder within the **[!UICONTROL Insight Server]** installation directory, place the layer file and the supporting image files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. By default, layers appear in lexicographic order by their names.

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see the Configuring Interface and Analysis Features chapter of the *Data Workbench User Guide*. 

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *< **[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. An X appears next to [!DNL Work Online].
1. Open a workspace and on a globe visualization, right-click and select the new layer. An X appears next to the layer name.
