---
description: Test results must be clear and meaningful so that you can feel confident making large dollar decisions based on those results.
seo-description: Test results must be clear and meaningful so that you can feel confident making large dollar decisions based on those results.
seo-title: What Should I Test?
solution: Insight,Analytics
title: What Should I Test?
topic: Data workbench
uuid: 83685b88-cd9e-43cb-b9f8-3f8a815c68fd
index: y
internal: n
snippet: y
---

# What Should I Test?{#what-should-i-test}

Test results must be clear and meaningful so that you can feel confident making large dollar decisions based on those results.

Although you can test various page layouts with [!DNL Sensor] and Site, Adobe suggests that you focus on testing high-value, strategic business initiatives, or new or redesigned website functionality that address the goals that you have set for your website as well as for your business. You can test for such issues as best price guarantees, personalization functionality, market offers (for example, packages or bundles), creative design, and application processes.

The following concepts are most important when developing your controlled experiment:

* **Understand the right changes to make.** This requires some research into how your website functions and the business processes underlying the front-end website. You want to make changes that provide the most impact and can be tested easily. 
* **Small changes can have significant impact.** Not all of the changes that you test need to be drastic to have a significant impact on your business. Always be open to making small, but very important changes.

## Supported Methodologies {#section-1071adaf54c64ba9bc5ef228c4a23635}

Many types of experiments with many different goals can be performed using Site. The following list provides a few examples:

* Altering pages, content, and website processes to improve conversion rates. 
* Changing marketing campaigns, promotions, cross-sells, and up-sells to increase revenue. 
* Varying page load times to understand customer quality of service and the actual value of infrastructure performance.

To reach these goals, Site supports the following types of methodologies for controlled experimentation and testing:

* **Page Replacement:** Replace static URL X with static URL Y. This methodology is of limited use in a dynamic environment. 
* **Dynamic URI Replacement:** This is a variant of Page Replacement that replaces static page X with dynamic page Y to render dynamic content. 
* **Object Replacement:** Replace fixed object X with fixed object Y. 
* **Content Replacement:** Replace content set X (multiple objects, pages, table, and so on) with content set Y. 
* **Experiment Variable Replacement:** Replace JavaScript object /writeCookie_X.js with JavaScript object /writeCookie_Y.js to write a cookie that can be used by a back-end system to serve particular content.

>[!NOTE]
>
>Controlled experiments are based on URI replacement, not query string replacement. The URI within a particular URL is highlighted in the following example: 
>
>```>
>http://www.omniture.com/index.asp?id=1
>```>
>For example, in your controlled experiment you could specify that the control group URI [!DNL index.asp] be replaced with the test group URI [!DNL index2.asp] to determine which page design would result in more value.

