---
description: null
seo-description: null
seo-title: Modifying the ExpPartialMatch Parameter (Optional)
solution: Insight,Analytics
title: Modifying the ExpPartialMatch Parameter (Optional)
topic: Data workbench
uuid: 911bff4f-a387-4ebc-8b5d-1bc50c15ec42
index: y
internal: n
snippet: y
---

# Modifying the ExpPartialMatch Parameter (Optional){#modifying-the-exppartialmatch-parameter-optional}

If you want to enable your controlled experiments to remap your entire website or an entire subdirectory of your website to another location, you can set the ExpPartialMatch parameter in the [!DNL txlogd.conf] file to “on.” The default is “off.”

Following is an example of the ExpPartialMatch parameter:

[!DNL ExpPartialMatch off]

Be very careful when setting this parameter to “on” because it can result in an inadvertent remapping of your entire website. 
