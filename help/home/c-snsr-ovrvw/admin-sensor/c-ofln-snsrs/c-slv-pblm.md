---
description: When a web server goes offline because of a failure, the solution is a simple one that requires a Data Workbench user with appropriate privileges to open the Log Processing Mode.cfg file and add the ID of the Sensor (in our example, WEB2) to the "Offline Sources" section.
seo-description: When a web server goes offline because of a failure, the solution is a simple one that requires a Data Workbench user with appropriate privileges to open the Log Processing Mode.cfg file and add the ID of the Sensor (in our example, WEB2) to the "Offline Sources" section.
seo-title: Solving the Problem
solution: Insight
title: Solving the Problem
uuid: 91b18456-7cfe-4ebc-9039-35a66daa847c
index: y
internal: n
snippet: y
---

# Solving the Problem{#solving-the-problem}

When a web server goes offline because of a failure, the solution is a simple one that requires a Data Workbench user with appropriate privileges to open the Log Processing Mode.cfg file and add the ID of the Sensor (in our example, WEB2) to the "Offline Sources" section.

This section of the file tells the [!DNL data workbench server] that it should no longer expect any data from this source because it is, in fact, offline.

>[!NOTE]
>
>This change does not need to be performed by an Adobe Consultant. Anyone who has appropriate privileges to open the [!DNL Log Processing Mode.cfg] file can make this change.

If WEB2 begins to send data again, the [!DNL data workbench server] brings the source back online and adjusts the As Of time to reflect the last time it received data from all of the sources of which it is aware. In other words, new data coming into the system takes precedence over what is written in the [!DNL Log Processing Mode.cfg file].

If WEB2 goes offline again, the As Of time will again stop, and you will need to edit the [!DNL Log Processing Mode.cfg] file again even though it might already have WEB2 listed as an offline source. This is an artifact of the design of the product in keeping with the definition of the As Of time: the last time the system has data for all known sources.

When you add more web servers (WEB4, WEB5, WEB6), and they begin sending data to the [!DNL data workbench server], you do not need to do anything to have the [!DNL data workbench server] recognize the new sources. The system simply becomes aware that it should be expecting data from these new sources, as described above. 
