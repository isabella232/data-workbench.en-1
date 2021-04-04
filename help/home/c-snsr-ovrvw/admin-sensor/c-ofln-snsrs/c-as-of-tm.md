---
description: A data workbench server becomes aware of a source of data, such as a Sensor, when it receives data from that source.
solution: Analytics
title: Understanding "As Of" Time
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
---
# Understanding "As Of" Time{#understanding-as-of-time}

A data workbench server becomes aware of a source of data, such as a Sensor, when it receives data from that source.

 The As Of time is a guarantee that the [!DNL data workbench server] has data for all of the data sources of which it is aware.

Let’s say that we have a set of three [!DNL Sensors] that send data to a [!DNL data workbench server]: WEB1, WEB2, and WEB3. As the [!DNL data workbench server] receives and processes the data from these [!DNL Sensors], it automatically comes to expect data from each of these sources. The As Of time indicates the last time that the [!DNL data workbench server] received data from all three of these sources.

In practical terms, the [!DNL data workbench server] only cares about the As Of time and not what might be referred to as “wall time,” or the time from a clock on the wall. The [!DNL data workbench server] knows the time only as the As Of time. This is particularly important for reporting purposes as it guarantees that reports always run based on the As Of time, which ensures that reports with only partial data can never be sent to end users of the system.

The [!DNL data workbench server] uses data that is sent from the transmitter to provide the As Of time, whether it be actual data collected from the website or periodic heartbeats sent by your [!DNL Sensors]. These heartbeats serve two purposes:

1. To keep an HTTP/1.1 persistent connection open between the [!DNL Sensor] and the [!DNL data workbench server]. 

1. To keep the As Of time current in the event that website traffic is not being collected and sent to the [!DNL data workbench server].
