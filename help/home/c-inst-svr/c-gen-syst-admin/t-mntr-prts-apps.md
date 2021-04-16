---
description: To more thoroughly monitor your implementation, you can monitor all of the ports on your server machines as well as the software products running on each of those ports.
title: Monitoring Ports and Applications
uuid: 63d92718-81df-49eb-adda-8b49bde57a9d
exl-id: 418b2e5c-42ec-40f0-9cae-375194288143
---
# Monitoring Ports and Applications{#monitoring-ports-and-applications}

To more thoroughly monitor your implementation, you can monitor all of the ports on your server machines as well as the software products running on each of those ports.

 **Recommended Frequency:** Every 5-10 minutes

Using an application or script, you can monitor the TCP port on which each application is running (typically port 80 or 443) to make sure that the application is bound to that port. To do so, you request an application status page from the machine you want to monitor.

**To request the application status page** 

1. On the machine you want to monitor, modify the Access Controls to allow your monitoring application or script to access the machine. For instructions, see [Configuring Access Control](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).
1. Connect to [!DNL https://IP Address/Status/], where IP Address is the IP address of the machine for which you want to receive status.

   Example: [!DNL https://127.0.0.1/Status/]

   The machine should respond with a server status description. If it does not respond, check your event logs and contact Adobe Customer Care.

   For more information about this type of advanced monitoring, please contact Adobe Consulting Services.
