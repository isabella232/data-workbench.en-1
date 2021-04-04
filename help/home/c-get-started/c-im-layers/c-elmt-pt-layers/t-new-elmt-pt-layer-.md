---
description: Steps to make any element point layer available to display on the globe visualization.
solution: Analytics
title: Make a new element point layer available
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
---
# Make a new element point layer available{#make-a-new-element-point-layer-available}

Steps to make any element point layer available to display on the globe visualization.

1. In the Profiles\*profile name*\Maps folder within the Data Workbench server installation directory, place the layer file and its related lookup file.
1. If you defined a new dimension for your element point layer and have not yet retransformed your dataset, retransform your dataset now.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. By default, layers appear in lexicographic order by their names.

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see the Configuring Interface and Analysis Features chapter of the *Data Workbench User Guide*. 

1. In Data Workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *< **[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. An X appears next to Work Online.
1. Open a workspace and on a globe visualization, right-click and select the new layer. An X appears next to the layer name.
