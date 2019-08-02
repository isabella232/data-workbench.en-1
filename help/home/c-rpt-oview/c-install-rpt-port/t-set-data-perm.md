---
description: To enable Report Portal to write to the database that contains information needed to authenticate users, you must set the proper permissions for the database.
seo-description: To enable Report Portal to write to the database that contains information needed to authenticate users, you must set the proper permissions for the database.
seo-title: Set Permissions for the Database
solution: Analytics
title: Set Permissions for the Database
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
index: y
internal: n
snippet: y
---

# Set Permissions for the Database{#set-permissions-for-the-database}

To enable Report Portal to write to the database that contains information needed to authenticate users, you must set the proper permissions for the database.

1. On the machine where IIS is running, navigate to \*PortalName*\data\users.mdb.
1. Right-click the **[!UICONTROL users.mdb]** file and select **[!UICONTROL Properties]**.
1. On the [!DNL Security] tab, in Groups or user names, click **[!UICONTROL Users]**.
1. In [!DNL Permission for User], in the Write row, select **[!UICONTROL Allow]**.
1. Click **[!UICONTROL OK]** and close the [!DNL Properties] dialog box.
