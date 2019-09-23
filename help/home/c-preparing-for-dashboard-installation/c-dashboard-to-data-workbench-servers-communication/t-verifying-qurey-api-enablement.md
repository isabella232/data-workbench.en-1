---
description: Each DPU from which the dashboard is to visualize data must have a Query API license.
seo-description: Each DPU from which the dashboard is to visualize data must have a Query API license.
seo-title: Verifying Query API Enablement
solution: Analytics
title: Verifying Query API Enablement
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
---

# Verifying Query API Enablement{#verifying-query-api-enablement}

Each DPU from which the dashboard is to visualize data must have a Query API license.

Below are some instructions on how to validate that Query API is installed and enabled. 

1. Find your data workbench server’s certificate.
1. Open this certificate in a text editor.
1. Ensure that the line `Product = Query API` exists in the certificate.
1. In the **[!UICONTROL Trace]** folder, open the [!DNL InsightServer64.log] in a text editor.
1. In the latest startup log entries, ensure that the line `Enabling Query API (licensed)` appears.

* If the Query API is not enabled, you will see the entry `Not enabling Query API (not licensed)`. 
* If you do not see any log entries, or suspect that the data workbench server has been restarted since the Query API was added, please restart the data workbench server again and check the log.

   If you are unable to validate that Query API is enabled, please contact Adobe ClientCare for assistance. 
