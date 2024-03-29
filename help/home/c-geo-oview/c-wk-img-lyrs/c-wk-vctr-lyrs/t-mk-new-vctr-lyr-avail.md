---
description: Steps to make a vector layer available to display on the globe visualization.
title: Making a New Vector Layer Available
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
---
# Making a New Vector Layer Available{#making-a-new-vector-layer-available}

Steps to make a vector layer available to display on the globe visualization.

1. In the Profiles\*profile name*\Maps folder within the data workbench server installation directory, place the layer file and the [!DNL .vec] or [!DNL .tsv] files.
1. Edit the [!DNL order.txt] file in the Profiles\*profile name*\Maps folder to reflect the order in which you want the layers to display. By default, layers appear in lexicographic order by their names.

   >[!NOTE]
   >
   >When editing the [!DNL order.txt] file, take care not to cover up map layers that you want to show.

   For more information about using [!DNL order.txt] files, see the Configuring Interface and Analysis Features chapter of the *Data Workbench User Guide*. 

1. In data workbench, select the desired profile by right-clicking the workspace title bar and clicking **[!UICONTROL Switch Profile]** > *< **[!UICONTROL profile name]**>*.
1. Right-click the workspace title bar and click **[!UICONTROL Work Online]**. An X appears next to [!DNL Work Online].
1. Open a workspace and on a globe visualization, right-click and select the new layer. An X appears next to the layer name.
