---
description: By default, Insight Server listens on ports 80 (for HTTP) and 443 (for HTTPS).
seo-description: By default, Insight Server listens on ports 80 (for HTTP) and 443 (for HTTPS).
seo-title: Checking the Port Settings
solution: Insight
title: Checking the Port Settings
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
index: y
internal: n
snippet: y
---

# Checking the Port Settings{#checking-the-port-settings}

By default, Insight Server listens on ports 80 (for HTTP) and 443 (for HTTPS).

 If these ports are already allocated by another process on the machine where you have installed [!DNL Insight Server], use the following procedure to change [!DNL Insight Server’s] port assignments.

**To change the port assignments** 

1. Navigate to the [!DNL Components] folder in the directory where you installed [!DNL Insight Server].

   Example: [!DNL C:\Adobe\Server\Components]

1. Open the [!DNL Communications.cfg] file in a text editor such as Notepad.
1. Locate the Port and the SSL Port entries, as shown below:

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. If these are not the ports that you want [!DNL Insight Server] to use, change the port assignments, then save and close the file.
