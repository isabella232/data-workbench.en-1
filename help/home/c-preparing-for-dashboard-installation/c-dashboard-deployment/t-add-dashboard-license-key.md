---
description: The dashboard product requires a license provided by Adobe ClientCare.
seo-description: The dashboard product requires a license provided by Adobe ClientCare.
seo-title: Add Dashboard License Key
solution: Analytics
title: Add Dashboard License Key
topic: Data workbench
uuid: e2d20199-c5fb-4376-869f-eff47cd728dc
index: y
internal: n
snippet: y
---

# Add Dashboard License Key{#add-dashboard-license-key}

The dashboard product requires a license provided by Adobe ClientCare.

1. Open **[!UICONTROL SQL Management Studio]** as an Administrator.
1. Open the database created by dashboard (for example, thinclientdb).
1. Right-click the **[!UICONTROL Configuration]** table and click **[!UICONTROL Edit Top 200 Rows]**.
1. Find the **[!UICONTROL licenseKey]** field and enter the key provided by Adobe ClientCare into the **[!UICONTROL Value]** column.
1. Restart the **[!UICONTROL Application Pool]** in the **[!UICONTROL IIS Manager Console]**.
