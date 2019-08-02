---
description: Information about installing a data service on a data workbench server.
seo-description: Information about installing a data service on a data workbench server.
seo-title: Installing a Data Service on a Data Workbench Server
solution: Analytics
title: Installing a Data Service on a Data Workbench Server
topic: Data workbench
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
index: y
internal: n
snippet: y
---

# Installing a Data Service on a Data Workbench Server{#installing-a-data-service-on-a-data-workbench-server}

Information about installing a data service on a data workbench server.

 If you are using the IP Geo-intelligence data service or the IP Geo-location data service, you must install either the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] profile and the related lookup files on your data workbench server. You must complete the following procedures after you have installed the data workbench [!DNL Geography] profile. See [Installing Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md#concept-0c093b4c2a6b469a831588cd4a272a91). If you have not installed data workbench, follow the instructions in the *Data Workbench User Guide* before proceeding.

>[!NOTE]
>
>To install the data service files, you must have access to the files on the data workbench server.

Adobe distributes the IP Geo-intelligence and IP Geo-location data services as [!DNL .zip] files. Each [!DNL .zip] file contains two folders: Lookups and Profiles. To install a data service on the data workbench server, you must perform the following steps:

* Install the data service profile. See [Installing the Data Service Profile](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md#concept-9ed269d23aa94757a6a71fcc3db9032a). 
* Install the data service lookups. See [Installing the Data Sevice Lookup Files](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md#task-3bcc2f5828c747e683a343381df793e7).

You must install the data service profile and lookup files on the data workbench server machine on which you are processing and running your dataset profile. If you are running a data workbench server cluster, you must install the files on the master server. For information about dataset profiles, see the *Dataset Configuration Guide*. 
