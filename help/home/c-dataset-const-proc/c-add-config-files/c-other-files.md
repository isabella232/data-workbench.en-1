---
description: The Dataset directory includes additional files that are either required for the operation of the software or provide additional functionality for your Adobe implementation.
title: Other Files
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
---
# Other Files{#other-files}

The Dataset directory includes additional files that are either required for the operation of the software or provide additional functionality for your Adobe implementation.

* **[!DNL Client.cfg:]** The [!DNL Client.cfg] file within the Dataset directory for the [!DNL Base] profile is required for operation of the software. Do not delete or modify any of the parameters in the [!DNL Client.cfg] file. 

* **[!DNL Cluster.cfg:]** The [!DNL Cluster.cfg] file within the Dataset directory for the [!DNL Base] profile is required for operation of the software. In the [!DNL Cluster.cfg] file, you should modify only the Normalize Server parameter if you are configuring a dataset to be processed on an data workbench server cluster. For instructions to modify the Normalize Server parameter, see [Creating a Centralized Normalization Server for a Cluster](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md). 

* **[!DNL Insight Transform.cfg] and [!DNL Insight Transform Mode.cfg]:** If you are using transformation functionality, you have two additional configuration files, data workbench [!DNL Transform.cfg] and data workbench [!DNL TransformMode.cfg], in the Dataset directory for the [!DNL Transform] profile. For information about these files and their parameters, see [Transform Functionality](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html). 

* The **PAServer.cfg** file. If you want to submit Predictive Analytics clustering jobs to Insight Servers, then you will need to configure the [!DNL PAServer.cfg] file for handling server-side clustering submissions. 
  The custom profile should inherit the [!DNL PAServer.cfg] from the Predictive Analytics profile ( [!DNL Server\Profiles\Predictive Analytics\Dataset]). 

  >[!IMPORTANT]
  >
  >Set a *Master Server* in this file and save the [!DNL PAServer.cfg] to the implementation site.
  >
  >```
  >PAServer = PAServerConfig: 
  >  Master Server = serverInfo: 
  >    Address = string: 
  >    Port = int: 80
  >    Use SSL = bool: false
  >```
  >
