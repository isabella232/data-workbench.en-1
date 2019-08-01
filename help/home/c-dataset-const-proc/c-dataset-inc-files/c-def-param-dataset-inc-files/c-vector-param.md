---
description: Vector parameters contain multiple values for a single variable.
seo-description: Vector parameters contain multiple values for a single variable.
seo-title: Vector Parameters
solution: Analytics
title: Vector Parameters
topic: Data workbench
uuid: 725a8aab-22b2-4aa7-9cc6-cb958b01907b
index: y
internal: n
snippet: y
---

# Vector Parameters{#vector-parameters}

Vector parameters contain multiple values for a single variable.

 You can reference vector parameters only as the sole item of a vector. This example shows a [!DNL Transformation Dataset Include] file that defines a vector parameter. The vector parameter, "Internal Domains," consists of three values.

![](assets/cfg_WebParameters_InternalDomains.png)

Note that the vector parameter is the only item listed for the [!DNL Matches] vector in the [!DNL String Match] condition.

![](assets/cfg_Parameters_InternalDomains_Ref.png)

For more information about internal domains, see [Configuration Settings for Web Data](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519). For information about the [!DNL String Match] condition, see [Conditions](../../../../home/c-dataset-const-proc/c-conditions/c-conditions.md#concept-9a576a00d5db48e7a599016c441e39e0). 
