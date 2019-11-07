---
description: To change the data workbench server with which a Sensor communicates (the target server), you must edit the txlogd.conf file on each of the web servers on which Sensor is installed.
solution: Insight
title: Changing the Target Data Workbench Server
uuid: 931d376d-8622-4858-8290-19ce91538570
---

# Changing the Target Data Workbench Server{#changing-the-target-data-workbench-server}

To change the data workbench server with which a Sensor communicates (the target server), you must edit the txlogd.conf file on each of the web servers on which Sensor is installed.

 **To change to target [!DNL data workbench server]** 

1. Stop both the original target server and the new target server.
1. Copy the most current [!DNL .vsl] file from the original target server to the new target server. When you restart the new target server in a later step, this causes all new [!DNL Sensor] data to be appended to the current, existing [!DNL .vsl] file instead of creating a new [!DNL .vsl] file. To do so, complete the following steps:

    1. On the original target server, browse to the [!DNL \Logs] folder in the [!DNL data workbench server] installation directory. 
    
    1. Copy the most current [!DNL .vsl] file in the folder. 
    1. On the new target server, browse to the [!DNL \Logs] folder in the [!DNL data workbench server] installation directory and paste the [!DNL .vsl] file to this folder.

1. On one of the web servers on which [!DNL Sensor] is installed, open and edit the [!DNL txlogd.conf] file. To do so, complete the following steps:

    1. Browse to the [!DNL Sensor] installation directory and open the [!DNL txlogd.conf] file in a text editor. 
    
    1. Locate the ServerAddress parameter and change it to reflect the address of the new target server. 
    1. Save and close the file.

1. Repeat steps 2-3 on all the remaining web servers on which [!DNL Sensor] is installed.
1. Restart the original target server (if it is still to be used) and the new target server.
1. Data will begin transmitting to the new target server that you have specified.
