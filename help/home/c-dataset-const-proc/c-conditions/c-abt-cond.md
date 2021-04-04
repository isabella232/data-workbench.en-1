---
description: Transformations and dimensions use conditions to determine when certain instructions or actions apply to log fields.
solution: Analytics
title: About Conditions
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
---
# About Conditions{#about-conditions}

Transformations and dimensions use conditions to determine when certain instructions or actions apply to log fields.

The Log Entry Condition parameter uses conditions to determine which log entries should be included in the dataset construction process. This appendix describes the different types of conditions available within data workbench server.

A condition falls into one of two categories:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression], and [!DNL String Match] conditions are used to test for different states in the available log fields. 

* **[!DNL Boolean Operations]:** The [!DNL And], [!DNL Or], and [!DNL Neither] conditions are used to combine the test operations described above. For example, if you have a [!DNL Range] condition and a [!DNL String Match] condition that must both be false to take the appropriate action, you would make these two operations children of the [!DNL Neither] condition. Note that the [!DNL And] condition is used as the root of all condition testing in the system.
