---
description: Target Insight Server machines running the Insight Server Replication Service must be able to read the log files on this repeater server.
title: Configuring Access Control for Target Machines
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
exl-id: 2d0b554a-30e9-4344-9aec-a68fd5f57304
---
# Configuring Access Control for Target Machines{#configuring-access-control-for-target-machines}

Target Insight Server machines running the Insight Server Replication Service must be able to read the log files on this repeater server.

Access to the target machines is granted using the [!DNL Access Control.cfg] file.

**To configure Access Control for access by target [!DNL Insight Server] machines** 

1. Navigate to the [!DNL Access Control] folder in the directory where you installed repeater functionality.

   Example: [!DNL D:\Adobe\Repeater\Access Control]

1. Open [!DNL Access Control.cfg] in a text editor such as Notepad.
1. Create an access group for the [!DNL Insight Server] machines that must access the log files on this repeater server. Give this access group a name something like “Replication Targets.”

   The following file fragment shows how the access group should look.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

    1. In the Members section, specify the IP address for each machine. 
    1. Update the items count for the Members vector to reflect the number of machine IP addresses you inserted. 
    1. In the Read-Only Access section, specify the location of the event data that the replication targets access. Use forward slashes in the path specification (/). The default location is the [!DNL Logs] folder on the Repeater machine (/Logs/). 
    1. Update the items count for the Read-Only Access vector to reflect the number of locations you inserted.

1. Update the number of access groups in the Access Control Groups vector at the top of the file to reflect the addition of the new access group.

   ```
   Access Control Groups = vector: n items
   ```

1. Save the file.
