---
description: Before the dashboard can operate, you must allow it to access the SQL Server.
title: Configuring the SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
---
# Configuring the SQL Server{#configuring-the-sql-server}

Before the dashboard can operate, you must allow it to access the SQL Server.

1. Open the SQL Management Studio as an Administrator.
1. Add a new login by right-clicking **[!UICONTROL Logins]** and selecting **[!UICONTROL New Login]**.
1. Enter the full application pool identity name.

   By default, the application pool identity is named after the application pool. If you choose `dashboard`, then the identity will be named `IIS AppPool\dashboard`. 1. Select **[!UICONTROL Server Roles]** and check the **[!UICONTROL dbcreator]** role.
1. Click **[!UICONTROL OK]** to add the new user.
