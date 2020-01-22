---
description: Profile filters constrain the scope of the data available from a dataset.
solution: Analytics
title: Built-in Profile Filters
topic: Data workbench
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
---

# Built-in Profile Filters{#built-in-profile-filters}

Profile filters constrain the scope of the data available from a dataset.

In addition to the log processing and transformation filters that can be applied before or during the creation of a dataset, other profile filters are available that impact the scope of the data available for selection from a dataset. This section describes only the latter type of special filters.

The following profile filters are available to the user after a dataset has been created:

* Data Subsetting Filter 
* Broken Session Filter

>[!NOTE]
>
>Additional filters can be created and applied through their presence in a profile's Filters directory.

## Data Subsetting {#section-0defb44315d94254ab6e629ec3d6f420}

A data subset acts as a data filter by allowing you to select only the dimension elements of data that are of interest to you.

Creating data subsets decreases the amount of time required to calculate exact answers to your queries. If the data subset that you specify is small enough, Data Workbench can retrieve all needed data from Insight Server and answer questions about the subset quickly and accurately. This is especially useful if you know that, for example, analyzing a day of data or sessions from a particular referrer will require several hours.

Users can create data subsets themselves, or they can access data subsets defined in an inherited or working profile. When a user creates a subset of the dataset (by selecting the desired data in Insight and then right-clicking in the workspace and clicking Data > Subset), a Data Subset.filter file is created in the Filters folder within the User profile directory. This filter defines the data subset that you have selected and saves the subset for future use.

>[!NOTE]
>
>You can create multiple data subsets and can toggle them to view different portions of the data. Remember to turn off Data Subsetting when you want to view all data. Otherwise, your metric values will not be representative of all data in the dataset.

## Broken Session Filter {#section-1608e97da6464b11aea27cbb7f3160e4}

The Broken Session Filter is a metric formula that can be easily modified to meet any filtering requirements. In the default Site profiles, the Broken Session Filter is configured to include all visitors that have a Visitorized Flag that is set to 1. The value 1 indicates the presence of a tracking cookie for that visitor.

Following is the text of the default Broken Session Filter.filter file provided by Adobe in the release package for the Site profiles.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

By default, workspaces have the Broken Session filter applied to both their selection and their benchmarks, and it can be toggled by right-clicking in the workspace and clicking Data > Broken Session Filter.

The Broken Session Filter can be referenced in filter expressions as Broken_Session_Filter, even if it is not enabled for the current workspace. See [filter expressions](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) for additional information. 
