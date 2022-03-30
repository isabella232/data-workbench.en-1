---
description: A typical configuration of Site uses cookies to uniquely identify visitors to your website and track their behavior over time.
solution: Analytics
title: How Does Site Identify Visitors?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
---
# How Does Site Identify Visitors?{#how-does-site-identify-visitors}

A typical configuration of Site uses cookies to uniquely identify visitors to your website and track their behavior over time.

The first time that a particular browser (considered a visitor) makes a request of your website, [!DNL Sensor] works with your web server to set a persistent cookie (by default [!DNL cs(cookie)(v1st)]), which is interpreted internally within the system as [!DNL x-trackingid]. This cookie is set only once, on the very first request made to your website by that visitor. It then is collected from that visitor each time that browser makes a request (either page or embedded object request) of your website in the future.

Accepting a persistent cookie is at the browser’s discretion. If a user does choose to block persistent cookies, their page view requests are still logged, but the measurement data from those requests are not correlated to a particular visitor or their sessions on the website unless you implement an alternate method of visitor identification, such as using the Hash transformation on the IP and UserAgent fields.

>[!NOTE]
>
>Site experiments can be analyzed only in datasets where the only method of visitor identification in use is the [!DNL Sensor] set persistent cookie method. Sensors running on J2EE servers (JBoss, Tomcat, WebLogic, and WebSphere) do not support controlled experimentation.

During a controlled experiment, users who do not accept cookies could be placed in different experiment groups from one click to the next. This becomes an issue only if you perform your test analysis with the Broken Session Filter turned off in [!DNL Insight], which Adobe does not recommended.

For more information about the Broken Session Filter, see the * [!DNL Insight] User Guide*.

If a visitor clears the cookie during an experiment, the visitor is assigned a new cookie and potentially could be assigned to a different group. Because Adobe identifies the visitor as new, the experiment is not invalidated.
