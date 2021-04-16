---
description: Information about resolving web server problems, such as, if the web server is taken out of rotation, or if the web server fails.
title: Understanding the Causes
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
---
# Understanding the Causes{#understanding-the-causes}

Information about resolving web server problems, such as, if the web server is taken out of rotation, or if the web server fails.

## When a Web Server is Taken Out of Rotation {#section-b9f709099cb44b4f9d1acb38ca5330e3}

When a web server is taken out of rotation from a pool of servers, but is otherwise connected with the transmitter sending periodic heartbeats, the As Of time is kept current and no intervention on anyone’s part is required.

## When a Web Server Fails {#section-19280cf83ca44bd7b1ee11bfc74494d2}

When a web server is completely offline due to some catastrophic failure, or is not sending data or heartbeats, the As Of time on the [!DNL data workbench server] stops to guarantee that it represents the last time the [!DNL data workbench server] received data from ALL of the data sources of which it is aware. The system itself continues to process data, which is still available for analysis in Data Workbench, but anything in the [!DNL data workbench server] that is based on the As Of time does not function. For example, the As Of time triggers reporting and is used to create many derived dimensions in the system. When the As Of time has stopped, reporting is not triggered and these particular derived dimensions are not available.

For example, if WEB2 went offline on June 15 and did not send any data for five days, the As Of time would be sometime on June 15. The dimension of Yesterday, for example, would be June 14 even though today’s date is June 20.
