---
description: The Access Control.cfg file manages access to certain features in Insight Server.
seo-description: The Access Control.cfg file manages access to certain features in Insight Server.
seo-title: Updating the Access Control File
solution: Insight
title: Updating the Access Control File
uuid: 71035740-b47a-444c-b776-ef9986c86125
index: y
internal: n
snippet: y
---

# Updating the Access Control File{#updating-the-access-control-file}

The Access Control.cfg file manages access to certain features in Insight Server.

 It defines entities called AccessGroups. An AccessGroup identifies a group of users that have permission to use certain features of the server.

Before you can connect to [!DNL Insight Server] with [!DNL Insight], you must update the Administrators AccessGroup to include one of the [!DNL Insight] licenses that Adobe has issued to your organization. This AccessGroup identifies users that are permitted to perform administrative functions through [!DNL Insight].

The following procedure describes how to add a license to the Administrators AccessGroup. To complete this task, you must determine which [!DNL Insight] license has administrative privileges for your organization. (For initial set-up and configuration, granting administrative privileges to a single license is sufficient. You can grant administrative privileges to additional licenses later.) You also need to know the “common name” assigned to this license. To obtain this value, you can examine the license certificates for your account at [https://aap.adobe.com](https://aap.adobe.com ).

The purpose of this procedure is simply to identify a licensed copy of [!DNL Insight] that you can use to initially set up and configure [!DNL Insight Server]. Once you identify this license, you can perform all subsequent server configuration (including additional AccessGroup configuration) using the licensed copy of [!DNL Insight]. For additional information about controlling access to the server using AccessGroups, see [Configuring Access Control](../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d).

**To update the access control file**

1. Navigate to the [!DNL Access Control] folder in the directory where you installed [!DNL Insight Server].

   Example: [!DNL C:\Adobe\Server\Access Control] 

1. Open the [!DNL Access Control.cfg] file in a text editor such as Notepad. 
1. Locate the CN entry in the Administrators AccessGroup and replace the existing value of this entry with the common name that identifies the [!DNL Insight] that you will use to initially set up and administer [!DNL Insight Server]. The following file fragment illustrates where you insert the common name in the [!DNL Access Control.cfg] file. 

   ```
   Access Control Groups = vector: 5 items 
     0 = AccessGroup: 
       Members = vector: 2 items 
         0 = string: IP:127.0.0.1 
         1 = string: CN: CommonName 
       Name = string: Administrators 
       Read-Only Access = vector: 0 items 
       Read-Write Access = vector: 1 items 
         0 = string: / 
     1 = AccessGroup: 
     . . . 
   
   ```

   If you are using credentials-based authentication, a few extra entries will be available for configuration. These entries are:

    * O (Organization ID): This entry represents the ID of the organization. For example, `1 = string: O:46F582D4582596B40A45491@ExampleOrg`. This ID can be found in the Admin Console. 
    * PLC - This entry allows access to the users provisioned for a particular product configuration. It can be used in format `Organization_Id-PLC`. For example, `1 = string: PLC:46F582D4582596B40A45491@ExampleOrg-DataworkbenchAdminUsers`. The users provisioned for Data Workbench using the PLC `DataworkbenchAdminUsers` will get access on their servers. 
    * Email - This entry allows access to any individual user. Its value should be the email address of the provisioned user. For example, `1 = string: Email:kim@exampleorg.com`.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * The entries are case sensitive. You must ensure that the values specified for O, PLC, and Email are exactly the same as the ones shown in the Admin Console. 
   >    * Type the common name exactly as it appears on the certificate. 
   >    * Do not use the Tab key to generate whitespace in the [!DNL Access Control.cfg] file (or in any other configuration file for an Adobe component). Use only spaces to create whitespace. A tab character prevents the system from reading the file correctly. 
   >    
   >

1. Save and close the file.

