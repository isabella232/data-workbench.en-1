---
description: Sensor enables you to acquire web request data (event or log data) as well as extended measurement data.
seo-description: Sensor enables you to acquire web request data (event or log data) as well as extended measurement data.
seo-title: What Kind of Data Can I Acquire?
solution: Analytics
title: What Kind of Data Can I Acquire?
topic: Data workbench
uuid: 5ac864b8-4017-4d80-b491-7a5976225eb2
---

# What Kind of Data Can I Acquire?{#what-kind-of-data-can-i-acquire}

Sensor enables you to acquire web request data (event or log data) as well as extended measurement data.

Extended measurement data is not available to your web servers as a part of their normal operation.

The following topics are described:

## Web Request Data {#section-a28217e8a8c047eb9b1c0ca1f67c832f}

[!DNL Sensor] enables web request data (event or log data) to be acquired and transported automatically to a central location for storage and processing for analysis. Unless you specifically choose to filter out certain types of requests and not collect data about those request types, [!DNL Sensor] captures data about all GET requests made of the web servers on which it is installed.

[!DNL Sensor] automates this data acquisition process for all GET requests that are made on your servers and has significant business and technical benefits over alternative methods of acquiring website request data. These benefits include the following:

* Requests that are unnecessary for analysis and reporting can be filtered out before you incur costs for their acquisition, transportation, storage, and processing. 
* Site administrators do not have to rotate log files in batch, either manually or via script. 
* [!DNL Sensor] aggregates log files at a central location to allow easy access for processing. 
* [!DNL Sensor] organizes and stores log files in a common data-preserving format, removing the need to preprocess them before they can be used for analysis and reporting purposes. 
* Instances of certain content types can be included in the log files even though most requests for a certain content type are automatically filtered out. 
* [!DNL Sensor] compresses log file entries, which requires significantly less storage space, reducing costs and allowing the data to be kept available for analysis for longer periods of time. 
* [!DNL Sensor’s] fault tolerant features allow system and network faults while still ensuring the delivery of the log data to a central repository. 
* [!DNL Sensor] allows the implementation of controlled experiments with web content, processes, and marketing campaigns. 
* [!DNL Sensor] time stamps log entries in 100ns units, allowing new types of analytic functionality. 
* [!DNL Sensor] allows site owners to add data (measurements) to the log entries after initial implementation for consideration in analysis and reporting.

For more information about acquiring extended measurement data, see [Acquiring Baseline Measurements](../../home/c-undst-pg-tag/c-acq-bsln-msmts/c-acq-bsln-msmts.md#concept-ed9b4b21693a4bafac75d60708b9b6fe).

## Extended Measurement Data {#section-b7f0285de49e432b9db8fda85fa735ba}

[!DNL Sensor] also supports the use of page tags (or embedded object requests) to acquire measurement data that is not available to your web servers as a part of their normal operation. Page tags are commonly used to measure:

* The viewing of a logical page in a dynamic website. 
* The viewing of content or ads on a third-party controlled website. 
* The viewing of content that is served from a browser cache or CDN. 
* Detailed information about a visitor's browser, including measurements such as page load time, screen resolution, what form fields the visitor has filled in, and so on. 
* Other data that is not otherwise sent by browsers to your web servers.

[!DNL Sensor] collects any information placed in any GET request made to a web server that is running [!DNL Sensor]. Such requests may come from embedded object requests of any sort, either to simply measure that the request was made at a certain time by a certain browser or to pass other measurement data into the data collection stream so that it may be processed for analysis and reporting purposes.

[!DNL Sensor] provides the best of both client-side and server-side data acquisition worlds—it acquires your server-side web log data and collects client-side, third-party site, or cache-busting measurements taken by embedded object requests. In other words, [!DNL Sensor] acquires both the request data normally known to your web servers (server-side measurements) and any additional measurement data that you collect through the use of page tags (client-side measurements) that send their data to any web servers running [!DNL Sensor]. Such web servers can be dedicated to collecting client-side measurements but are not required to be.

For more information about acquiring extended measurement data, see [Acquiring Extended Measurements](../../home/c-undst-pg-tag/c-acq-ext-msmt/c-acq-ext-msmt.md#concept-d171a6d2bde843cdb65bcfe69c6a4944). 
