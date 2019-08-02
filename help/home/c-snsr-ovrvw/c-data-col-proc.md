---
description: Sensor automates the acquisition of data from your Internet channel by doing away with the bulk of human labor traditionally involved in data collection.
seo-description: Sensor automates the acquisition of data from your Internet channel by doing away with the bulk of human labor traditionally involved in data collection.
seo-title: How Does the Data Collection Process Work?
solution: Insight
title: How Does the Data Collection Process Work?
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
index: y
internal: n
snippet: y
---

# How Does the Data Collection Process Work?{#how-does-the-data-collection-process-work}

Sensor automates the acquisition of data from your Internet channel by doing away with the bulk of human labor traditionally involved in data collection.

 In many cases, using [!DNL Sensor] can vastly simplify your data management process.

Today’s large Internet, extranet, and intranet sites often run on an array of web servers. The logs and data produced can be very large and cumbersome to manage. For example, if your site is running 30 web servers, typically one of your employees (or outsourced service provider’s employees) would pull and consolidate each log file on each of the 30 servers, then run reports on them. Installing [!DNL Sensor] on each of your web servers automates this entire process, reducing your expenses and making data available in real time.

To automate this process, [!DNL Sensor] collects raw information about the traffic on a website directly from each web server. The raw data that [!DNL Sensor] captures is called event data and is similar to the type of data that your web server records in its log files.

To capture this data, instrumentation within [!DNL Sensor] records information about each HTTP request that your web server processes. [!DNL Sensor] then buffers the information to protect against network failure and securely transmits the information via HTTP/S to the [!DNL data workbench server] that you specify.

After the [!DNL data workbench server] receives the data, it processes and stores your log files in highly-compressed [!DNL .vsl] format files, allowing you to easily maintain very large amounts of data on inexpensive hardware.

For information about the event data fields collected by [!DNL Sensor] in [!DNL .vsl] files, see [Event Data Record Fields](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44). 
