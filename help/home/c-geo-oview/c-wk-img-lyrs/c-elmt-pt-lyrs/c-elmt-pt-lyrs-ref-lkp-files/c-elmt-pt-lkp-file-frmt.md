---
description: Information about the element point layer columns.
seo-description: Information about the element point layer columns.
seo-title: Element Point Lookup File Format
solution: Analytics
title: Element Point Lookup File Format
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
index: y
internal: n
snippet: y
---

# Element Point Lookup File Format{#element-point-lookup-file-format}

Information about the element point layer columns.

The element point layer lookup file must contain at least the following three columns:

* **[!DNL Key] column:** This column should contain common key data, which enables the data workbench server to connect the data in the lookup file to that in the dataset. The [!DNL Key] column must be the first column in the lookup file. Each row in this column identifies an element of the dimension. 

* **[!DNL Longitude] column:** This column should contain the longitude for each data point in the [!DNL Key] column. 

* **[!DNL Latitude] column:** This column should contain the latitude for each data point in the [!DNL Key] column. 

* **[!DNL Name] column:** (Optional). If you want to specify a name to be displayed on the map for each data point, you can include a [!DNL Name] column in the lookup file.

Each row in the [!DNL Zip Points.txt] lookup file contains a ZIP Code in the first column followed by the longitude, latitude, and associated city name.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

