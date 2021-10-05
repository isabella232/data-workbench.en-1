---
description: The purpose of Sensor’s content-type filtering capability is to eliminate the need to store and process information that is not useful for analysis purposes.
title: Filtering By Content Type
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
---
# Filtering By Content Type{#filtering-by-content-type}

The purpose of Sensor’s content-type filtering capability is to eliminate the need to store and process information that is not useful for analysis purposes.

Much of the request data that is available through a web server’s API is not useful in business analysis. Storage and processing are expensive and [!DNL Sensor’s] content-type filtering allows you to avoid unnecessary storage and processing.

To maximize the web log data processing performance and reduce the amount of measurement data that must be stored, [!DNL Site] acquires measurement data (request data, log entries, log data, and so on) for all web content-type requests, except for specifically listed content types (such as cascading style sheets, image requests, and so forth), which are filtered out before they are transmitted to the data workbench server by [!DNL Sensor]. This filtering can be disabled for an entire web server, and it also can be overridden for a particular content object by adding the name-value pair “Log=1” to the query string of a particular embedded object (for example, [!DNL https://www.mysite.com/advertisement.gif?Log=1]).
