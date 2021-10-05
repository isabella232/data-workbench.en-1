---
description: The final step is to run the dashboard for the first time to allow it to initialize.
title: Initializing the Dashboard
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
---
# Initializing the Dashboard{#initializing-the-dashboard}

The final step is to run the dashboard for the first time to allow it to initialize.

1. Open a web browser and enter the URL to the newly deployed site (for example, https://localhost/dashboard).
1. Connecting for the first time will setup the database tables, so you may experience a slight delay.
1. The initial logon credentials are:

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. On your first login, go to **[!UICONTROL User]** > **[!UICONTROL Account Settings]** and select **[!UICONTROL Change Password]** to change your administrator password.

The dashboard installation is now complete. If you haven’t already, use the instructions detailed in the Preparing Data Workbench section of this guide to configure your communication with data workbench servers and to manage users and groups.

>[!NOTE]
>
>Dashboard error and audit logs can be found in the [!DNL logs] directory within the installation path.

>[!NOTE]
>
>If you need to change the application pool identity to a different account, make sure to grant access to the database and give the identity read/write access to the [!DNL logs] folder in the installation path.

>[!NOTE]
>
>If you ever need to change the connection string for the database, simply edit the value using the **[!UICONTROL IIS Management Console]**.
