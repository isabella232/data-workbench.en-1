---
description: The query string (cs-uri-query) is often used by web applications and site developers to pass information from page to page because of the stateless nature of HTTP.
solution: Analytics
title: Understanding the Query String
topic: Data workbench
uuid: 7403277d-fbce-4e98-bd42-894142e38d0d
exl-id: b5281e5f-3eb7-4d6a-a7b3-9958cb430621
---
# Understanding the Query String{#understanding-the-query-string}

The query string (cs-uri-query) is often used by web applications and site developers to pass information from page to page because of the stateless nature of HTTP.

 In many cases, information may be passed in the query string when it is acquired by [!DNL Sensor] at the web server. Such information can be used by [!DNL Site] to illuminate the true structure of the site, and the path of visitors through it, as well as other information.

In some dynamic websites, name=value pairs (variables) in the query string are important for determining the actual page being requested by a visitor. In such cases, URLs may be structured in the following or similar manner:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```

In this example, PAGENAME is actually the indicator of what page will be served to the requester of this URL. Many web log analysis tools and services limit a site operator’s ability to define what a page is in their site based on what query string variables occur in the query strings of the site’s URLs. The data workbench server and data workbench can be configured to use such query names to define unique pages. This is important because many systems would interpret the following URLs as the same page, but [!DNL Site] does not.

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
http://www.myserver.com/pageserved.asp?PAGENAME=HOME2
```

Similarly, site developers and applications often add many query string variables into a site’s URLs that have nothing to do with identifying the actual page that is being requested. Examples are shown below:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10001
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10002
http://www.myserver.com/pageserved.asp?PAGENAME=HOME&CAMPAIGN=10003
```

In this example, the query string variable CAMPAIGN= has been added to the URL. This CAMPAIGN variable is being used to indicate which marketing campaign caused a visitor to select this URL. [!DNL Site] can be configured to use this CAMPAIGN information, yet separate it from the definition of what page a visitor viewed so that in your list of pages for reporting and analysis purposes you would simply see the following:

```
http://www.myserver.com/pageserved.asp?PAGENAME=HOME
```
