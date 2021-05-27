---
description: The Insight Server enables you to define countable, simple, many-to-many, numeric, denormal, and time dimensions for inclusion in your data set.
title: Types of Extended Dimensions
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
---
# Types of Extended Dimensions{#types-of-extended-dimensions}

The Insight Server enables you to define countable, simple, many-to-many, numeric, denormal, and time dimensions for inclusion in your data set.

 Each dimension type has a set of parameters whose values you edit to provide specific instructions for the Insight Server to create the dimensions during the transformation phase of data set construction.

While some of the parameters differ among the dimension types, all require the specification of a parent dimension (the Parent parameter). The parent dimension determines which log entries from the log sources are provided as input to the new dimension. In other words, the log entries that are associated with the elements of the parent dimension are the ones that are associated with the new dimension before any filtering is applied. The parent dimension also determines the new dimension's position within the data set's hierarchy, referred to as the data set schema. For information about the interface that shows the data set schema, see [Dataset Configuration Tools](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

After the Insight Server uses the parent dimension to determine which log entries should be considered in the creation of the dimension, it applies the specified condition(s) (the Condition parameter) to blank the log entries that do not satisfy the condition. The server then identifies the value of the specified input field (the Input parameter) for each log entry and applies the specified operation (the Operation parameter), if applicable.

>[!NOTE]
>
>If a log entry does not satisfy an extended dimension's Condition, the Insight Server substitutes blank values for all of the fields in the log entry. The actual log entry still exists, and the specified Operation determines whether the blank value of the [!DNL Input] field is used.
