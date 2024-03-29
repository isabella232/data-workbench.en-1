---
description: You can customize the appearance of menus including the workspace window menu (accessed by right-clicking in any workspace) and menus listing metrics, dimensions, and map layers.
title: Customize a menu
uuid: 8c409c50-40b3-4de3-8048-a825ef4d75f5
exl-id: 7a377d9c-d339-43d8-a71a-a322416b2e60
---
# Customize a menu{#customize-a-menu}

You can customize the appearance of menus including the workspace window menu (accessed by right-clicking in any workspace) and menus listing metrics, dimensions, and map layers.

The hierarchy of any menu mirrors the structure of its directory in the [!DNL Profile Manager]. For example, the workspace window menu mirrors the structure of the Menu directory and the metrics menu mirrors the structure of the Metrics directory. For any menu, the corresponding directory may contain the following items:

* **Files:** These files represent the visualizations, legends, annotations, administrative interfaces, metrics, dimensions, or map layers that you can open by clicking the corresponding menu item. 
* **An [!DNL order.txt] file:** This file specifies in what order the menu displays its items. 
* **Subdirectories:** Each subdirectory represents a submenu. Each subdirectory may contain its own files, subdirectories, and [!DNL order.txt] file.

For example, the [!DNL Add Legend] menu contains the menu items Metric, Color, Value, and Confidence, in that order. In comparison, the Menu\Add Legend directory in the [!DNL Profile Manager] contains the files [!DNL Color.vw], [!DNL Confidence.vw], [!DNL Metric.vw], and [!DNL Value.vw] files in alphabetical order, as well as an [!DNL order.txt] file to control the order of the other files.
