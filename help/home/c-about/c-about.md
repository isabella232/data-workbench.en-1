---
description: Metrics, dimensions, and filters provide a framework within which calculations are made about the data processed into a data workbench dataset.
seo-description: Metrics, dimensions, and filters provide a framework within which calculations are made about the data processed into a data workbench dataset.
seo-title: Data Workbench Metrics, Dimensions, and Filters
solution: Analytics
title: Data Workbench Metrics, Dimensions, and Filters
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
index: y
internal: n
snippet: y
---

# Data Workbench Metrics, Dimensions, and Filters{#data-workbench-metrics-dimensions-and-filters}

Metrics, dimensions, and filters provide a framework within which calculations are made about the data processed into a data workbench dataset.

The results of the calculations defined using this framework are shown in workspaces, dashboards, reports, or other outputs. In short, any number that you see in or from an application is the result of a query of a dataset that involves a metric, a dimension, and a filter.

At the most basic level, a metric describes what is being calculated from and about the dataset, a dimension breaks down the data in the dataset into categories, and a filter describes a selected portion or subset of the data in the dataset.

When the Data Workbench Server processes data to create a dataset, dimensions of the data are created and then updated on an ongoing basis as new data is read and processed by the server. Metrics and filters are calculated from these dimensions of data.

>[!CAUTION]
>
>If you redefine an internal metric, the system will behave unexpectedly because of the wrong value. Your reports will not generate unless a metric reads 100%. It is recommended that you do not change metric definitions.

## An Example {#section-ecc465d1a5e34d559c1983e96fa409ec}

Imagine a dataset that contains information about all of the people in the world. This dataset contains, at a minimum, all of the people in the world and their ages. A useful metric to calculate from this dataset would be Average Age. Evaluating this metric would result in one number: the average age of the world’s population.

Adding a dimension to the dataset makes this information more useful and manageable. If the dataset also contains each person’s country of residence, defining a Country dimension would provide a way to segment the people into groups for each country in the world. Evaluating the Average Age metric over the Country dimension would result in a list of numbers, one for each country, each representing the average age of the people in that country.

The application of a filter (or selection filter) in a metric formula can give more detailed information or allow the definition of a new metric based on existing metrics and dimensions. Evaluating the Average Age metric with a filter of “where country equals Sweden” results in one number: the average age of people in Sweden. A metric based on this filter could be Swedish Average Age.

For example:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## How Metrics, Dimensions, and Filters Relate {#section-28622596124140b280e6b993b174ef84}

In general, evaluating a metric over a dimension results in that metric being evaluated for each dimension element (or element). In the example above, the Country dimension has an element for each country of the world. Evaluating Average Age over Country would yield the average age for each of the elements (countries), including the element Sweden.

It is important to note that when you evaluate a metric over a dimension, you will receive the same numerical result for a specific dimension element regardless of whether you evaluate that metric for the whole dimension or you define a filter corresponding to that specific dimension element. Using the previous example, when looking for the average age of people in Sweden, either of the following methods would yield identical results:

* Evaluate the Average Age metric over the Country dimension and then look at the number for the dimension element Sweden. 
* Evaluate the Average Age metric with a filter of “people in Sweden” (expressed as [!DNL Average_Age[Country='Sweden']]).

Filters are syntactical expressions that reference one or more dimensions and dimension elements. As you saw in the above example, using the expression [!DNL [dimension=element]] is an easy way to specify a filter.

It is just as easy to apply such a filter to define a new metric using an expression such as [!DNL New_Metric=Metric[Filter]]. Such a filter can be used to define a new metric based on a specific dimension element. To use the above example, [!DNL Average_Age[Country='Sweden']]specifies a metric for the average age of people in Sweden. If we were to give this metric a name, such as Swedish_Average_Age, we could use it in other calculations as a metric. For example, evaluating [!DNL Swedish_Average_Age/Average_Age] would result in a single number: the ratio of the average age of people in Sweden to that of people in the rest of the world.

If the dataset with information about all of the people in world also includes a dimension Eye Color, the expression [!DNL Swedish_Average_Age[Eye_Color='green']] would result in the average age of Swedes with green eyes. You might also obtain this same result without using an intermediate metric definition by applying a different filter: [!DNL Average_Age[Country='Sweden' AND Eye_Color='green']]. In this case, the [!DNL AND] operator specifies a filter expression using two other basic filter expressions. 
