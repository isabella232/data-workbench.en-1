---
description: The Unescape URI transformation unescapes any characters in a string that have been escaped.
seo-description: The Unescape URI transformation unescapes any characters in a string that have been escaped.
seo-title: UnescapeURI
solution: Analytics
title: UnescapeURI
topic: Data workbench
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
---

# UnescapeURI{#unescapeuri}

The Unescape URI transformation unescapes any characters in a string that have been escaped.

>[!NOTE]
>
>Escaped characters replace the unsafe characters in a URI string. They are represented by a triplet consisting of a percent sign followed by two hexadecimal digits (for example, %20).

|  Parameter  | Description  | Default  |
|---|---|---|
|  Name  | Descriptive name of the transformation. You can enter any name here.  | |
|  Comments  | Optional. Notes about the transformation.  | |
|  Condition  | The conditions under which this transformation is applied.  | |
|  Default  | The default value to use if the condition is met and the input value is not available.  | |
|  Input  | The URI string to be unescaped.  | |
|  Output  | The name of the field in which the unescaped string is to be stored.  | |

The following transformation unescapes the docname value in a HTTP header field and stores the output in the field x-docname-unescaped:

![](assets/cfg_TransformationType_UnescapeURI.png)

If the docname value were

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

then the value of x-docname-unescape would be

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]

