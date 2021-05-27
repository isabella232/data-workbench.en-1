---
description: Value Profile Metrics
title: Value Profile Metrics
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
---
# Value Profile Metrics{#value-profile-metrics}

|  Metric  | Formula  | Level  | Description  |
|---|---|---|---|
|  Conversion  | `Sessions[not Session_Value=#0]/Sessions`  | Session  | The percentage of sessions which generated business value (as defined by the Business Value Model).  |
|  Pct of Value  | `Value/total(Value)`  | Session  | The percentage of overall value that was generated from the selected set of sessions.  |
|  Value  | `sum(Session_Value, Session)*0.01`  | Session  | The total business value generated, in dollars (as defined by the Business Value Model).  |
|  Value Events  | `Sessions[not Session_Value=#0]`  | Session  | The count of sessions that generated business value (as defined by the Business Value Model).  |
|  Value Events per Visitor  | `(Value_Events/Visitors) by Visitor`  | Visitor  | The average number of sessions for each visitor that generated business value (as defined by the Business Value Model).  |
|  Value per Visitor  | `(Value/Visitors) by Visitor`  | Visitor  | The average business value generated, in dollars, by each visitor.|
