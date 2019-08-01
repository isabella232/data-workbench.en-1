---
description: When collecting event data from a web server, Sensor automatically sets a persistent cookie for each visitor containing a small random identifier, without capturing any personally identifying information.
seo-description: When collecting event data from a web server, Sensor automatically sets a persistent cookie for each visitor containing a small random identifier, without capturing any personally identifying information.
seo-title: How Does Sensor Identify Visitors and Sessions?
solution: Insight
title: How Does Sensor Identify Visitors and Sessions?
uuid: 367395e8-2cb5-47e3-b8ae-57f5729220d9
index: y
internal: n
snippet: y
---

# How Does Sensor Identify Visitors and Sessions?{#how-does-sensor-identify-visitors-and-sessions}

When collecting event data from a web server, Sensor automatically sets a persistent cookie for each visitor containing a small random identifier, without capturing any personally identifying information.

 This Adobe cookie is used to identify the unique visitor and all of its related sessions.

By default, [!DNL Sensor] captures all of the W3C Extended Log File Format fields from each HTTP header, but you can configure [!DNL Sensor] to capture any header that is transmitted between the client and server. For information about the event data fields collected by [!DNL Sensor] in [!DNL .vsl] files, see [Event Data Record Fields](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).

Some visitors’ browsers do not store cookies persistently, and a very small number of visitors’ browsers do not accept cookies at all (even session cookies). Even though they account for only a fraction of a site’s total traffic, they can result in significant miscounting if each page view by such a visitor is counted incorrectly as an entire session, as is done by some log file analysis software. Adobe addresses this problem by enabling you to analyze visitors with and without using cookies.

For more information about the Broken Sessions Filter, see the *Data Workbench Sensor Guide*. 
