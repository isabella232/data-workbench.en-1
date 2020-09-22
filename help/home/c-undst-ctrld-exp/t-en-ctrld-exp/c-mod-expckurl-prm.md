---
description: The ExpCookieURL parameter can be used to test that your controlled experiment is working properly.
solution: Analytics,Analytics
title: Modifying the ExpCookieURL Paramter (Optional)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
---

# Modifying the ExpCookieURL Paramter (Optional){#modifying-the-expcookieurl-paramter-optional}

The ExpCookieURL parameter can be used to test that your controlled experiment is working properly.

 This parameter defines the URL of a virtual page that when requested places you into a specified experiment and group and then redirects you to the root of your website. From that point through the end of the experiment, you are part of the specified experiment and group.

The default page for this parameter is [!DNL setcookie.htm], but you can use any valid virtual URL.

>[!NOTE]
>
>This must be a virtual URL and must not be a real page or piece of existing content. There should be no file on the web server at the specified path with the specified name.

Following is an example of the ExpCookieURL parameter:

[!DNL ExpCookieURL /setcookie.htm] 
