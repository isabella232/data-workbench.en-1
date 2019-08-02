---
description: Site uses cookies to uniquely identify visitors to your website and track their behavior over time.
seo-description: Site uses cookies to uniquely identify visitors to your website and track their behavior over time.
seo-title: Understanding the v1st Cookie
solution: Analytics
title: Understanding the v1st Cookie
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
index: y
internal: n
snippet: y
---

# Understanding the v1st Cookie{#understanding-the-v-st-cookie}

Site uses cookies to uniquely identify visitors to your website and track their behavior over time.

The first time that a particular browser (considered a visitor) makes a request of your website, [!DNL Sensor] works with your web server to set a persistent cookie, cs(cookie)(v1st), which is interpreted internally within the system as x-trackingid. This persistent cookie is set in addition to any other cookie that your site may otherwise set. This cookie optimizes your ability to track your visitors over multiple sessions, which enables many types of analysis that are otherwise impossible.

[!DNL Sensor] assigns a 64-bit numeric key in the cookie to identify new visitors that make a request of the site as a unique identifier. When the [!DNL Sensor] sees a request from a browser, it checks to see whether “cs(cookie)(v1st)”, a first-party persistent cookie set by [!DNL Sensor], exists in the request data. If the cs(cookie)(v1st) is not present, [!DNL Sensor], through your web server, tells the browser to set it. Unlike other solutions, [!DNL Sensor] is able to set this cookie on the visitor’s first request.

Below is the standard persistent cookie header sent to the browser on its first request of your site by your web server, at the direction of [!DNL Sensor]. The format can be defined at the time of configuration if a different name or expiration date is desired. For example:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

This cookie is set just once, on the very first request made to your site by that visitor. It then is collected from that visitor each time that browser makes a request (either page or embedded object request) of your site in the future. The cookie is very small in size to minimize the amount of bandwidth used to transmit it to your servers with each request from that browser to your site.

Accepting a persistent cookie is at the browser’s discretion. Most web users understand what cookies do and also recognize that first-party cookies provide a valuable benefit to them in allowing site content to be customized to their preferences. These first-party cookies are not blocked by the default security settings of the popular browsers. If a user does choose to block first-party cookies, their page view requests are still logged, but the measurement data from those requests cannot be reliably correlated to a particular visitor or their sessions on the site. Many sites, especially sophisticated dynamic sites, already use first-party cookies, which are in many cases necessary to enable web applications to operate for the visitor. A step back from a persistent cookie is a session cookie, which allows a series of requests to be knit together into a session, but does not allow inter-session visitor tracking. [!DNL Site] is capable of sessionizing visitor data based on session cookies or by IP number, but both methods significantly detract from the types and value of analysis that can be conducted with [!DNL Site] or any other web activity analysis and reporting system. 
