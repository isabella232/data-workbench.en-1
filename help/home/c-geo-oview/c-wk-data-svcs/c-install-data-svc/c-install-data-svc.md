---
description: Information about installing a data service on a data workbench server.
title: Installing a Data Service on a Data Workbench Server
uuid: afe8e259-7fef-4327-9afc-18f36a1934db
exl-id: 414e93b7-4e9c-4c84-8fba-8052939240c5
---
# Installing a Data Service on a Data Workbench Server{#installing-a-data-service-on-a-data-workbench-server}

Information about installing a data service on a data workbench server.

 If you are using the IP Geo-intelligence data service or the IP Geo-location data service, you must install either the [!DNL IP Geo-intelligence] or [!DNL IP Geo-location] profile and the related lookup files on your data workbench server. You must complete the following procedures after you have installed the data workbench [!DNL Geography] profile. See [Installing Data Workbench Geography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md). If you have not installed data workbench, follow the instructions in the *Data Workbench User Guide* before proceeding.

>[!NOTE]
>
>To install the data service files, you must have access to the files on the data workbench server.

Adobe distributes the IP Geo-intelligence and IP Geo-location data services as [!DNL .zip] files. Each [!DNL .zip] file contains two folders: Lookups and Profiles. To install a data service on the data workbench server, you must perform the following steps:

* Install the data service profile. See [Installing the Data Service Profile](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/c-inst-data-svc-prof.md). 
* Install the data service lookups. See [Installing the Data Sevice Lookup Files](../../../../home/c-geo-oview/c-wk-data-svcs/c-install-data-svc/t-inst-data-svc-lkp-files.md).

You must install the data service profile and lookup files on the data workbench server machine on which you are processing and running your dataset profile. If you are running a data workbench server cluster, you must install the files on the master server. For information about dataset profiles, see the *Dataset Configuration Guide*.
