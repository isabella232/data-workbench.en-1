---
description: Insight Server is available under two license types.
solution: Insight
title: About Insight Server License Units
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
---

# About Insight Server License Units{#about-insight-server-license-units}

Insight Server is available under two license types.

The following are the two license types:

* [Data Processing Unit (DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65) 
* [File Server Unit (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## Data Processing Unit (DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

This type of [!DNL Insight Server] can process, store, and serve data from an Adobe dataset. It optionally can store the log files that contain the source data from which the dataset is constructed, or it can receive that data from an [!DNL Insight Server] File Server Unit (FSU). A DPU is the type of [!DNL Insight Server] with which [!DNL Insight] and [!DNL Report] clients interact directly.

If you are installing an [!DNL Insight Server] DPU, see [Installation Procedures for an Insight Server DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## File Server Unit (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

This type of server is configured to receive and store event data from one or more [!DNL Sensor] or event data replication instances ( [!DNL Repeater] functionality provided with a special use license) and stream the data to one or more [!DNL Insight Server] Data Processing Units (DPUs) for constructing Adobe datasets. DPUs communicate with an FSU using a protocol that optimizes the transfer of event data to the DPU and is significantly faster than maintaining log files on ordinary file servers. The use of an FSU also reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple [!DNL Sensors] to point to a single [!DNL Insight Server].

If you are installing an [!DNL Insight Server] FSU, see [Installation Procedures for an Insight Server FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016). 
