---
description: Modifying the ExpPartialMatch Parameter (Optional)
title: Modifying the ExpPartialMatch Parameter (Optional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
---
# Modifying the ExpPartialMatch Parameter (Optional){#modifying-the-exppartialmatch-parameter-optional}

If you want to enable your controlled experiments to remap your entire website or an entire subdirectory of your website to another location, you can set the ExpPartialMatch parameter in the [!DNL txlogd.conf] file to “on.” The default is “off.”

Following is an example of the ExpPartialMatch parameter:

[!DNL ExpPartialMatch off]

Be very careful when setting this parameter to “on” because it can result in an inadvertent remapping of your entire website.
