---
description: Metric, dimension, and filter expressions can use identifiers to refer to named metrics, dimensions, and filters.
seo-description: Metric, dimension, and filter expressions can use identifiers to refer to named metrics, dimensions, and filters.
seo-title: Syntax for identifiers
solution: Analytics
title: Syntax for identifiers
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
---

# Syntax for identifiers{#syntax-for-identifiers}

Metric, dimension, and filter expressions can use identifiers to refer to named metrics, dimensions, and filters.

 These identifiers are case sensitive and must be typed exactly as they are defined.

A valid identifier can contain one or more of the following:

* Underscores (_). Underscores in an identifier represent spaces in the metric, dimension, or filter name. For example, the Session Referrer dimension would be referred to as [!DNL Session_Referrer] in an expression. 
* Percent signs (%) 
* Upper case letters (A-Z) 
* Lower case letters (a-z) 
* Dollar signs ($) 
* Numbers (0-9), except as the first character in an identifier. 
* Non-ASCII characters

All other characters are illegal in an identifier.

These same rules apply to the names of metrics, dimensions, and filters when they are used outside of expressions, except that the names can contain spaces but not underscores. For example, you can define the Session Referrer dimension in the [!DNL Transformation.cfg] file as Session Referrer, but not [!DNL Session_Referrer]. 
