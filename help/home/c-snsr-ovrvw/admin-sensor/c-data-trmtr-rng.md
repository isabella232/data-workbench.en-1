---
description: Check whether the transmitter is running by setting up alerts, checking the system status of the Sensor, and more.
solution: Analytics
title: Confirming that the Data Transmitter is Running
uuid: 8dd6307c-e7d2-4800-88c7-f93385b33ca5
exl-id: 10ba704e-85be-425f-8a5d-9429100f367d
---
# Confirming that the Data Transmitter is Running{#confirming-that-the-data-transmitter-is-running}

Check whether the transmitter is running by setting up alerts, checking the system status of the Sensor, and more.

 **Recommended Frequency:** Every 5-10 minutes

* [Check that the transmitter process is running.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-79806fa3b7034a8eaf571a66e24874d7) 
* [Set up administrative alerts in Insight Server.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-d98e0f18b8fb45a78419fe75610a3b1e) 
* [Check the System Status of the Sensor.](../../../home/c-snsr-ovrvw/admin-sensor/c-data-trmtr-rng.md#section-de9d7e359242487a9fbead4ed65aebbc)

## Checking the Transmitter Process {#section-79806fa3b7034a8eaf571a66e24874d7}

One way to verify that the transmitter is running is to check that the [!DNL Sensor] transmitter process is running on each web server where a [!DNL Sensor] instance is installed. The transmitter process appears as “txlogd” in the web server’s list of processes. You can perform this check using a system monitoring tool.

## Setting Up Administrative Alerts in the Data Workbench Server {#section-d98e0f18b8fb45a78419fe75610a3b1e}

Another way to verify that the transmitter is running is to set up automated administrative alerts in the [!DNL data workbench server]. When administrative alerts have been configured, the [!DNL data workbench server] generates an email alert when it has received no data from a configured and previously connected [!DNL Sensor] within the time frame specified in the [!DNL Sensor] Alert Timeout (min) parameter in the [!DNL data workbench server’s] [!DNL Administrative Alerts.cfg] file. For more information about setting up administrative alerts, see the *Server Products Installation and Administration Guide*.

## Checking the System Status of the Sensor {#section-de9d7e359242487a9fbead4ed65aebbc}

Yet another way to verify that the transmitter is running is to manually check the [!DNL Servers Manager] in Data Workbench.

**To view the [!DNL Servers Manager]**

* In Data Workbench, right-click within a workspace, click **[!UICONTROL Admin]**, then under [!DNL Manage], click **[!UICONTROL Servers]**.

If the icon for a [!DNL Sensor] is green, the transmitter is running.

For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench [!DNL Sensor] Guide*.
