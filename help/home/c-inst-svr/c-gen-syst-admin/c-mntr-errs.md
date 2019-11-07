---
description: To detect system and application errors as soon as possible and address them before they cause major problems or outages, you should regularly monitor your event logs.
solution: Insight
title: Monitoring Events for Errors
uuid: 09bb34db-e24d-4bc5-84d2-7fc37df60681
---

# Monitoring Events for Errors{#monitoring-events-for-errors}

To detect system and application errors as soon as possible and address them before they cause major problems or outages, you should regularly monitor your event logs.

 **Recommended Frequency:** Every 5-10 minutes

To monitor your Adobe server software products, your automated management tool can be set to monitor your event log for errors with the source “Adobe” and then alert appropriate personnel to issues that may require intervention.

In Windows, application error messages are output to the Application Event Log in Windows, which you can access using the Windows Event Viewer. In Unix, application error messages are output to the Unix syslog using the LOG_DAEMON facility.

**To open the Windows Event Viewer**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

