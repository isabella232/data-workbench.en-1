---
description: To connect to a data workbench server, Report Server must have permission to access that server.
seo-description: To connect to a data workbench server, Report Server must have permission to access that server.
seo-title: Enabling Access to the Data Workbench Server
solution: Analytics
title: Enabling Access to the Data Workbench Server
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
---

# Enabling Access to the Data Workbench Server{#enabling-access-to-the-data-workbench-server}

To connect to a data workbench server, Report Server must have permission to access that server.

You grant access to a data workbench server by adding Report Server’s common name (as assigned on Report Server’s digital certificate) to the server’s access control file.

>[!NOTE]
>
>When working in a clustered environment, Report Server should be configured to access the master data workbench server to avoid synchronization issues. In data workbench you can view information about processing servers in your cluster using the [!DNL Related Servers] menu item in the [!DNL Servers Manager]. For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

The following procedure describes how to manually add Report Server to the access control file on a data workbench server. To update the access control file in this way, you must have file-system access on the machine where the data workbench server is installed.

You also can update the server’s access control file using the [!DNL Server Files Manager] in data workbench. To do this, your data workbench client must have administrative privileges on the server.

For more information about the [!DNL Server Files Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**To configure access to a data workbench server** 

1. Navigate to the Access Control folder in the directory where you installed the data workbench server (InsightServer64.exe).

   Example: [!DNL C:\Adobe\Server\Access Control] 

1. Open [!DNL Access Control.cfg] in a text editor such as Notepad.
1. Locate the [!DNL Report Server AccessGroup] and add [!DNL Report Server’s] common name to this group as highlighted in the following file fragment. (Type the common name exactly as it appears on [!DNL Report Server’s] digital certificate.)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. Save the file.
