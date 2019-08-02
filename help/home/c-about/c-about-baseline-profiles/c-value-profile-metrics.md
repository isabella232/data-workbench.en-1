---
description: null
seo-description: null
seo-title: Value Profile Metrics
solution: Analytics
title: Value Profile Metrics
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
index: y
internal: n
snippet: y
---

# Value Profile Metrics{#value-profile-metrics}

|  Metric  | Formula  | Level  | Description  |
|---|---|---|---|
|  Conversion  | [!DNL Sessions[not Session_Value=#0]/Sessions]  | Session  | The percentage of sessions which generated business value (as defined by the Business Value Model).  |
|  Pct of Value  | [!DNL Value/total(Value)]  | Session  | The percentage of overall value that was generated from the selected set of sessions.  |
|  Value  | [!DNL sum(Session_Value, Session)*0.01]  | Session  | The total business value generated, in dollars (as defined by the Business Value Model).  |
|  Value Events  | [!DNL Sessions[not Session_Value=#0]]  | Session  | The count of sessions that generated business value (as defined by the Business Value Model).  |
|  Value Events per Visitor  | [!DNL (Value_Events/Visitors) by Visitor]  | Visitor  | The average number of sessions for each visitor that generated business value (as defined by the Business Value Model).  |
|  Value per Visitor  | [!DNL (Value/Visitors) by Visitor]  | Visitor  | The average business value generated, in dollars, by each visitor.  |

