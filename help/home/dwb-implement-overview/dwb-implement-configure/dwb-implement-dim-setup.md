---
description: This section explains the different types of Dimensions and how to set them up in DWB.
title: Dimension Setup
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
---

# Dimension Setup{#dimension-setup}

This section explains the different types of Dimensions and how to set them up in DWB.

## What are Dimensions {#section-dac631943df24706827cedc6f0641543}

At the most basic level, dimensions are categories into which the data in the dataset can be broken down.

Best Practice: Dimensions in the data schema can be provided any name. Dimension names used and explained in this course are considered a best practice. Dimensions can be named differently. As you gain exposure to other datasets, you will begin to see differences in datasets. It is important to understand the purpose of the dimensions rather than their name. For example, whether it is called "Visitor", "Customer", "Person", "Consumer", or "User", it is important to understand that these are terms commonly use to refer to the highest level countable dimension that is being used to gather information about a singular person.

For complete information, see the [Dataset Configuration](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) guide.

## Types of Dimensions in DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

There are two types of dimensions in Data Workbench: Extended Dimensions and Derived Dimensions.

Extended Dimensions are created from fields in the "raw" data files. Extended dimensions are used to categorize "raw" data and to specify the relationships that exist among the data. Extended dimensions are created by Data Workbench Architects.

Derived Dimensions are created by a user "on the client- side" after the dataset has been processed using existing Extended dimension definitions. For example, based on the existing URI dimension, a user may choose to create a derived Page Name dimension, which displays a more user-friendly page name in place of a given URI. All dimensions consist of elements or items that have been categorized (grouped) together to form the dimension. Below are three dimensions and their elements.

Many derived dimensions are created automatically to drive different types of visualizations. For example, when a user builds a site or process map, DWB servers create a Prefix dimension. Others, such as the reporting time dimensions, are defined by files in the Dimensions directory of a profile.

>[!NOTE]
>
>The elements appearing in any given dimension will only reflect those values that exist in records that have been chosen to be loaded into the dataset. For instance, if there is no data for "May '12", then that month will not appear in the 'Month' dimension.

## Extended Dimensions {#section-5fc51fa539034941a30a2df606f7d727}

Types of Extended Dimensions

**1) Countable Dimensions**

At the highest level are countable dimensions. Countable dimensions serve two major functions. First, they are dimensions whose elements you want to count. In other words, countables answers the questions such as:

* "How many visitors visited your homepage?" 
* "How many visits came from google.com?"

For this reason, countables are often used as the basic fundamental building block to create metrics.

The second major function of countables is that they form the backbone of your dataset schema structure. Your data schema and all other dimensions are organized to be grouped under and belong to a countable. In other words, if we consider dimensions as "categories", then countables are the way we organize these "categories" into groups.

When dimensions are grouped under a countable dimension, they are said to be at the "level" of the countable dimension. For example, the 'Email Address' can be at the Visitor level and "Browser" is at the Visit level. "Parent" and "child" refer to the relationship between the countable and the dimensions grouped below it. For example, Visitor is a "parent" of Email address. Conversely, Email address is a "child" of Visitor.

**2) Simple Dimensions**

The most common of all dimensions are Simple dimensions. Simple dimensions have a one-to-many relationship with a parent countable dimension and are commonly used in visualizations so you can view their elements. This means that a countable dimension can have one value for a simple dimension but the simple dimension can belong to one or more countables. For example, a customer has a name of 'John' - that customer can only have one first name, however, many other customers can have the name 'John;. As another example only one browser (e.g. Firefox) can be used for any particular visit to a web site but that browser can be used for many different visits.

If countable dimensions answer "How many?", then simple dimensions answer "Which ones?". Using the same example above used in the countable dimension section; Page Name is the simple dimension. Using the table and the simple dimension, Page Name, we can answer questions such as:

* "Which page had the most page views?" 
* "Of all the Shopping Cart pages, which one had the most visits?".

**3) Many-to-Many Dimensions**

Many-to-many dimensions have a many-to-many relationship with a parent countable dimension. For example, if a dimension named External Search Term is at the Visit level; a given External Search Term may be used in one or many Visits, and a given Visit may include one or many External Search Terms. Thus, External Search Term is a many-to-many dimension.

**4) Numeric Dimensions**

Numeric dimensions are a type of simple dimension that has a numeric value. Numeric dimensions are often created to be used in metrics. Examples of numeric dimensions include 'Revenue', 'Orders', and 'Units'. In the example above, the 'Customer Orders' is a numeric dimension. 
**5) Denormal Dimensions** Denormal dimensions are dimensions that have a one-to-one relationship with a parent countable dimension. Denormal dimensions are often used with dimensions that have high cardinality (many unique elements) like identification data. For example, a visitor can only have one User ID and a User ID can only belong to one visitor. Thus, this is a one-to-one relationship and can be a denormal dimension.

For example, Geometrixx Web User ID is a denormal dimension at the customer level. Since it is denormal, it has a one-to-one relationship with its parent dimension, meaning that each Web User ID has one customer and each customer only has one Web User ID. Thus, the 'Customers' metric can only be '1' for each element of Geometrixx Web User ID.

**6) Time Dimensions**

Time dimensions allow you to create a set of periodic or absolute local time dimensions based on the timestamp field that you specify. Examples of time dimensions include 'Day', 'Hour', 'Week', and 'Hour of Day'. In the example above, the 'Hour of Day' table shows how many visits and page views were received during the different hours of the days.

>[!NOTE]
>
>The % escapes used for display formatting is the same as the standard C library *strftime*.

## Defining Extended Dimensions {#section-38ee124ec74b43fb95f13194a9582b97}

Steps to define Extended Dimension:

1. While working in your dataset profile, open the Profile Manager and click Dataset to show its contents. 
1. Open the Transformation.cfg file or the Transformation Dataset Include file in which you want to define the extended dimension. 
1. Right -click Transformations and click Add new > `<Extended dimension type>`. 
1. Input the appropriate information for your extended dimension. For descriptions of the transformation types and information about their parameters, see the following sections:

    * [Countable Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html) 
    * [Simple Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html) 
    * [Many-to-Many Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html) 
    * [Numeric Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html) 
    * [Denormal Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html) 
    * [Time Dimensions](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. For any extended dimension that you define, you can add one or more comment lines to the Comments parameter to further describe the dimension or add notes about its use. To add a comment, right-click the *Comments* label and click* Add new > Comment Line*. 

1. After you have defined your extended dimension(s) in the configuration file, save the file locally and save it to your dataset profile on the DWB server.

## Hiding Extended Dimensions {#section-02339fb51658418eabc10186cd5957d7}

Extended Dimensions can be hidden so they do not show up on the Dimension Menu in the DWB. To hide the dimension, set the Hidden property to "True" in the dimension definition. 
