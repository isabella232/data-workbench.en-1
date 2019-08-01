---
description: Create custom column export headers for your segment export files to add easily understood descriptions for exported segments. This export feature also lets you output as TSV and CSV files.
seo-description: Create custom column export headers for your segment export files to add easily understood descriptions for exported segments. This export feature also lets you output as TSV and CSV files.
seo-title: Segment Export with Custom Headers
title: Segment Export with Custom Headers
uuid: d79f8663-0290-49f6-a803-006d44037fcd
index: y
internal: n
snippet: y
---

# Segment Export with Custom Headers{#segment-export-with-custom-headers}

Create custom column export headers for your segment export files to add easily understood descriptions for exported segments. This export feature also lets you output as TSV and CSV files.

New functionality has been added to Segment Export, including the ability to export with a header, or in CSV and TSV formats.

You can create column headers for your export files.

## Creating a New Segment Export {#section-cffff55855f8467ea468b71393ab7676}

1. Open a workspace and right-click **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**. 

1. Right-click and select **[!UICONTROL Add Level > Extended]** > Choose an item. 
1. Right-click title and select **[!UICONTROL Add Attribute.]** Select a dimension from the menu. 

1. Right-click title and select **[!UICONTROL Add Metric.]** Select a metric from the menu. 

1. Right-click title and select **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** automatically populates the Column Name with the name of the metric. **[!UICONTROL New Segment Export]** requires you to set a custom name. ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >The Column Name field cannot be left empty or the header will not be present.

1. Right-click and name the segment and then click **[!UICONTROL Save Export File]**.

   An export window will open. 

1. Right-click the export name and click **[!UICONTROL Save as <export filename>]**.

   ![](assets/segment_export_headers_7.png)

1. Right-click [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. Find the export file you just created and save it to an existing profile.

   ![](assets/segment_export_headers_8.png)

