---
description: You must install and run Sensor on each web server that serves the content for your site to collect all of the requests that are seen by those servers.
title: How Do I Acquire this Data_
uuid: c0d8b01e-a135-4ef7-8159-811766929f62
exl-id: 1c886f60-eae9-48c2-b641-396c622035d4
---
# How Do I Acquire this Data_{#how-do-i-acquire-this-data}

You must install and run Sensor on each web server that serves the content for your site to collect all of the requests that are seen by those servers.

 These requests make up 90% or more of the requests made to your site and 90% or more of the data that is needed for the complete analysis of your site's traffic. [!DNL Page Tags] should then be used to collect the remaining 10% or less of the traffic data that is not known to your web servers. The following, however, are valid configurations for the collection of web request data from your site, in order of preference, based on our operational experience: 

1. [!DNL Sensor] is installed on each web server that you control and that supports your site. Content from third-party sites, content served from cache, and certain types of dynamic content should be tagged, and such page tags should send the data that they collect to a web server at your location that is running [!DNL Sensor]. You may add an additional web server if the level of page tag request traffic justifies such, or in special cases, dedicate a web server to collect these page tag requests.
1. [!DNL Sensor] is installed on two web servers, also referred to as data collection servers in this guide, at your location that are dedicated to collecting page tag request data from tagged pages. All content on your site is tagged and all page tags are directed to the two data collection servers.
1. [!DNL Sensor’s] data collection services are provided by an outsourcer that runs data collection servers to collect all of your web request data. In this case, all content on your site is tagged and the page tags send their data to the outsourced data collection servers.

   For more information about [!DNL Sensor], see the *Data Workbench [!DNL Sensor] Guide*.
