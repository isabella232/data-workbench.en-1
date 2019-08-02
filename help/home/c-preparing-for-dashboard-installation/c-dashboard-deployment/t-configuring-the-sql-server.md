---
description: Before the dashboard can operate, you must allow it to access the SQL Server.
seo-description: Before the dashboard can operate, you must allow it to access the SQL Server.
seo-title: Configuring the SQL Server
solution: Analytics
title: Configuring the SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
index: y
internal: n
snippet: y
---

# Configuring the SQL Server{#configuring-the-sql-server}

Before the dashboard can operate, you must allow it to access the SQL Server.

1. Open the SQL Management Studio as an Administrator.
1. Add a new login by right-clicking **[!UICONTROL Logins]** and selecting **[!UICONTROL New Login]**.
1. Enter the full application pool identity name.

   By default, the application pool identity is named after the application pool. If you choose `dashboard`, then the identity will be named `IIS AppPool\dashboard`. 1. Select **[!UICONTROL Server Roles]** and check the **[!UICONTROL dbcreator]** role.
1. Click **[!UICONTROL OK]** to add the new user.
