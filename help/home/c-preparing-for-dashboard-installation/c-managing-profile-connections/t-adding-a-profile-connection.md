---
description: null
solution: Analytics
title: Adding a Profile Connection
topic: Data workbench
uuid: 0a168236-8c15-456b-9ac8-ca572baa916a
---

# Adding a Profile Connection{#adding-a-profile-connection}

1. Click **[!UICONTROL Add Profile Connection]** to bring up the **[!UICONTROL New Profile Connection]** window.
1. Using the form below, fill in the necessary fields:

   ![](assets/new_profile_connection.png)

   1. **[!UICONTROL Insight FSU Address]**: Enter the address to the FSU that hosts the profile(s) you would like to add to dashboard.

   1. **[!UICONTROL Use Certificate]**: Click if authentication is required, along with the CN of the certificate (this certificate needs to be added to the dashboard server in advance using the Windows Certificate Manager).
   1. **[!UICONTROL Insight DPU Address]**: Enter the address to the DPU that hosts the profile(s) you would like to add to dashboard.
   1. **[!UICONTROL Profiles]**: If multiple profiles exist on the given FSU/DPU entries above, multiple profiles may be added here by clicking the Add Profile button.

    * **[!UICONTROL Profile]**: Enter the name of the profile as it appears in Insight 
    * **[!UICONTROL Name]**: Enter the name of the profile as it should appear in dashboard.

1. Once the form has been configured appropriately, click **[!UICONTROL Create Connection]** to add the profile connection to the system.

   If the operation was successful, you will see a prompt indicating that the profile connection has been created. 