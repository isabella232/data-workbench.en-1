---
description: The data workbench client application now supports Simplified Chinese.
seo-description: The data workbench client application now supports Simplified Chinese.
seo-title: Simplified Chinese localization
solution: Analytics
title: Simplified Chinese localization
topic: Data workbench
uuid: 761a5e4f-4c84-4900-bfed-63e07a073612
index: y
internal: n
snippet: y
---

# Simplified Chinese localization{#simplified-chinese-localization}

The data workbench client application now supports Simplified Chinese.

 **To install Simplified Chinese**:

Before configuring [!DNL Insight.exe] and supporting files, you must exit the client application.

1. Create a shortcut that passes in the command-line setting to the [!DNL insight.exe] file. 

   ```
   Insight.exe -zh-cn
   ```

1. Configure [!DNL Insight.cfg] to support single and double-byte font characters.

   Data workbench currently supports both English and Simplified Chinese. You can select fonts to support both of these languages:

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial 
   ```

1. Restart [!DNL Insight.exe].

