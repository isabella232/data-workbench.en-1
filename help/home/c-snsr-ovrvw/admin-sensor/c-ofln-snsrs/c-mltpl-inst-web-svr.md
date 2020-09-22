---
description: Information about the general configuration of the Sensor with one web server instance running on a web server.
solution: Analytics
title: Working with Multiple Instances of a Web Server
uuid: 778ea95f-e0f2-4c2a-b7ed-7e323fea1e48
---

# Working with Multiple Instances of a Web Server{#working-with-multiple-instances-of-a-web-server}

Information about the general configuration of the Sensor with one web server instance running on a web server.

 ![](assets/web_inst.png)

In this scenario, a single web server instance is writing data to the memory mapped queue file, which is read by the transmitter and sent to the [!DNL data workbench server].

When [!DNL Sensor] is installed on a web server that is running multiple collector instances, you can configure it one of two ways:

* You can have all of the collector modules share one queue file.

  When using a single queue file, the management, configuration, and administration is somewhat simplified because the architecture itself is less complex. However, with a single queue file, the entire web server, regardless of the number of instances, is identified as WEB1. 

* You can replicate the above architecture multiple times and have each web server instance have a separate queue file.

  This enables you to identify each of the web server instances uniquely. In other words, the identification of the web server (and the corresponding SensorID in the [!DNL Sensor] configuration) is a function of this configuration.

In any case, the data still has all of the host name information so that you can distinguish between [!DNL www.client.com], [!DNL www2.client.com], and so forth. The correct configuration is determined by the analysis goals and whether the analysts need to segment the data based on a specific instance running on a web server.

>[!NOTE]
>
>This type of segmentation is typically used only in operational analysis and does not provide much practical use outside of that area.

