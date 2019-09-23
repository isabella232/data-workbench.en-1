---
description: Conceptual information about third-party tagging and preventing cookie-blocking using P3P.
seo-description: Conceptual information about third-party tagging and preventing cookie-blocking using P3P.
seo-title: P3P Considerations for Third-Party Page Tagging
solution: Analytics
title: P3P Considerations for Third-Party Page Tagging
topic: Data workbench
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
---

# P3P Considerations for Third-Party Page Tagging{#p-p-considerations-for-third-party-page-tagging}

Conceptual information about third-party tagging and preventing cookie-blocking using P3P.

## Understanding Third-Party Page Tagging {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

In most implementations, the Adobe persistent cookie is viewed as a first-party cookie. First-party cookies are defined as those associated with the host domain.

Suppose a user visits http://www.example.com/. Assuming that a Sensor is installed and operational on the web server hosting the domain, an Adobe persistent cookie is set and viewed as a first-party cookie. You may, however, want to collect measurement data from a third-party site through the use of embedded objects, which are requested and loaded from your server that is running [!DNL Sensor] instead of from the third-party server hosting the page or advertising program. For example, http://www.example2.com/ serves a web page with an embedded object request served from http://www.example.com/. The request for the embedded object from http://www.example.com/ results in a cookie being set; however, in this context, the web browser or user-agent views the cookie as a third-party cookie.

In newer web browsers such as Microsoft’s IE6, privacy features filter cookies based on their compact policies sent in the HTTP response header from the web server. In the default IE6 settings, which most users never change, third-party cookies are blocked when they have nonexistent or unsatisfactory compact policies. Most sites that are experiencing cookie-blocking problems have third-party cookies on their site that do not have the appropriate compact policies being sent in the HTTP response header. Additionally, some cookie-blocking problems occur when a site is framed by another site. For example, an online store that is part of an online shopping portal may appear in a frame provided by the portal. From the perspective of the browser, the store content may appear to be third-party content when framed by the portal. However, if a visitor goes directly to the online store without going through the portal, the content will be first-party content. Thus, the online store finds their cookies are blocked only when visitors come in through the portal.

Web-based mail systems cause a similar problem. If a website visitor emails a web page to a friend who uses a web-based mail system, the email message appears as third-party content to the friend’s browser because it is framed by the email system. If there are any cookies associated with the page that was emailed, they are treated as third-party cookies by IE6.

## Using P3P to Prevent Cookie-Blocking {#section-96831cad887649f295aec6931750e41a}

P3P provides a standard way for websites to encode their privacy policies in a computer-readable XML format. P3P-enabled web browsers and other P3P user agents automatically fetch P3P privacy policies, parse them, and compare them with a user’s privacy preferences.

To prevent IE6 from blocking cookies on your site, you need to ensure the following:

1. All of the cookies that are being set in a third-party context have P3P compact policies associated with them. 
1. The appropriate compact policy is sent using a custom HTTP response header. 
1. Those compact policies are considered satisfactory by IE6. 
1. If the third-party cookies are being set by another company, you may need to ask them to enable P3P and set P3P compact policies. Any host that sets a P3P compact policy also must have a corresponding full P3P policy. Users can change their IE6 settings so that cookies are blocked under other conditions as well; however, placing satisfactory compact policies on third-party cookies prevents most IE6 cookie-blocking.

The following is an example of such a P3P header:

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

In this example, the file [!DNL p3p.xml] is used to reference an associated [!DNL policy.xml] file residing on your web server that denotes the kinds of information your website collects, dispute resolution methods that your organization adheres to, how the data collected is used, who owns the data, and other standard information related to Internet Privacy. The three character codes following the “CP” are the compact policy codes that emulate what is stated within your [!DNL policy.xml] file.

All compact policies and policy XML files should be tailored for the respective organization for which they are being deployed, accurately specifying their internal privacy policies with regard to website data collection. A multitude of P3P policy editors can be found online along with more in-depth information relative to implementing an appropriate privacy policy within your website.

For more information on how Internet Explorer 6 handles P3P Headers, please visit:

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp) 
