---
description: The ReplaceURI transformation changes the value in the internal URI dimension to a new value.
seo-description: The ReplaceURI transformation changes the value in the internal URI dimension to a new value.
seo-title: ReplaceURI
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
---

# ReplaceURI{#replaceuri}

The ReplaceURI transformation changes the value in the internal URI dimension to a new value.

 If [!DNL URI Prefix] is specified, the resulting value is simply the URI prefix concatenated with the provided input value.

|  Parameter  | Description  | Default  |
|---|---|---|
|  Name  | Descriptive name of the transformation. You can enter any name here.  |  |
|  Comments  | Optional. Notes about the transformation.  |  |
|  Condition  | The conditions under which this transformation is applied.  |  |
|  Default  | The default value to use if the condition is met and the input value is not available.  |  |
|  Input  | The value to replace the URI.  |  |
|  URI Prefix  |The value (string) to be prepended to the value in the [!DNL Input] field.  |  |

>[!NOTE]
>
>Before applying [!DNL ReplaceURI] transformations, you should create a new simple dimension with a parent of [!DNL Page View]from a copy of cs-uri-stem or cs-uri. For assistance with this, contact Adobe.

This example demonstrates the use of [!DNL ReplaceURI] to replace the "page=*pageid*" query strings with " [!DNL homepage.html]" whenever *pageid* indicates that the website's homepage was viewed. The end result is a more user-friendly view of the URI.

![](assets/cfg_TransformationType_ReplaceURI.bmp)

For the transformation shown, the page

* [!DNL www.examplesite.com/info.html?page=1550]

would be changed to

* [!DNL www.examplesite.com/homepage.html]

