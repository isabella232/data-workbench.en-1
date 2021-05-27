---
description: The dashboard requires certain read-only permissions to be able to access and display your data workbench data. Write privileges are not required.
title: Configuring Access Control
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
---
# Configuring Access Control{#configuring-access-control}

The dashboard requires certain read-only permissions to be able to access and display your data workbench data. Write privileges are not required.

Configuring access control involves editing your [!DNL Access Control.cfg] file on the FSU(s) and adding a new group to grant permission to the data workbench dashboard: 

1. Edit the [!DNL AccessControl.cfg] file (preferably using the data workbench workstation).
1. Create a new group named *Insight Dashboard Access*.
1. Under this group’s members, add the proper CN provided to you for this purpose (Example: CN:INSIGHT-USER01). Contact Adobe Customer Care for this CN.
1. Under this group’s read-only access, modify the list to reflect the following:

* /Profiles/$ 
* /Profiles/ 
* /Addresses 
* /Status/ 
* /Users/$

1. Remove any items from the read-write access section, as no write permissions are required for the dashboard.
1. Save the changes to the [!DNL AccessControl.cfg] file to the server for permissions to take effect.
