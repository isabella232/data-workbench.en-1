---
description: Check whether the collector is running using different methods.
solution: Analytics
title: Confirming that the Data Collector is Running
uuid: e5b9b12a-b8a5-4c00-abe5-e824516d46b7
---

# Confirming that the Data Collector is Running{#confirming-that-the-data-collector-is-running}

Check whether the collector is running using different methods.

 **Recommended Frequency:** Every 5-10 minutes

* [Use the Site Test Functionality in the transmitter.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-a5a697c3252e40f184c0b662926170f2) 
* [Check whether [!DNL Sensor] is setting a cookie.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-cltr-rng.md#section-365a0182474c4dc9a5372d3e984f53de)

## Using Site Test {#section-a5a697c3252e40f184c0b662926170f2}

One way to verify that the collector is running is to enable the Site Test function in the transmitter. When you enable Site Test, the transmitter periodically (every 60 seconds) sends a GET request to the web server on which the collector is running. If Site Test does not get a response from the web server, it writes an error message to syslog and sends an error message to the [!DNL data workbench server] (which is written to the sensor-log file).

If Site Test receives a response from the web server, it looks in the queue file for a packet from the web server. If the packet does not appear (indicating that the collector was not running to capture the event), Site Test writes an error message to syslog and sends an error message to Adobe (which also is written to the sensor-log file).

In the requests that Site Test sends to the web server, Site Test sets the User-Agent value to “ [!DNL Sensor] Test.” If you do not want these requests to appear in your dataset, add the “ [!DNL Sensor] Test” User-Agent to the [!DNL Baseline Robots List.txt] file or the [!DNL Extended Robots List.txt] file in the [!DNL Lookups] folder on the [!DNL data workbench server].

**To enable Site Test in the transmitter**

1. Locate the [!DNL txlogd.conf] file on the machine where [!DNL Sensor] is running and open it in a text editor. 

1. In the [!DNL txlogd.conf] file, locate the “SiteTest” line and configure it as shown below. If your [!DNL txlogd.conf] file does not include the “SiteTest” line, simply add the line to the end of the configuration file.

   SiteTest http, *serverAddress*, *port*, *resource*

   where *serverAddress* is the web server’s name or IP address, *port* is the server’s HTTP listening port, and *resource* is the specific resource that you want Site Test to request when testing the server. Note that *resource* can include a query string.

   Example: SiteTest http,localhost,80,/index.jsp

   To test multiple web servers, you simply specify multiple SiteTest lines.

## Checking for a Cookie {#section-365a0182474c4dc9a5372d3e984f53de}

Another way to verify that the collector is running on a web server is to check whether [!DNL Sensor] is setting a cookie in the responses that the web server is returning to clients. If the collector is working, the web server returns a “v1st” cookie.

It is possible to rename the cookie. If you have done so, you must look for the name specified, not v1st.

You can perform this check using an automated script or monitoring agent. For a sample script or additional help with this task, please contact Adobe Consulting Services. 
