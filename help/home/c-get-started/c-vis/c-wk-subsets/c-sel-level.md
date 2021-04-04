---
description: When you create a subset, you must specify a level.
solution: Analytics
title: Select a level
topic: Data workbench
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
---
# Select a level{#select-a-level}

When you create a subset, you must specify a level.

A level is any countable dimension. For example, if you are working with website data, if you select the element Tue from the Day of Week dimension and create a subset, you must select the level that you want to view: Page View, Session, or Visitor.

* **Day of Week=“Tue” by Page View:** The page view level shows you only those page views that occurred on a Tuesday.

  ![](assets/vis_Subset_byPageView.png)

* **Day of Week=“Tue” by Session:** The session level shows you only those sessions that occurred on a Tuesday.

  ![](assets/vis_Subset_bySession.png)

* **Day of Week=“Tue” by Visitor:** The visitor level shows you all of the visitors who came to the site on Tuesdays, but it also shows other days that those same visitors came to the site.

  ![](assets/vis_Subset_byVisitor.png)
