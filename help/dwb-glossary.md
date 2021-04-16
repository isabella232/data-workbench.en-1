---
description: Data Workbench Glossary
title: Data Workbench Glossary
uuid: 1000c43d-383c-442d-bd09-de4f286ded31
exl-id: 29d6560a-0394-4031-8152-20f7ea0de00b
---
# Data Workbench Glossary{#data-workbench-glossary}

**Alert**

In data workbench, a message or report that is automatically triggered when a metric reaches a defined threshold within a specified time frame. For example, one might create an alert that issues an e-mail if the number of page views during a 24-hour period falls above or below a specified quantity.

**Analyst**

An individual who performs analysis, defines reports, or otherwise uses data workbench.

**Architect**

An individual who determines how data will be captured, processed, and organized for analysis and reporting. This individual generally has significant expertise in configuring the Adobe® Platform for use by analysts.

**Bar graph**

A form of graph that uses rectangular bars of various sizes to show comparisons among two or more items.

**Benchmark**

A measurement or standard that serves as a point of reference by which others may be measured or judged. In data workbench, a benchmark illustrates the comparison between the value associated with a selection (a selected subset) and the value that would be shown if the selection were not made.

**Cardinality**

The number of elements in a set. The number of elements in an Adobe data dimension is referred to as the dimension’s cardinality.

**Checkpoint**

The time at which a copy of an Adobe dataset was written for backup or recovery purposes. The term also refers to the set of data that is written during a checkpoint operation.

**Chi-square**

A statistical test to determine the probability that an observed deviation from the expected event or outcome occurred by chance. In data workbench, the closer Chi square is to 100%, the smaller the likelihood that the deviation occurred solely by chance.

**Clickstream**

An informal term that refers to the sequence of pages that a user requests while browsing a Web site. Clickstream information can help site owners understand how visitors use their site and which pages they request most frequently. Site owners can capture the clickstreams of visitors to their sites, but cannot capture clickstreams outside their site (except by using third-party cookies or page tags) because those requests are logged by outside Web servers.

**Color Legend**

A legend in data workbench that displays the color ramp for a selected metric. Color legends enable the colorcoding of visualizations by various metrics. Color-coding visualizations makes it easier to spot anomalies, exceptions, and trends.

**Color Ramp**

In a color legend, the range of colors used to represent the range of possible values for a metric. When a color legend is applied to a visualization, graphical elements in the visualization (for example, bars in a bar graph) are color-coded according to the values represented by the color ramp.

**Common Key**

A common variable that forms a relationship between the rows in two tabular sets of data. For example, a product ID might act as the common key between a table of query-string variables and a table of product data from an inventory-management system.

**Confidence Interval**

A range of values that has a specified probability of containing the rate or trend. The 80% (p-value = .20), 95% (p-value = .05) and 99% (p-value = .01) confidence intervals are the most commonly used intervals. (Source: `http://www.nci.nih.gov/statistics/glossary`)

**Confidence Level**

The likelihood that the sampling error in a survey result will fall within a specified range, usually expressed in terms of standard errors (for example, 1 standard error equals 68% likelihood, 2 standard errors equals 95.4% likelihood). (Source: `http://www.magazine.org/research/3410.cfm`)

**Conversion Map**

In data workbench, a type of visualization in which elements are plotted on the x-axis according to the value of the Conversion metric.

**Conversion Rate**

In data workbench, the percentage of sessions during which a value event occurred. Conversion rate is calculated by dividing the number of sessions in which a value event occurred by the total number of sessions.

**Correlation**

A numeric measure of the strength of a linear relationship between two random variables. Variables that tend to move up or down together are positively correlated, while variables that tend to move in opposite directions are negatively correlated. See also Correlation Coefficient.

**Correlation Coefficient**

The numeric value that signifies the strength of a linear relationship between two random variables. See also Correlation.

**Countable Dimension**

A dimension in which the number of elements the dimension contains can be discretely counted. Countable dimensions can have child dimensions of the following types: Countable, Numeric, Simple, Many-to-Many, and Denormal.

**CrossRows Transformation**

In data workbench server, a data transformation that enables data from multiple event records for a Visitor (made at different times) to be incorporated in a calculation.

**Crosstab**

In data workbench, a tabular visualization that displays the metrics associated with the intersections of two dimensions.

**Cube**

A multi-dimensional data structure or a group of data cells arranged by the dimensions of the data. For example, a spreadsheet exemplifies a two-dimensional array with data arranged in rows and columns. In a spreadsheet, each row or column is a dimension. A three-dimensional array can be visualized as a cube with each dimension forming a side of the cube, including any slice parallel with that side. Higher dimensional arrays have no physical metaphor, but they can be used to organize data in ways that users think about their enterprise. Also known as a hypercube, multi-dimensional array, or multi-dimensional database.

**Dashboard**

A workspace that is created for viewing rather than interaction. Dashboards provide “at-a-glance” status through the display of key performance indicators that are appropriate for a particular manager or operator who is overseeing one or more business objectives. See also Workspace.

**Data Mining**

The unguided or interactive application of a collection of mathematical procedures to historical business data in an effort to find insights in the form of correlations and other statistical relationships.

**Data Subset**

A feature that enables users to easily select a subset of a dataset for use in online or offline analysis. (A data subset is a portion of the dataset based on a filter.)

**Data Warehouse**

A database designed to support decision making in organizations. A data warehouse generally contains large amounts of subject-oriented, time-variant, nonvolatile data that is structured for rapid, online queries and managerial summaries.

**Data Processing Unit**

A type of data workbench server that processes, stores, and serves data from an Adobe dataset. A DPU can optionally store the VSL log files that contain the source data from which the dataset is constructed or can receive that data from an data workbench server File Server Unit (FSU). A DPU is the type of data workbench server with which data workbench and Report® clients interact directly.

**Dataset**

The data loaded and processed by data workbench server. The dataset represents the data that can be transmitted to data workbench or Report for analysis, reporting, and alerting purposes. Physically, the dataset resides in the temp.db file. Each data workbench server computer (or data workbench server cluster) maintains one dataset.

**Dataset Data**

The data created and stored in an data workbench server dataset. It includes the event data and integration data that is admitted to or created in the dataset. It also includes any information derived from such data as determined by the configuration files that define that dataset. Dataset data can be re-created by reprocessing the event and integration data using the same or different configuration files. (Configuration files are system files that are managed as a part of an Adobe profile.)

**Dataset Records**

Those event data records admitted to an Adobe dataset after all filtering and other processing has been performed. Also called processed log entries.

**Dataset Schema**

A visualization in data workbench that displays the schema of the dataset that backs the currently selected profile.

**Dataset Storage Space**

The amount of data (in bytes) entered or created in an Adobe dataset. This data is stored by the dataset in a file called Temp.db on an data workbench server computer. The data in Temp.db is transient and can be recreated by reprocessing the source data (i.e., event data and integration data) with the appropriate configuration files.

**Decoder**

The component in data workbench server that reads event data from various sources and generates data that is used to produce the dataset. Output from a decoder can be used as input to any of the “log processing” capabilities in data workbench server. Decoder types include the Sensor decoder (for loading data from various versions of Sensor), the Regular Expression decoder (for loading data from delimited flat files), and the ODBC decoder (for loading data from ODBC data sources).

**Dimension**

A set of elements, all of which are of a similar type in the user’s perception. The elements define a set of categories into which data can be grouped. For instance, the elements Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, and Sunday make up a “Weekday” dimension.

**Dimension Element**

An individual category within a dimension. For example, a “Weekday” dimension would contain the individual elements Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, and Sunday.

**Dimension Legend**

In data workbench, the legend that lists the dimensions that have been defined in (or derived from) the dataset. When a selection is made in a visualization, the Dimension legend identifies those dimensions whose values differ from the benchmark by a statistically significant amount.

**Drill Up-Down**

A specific analytical technique whereby the user navigates among levels of data ranging from the most summarized (up) to the most detailed (down). For example, when viewing sales data for North America, a drill-down operation in the Region dimension might display Canada, the United States, and Mexico. A further drill- down on Canada might display Toronto, Vancouver, Montreal, and so forth.

**Event Data**

The data collected by Sensors or other means (for example, a web server log file), which constitutes the primary input to data workbench server. Each event data record represents a transaction record or a single instance of an event.

**Extended Dimension**

A dimension that is based on extended data. Extended data is any data beyond what is minimally required to form a valid event data record. Extended data can be added to an event data record when the original event is captured or it can be incorporated from other sources and added to the event data record as integration data. Any dimension that is based on this additional data is considered to be “extended.”

**File Server Unit (FSU)**

A type of data workbench server whose function is solely to receive event data from one or more Sensors or repeater servers and provide data to one or more data workbench server Data Processing Units (DPUs) for their use in constructing Adobe datasets. FSUs optimize the transfer of event data to the DPUs and are significantly faster than ordinary file servers. The use of an FSU reduces hardware costs by enabling log data to be stored on lower cost storage hardware and reduces administrative complexity by allowing multiple Sensors to point to a single data workbench server.

**Incremental Query Evaluation**

The patented process by which data workbench server provides immediate query results to a user based on a projected random sample of the full population. Under this process, the server incrementally refines the accuracy of the query by considering more data until all data has been considered and an exact count has been obtained.

**Integration Data**

Integration data is external data from corporate databases or look-up files that you can combine with event data to create the dataset. In general, you use integration data to augment the event data acquired by Sensor. (Conceptually, you can think of using integration data to populate event data records with additional columns of information.)

**Legend**

A window in data workbench that provides explanatory details about the visualizations displayed in the workspace. Types of legends include Color legends, Dimension legends, and Metric legends. Like any window in data workbench, Legend windows can be generated and distributed by Report.

**Line Graph**

A type of visualization in data workbench that plots metrics for a specified dimension as successive points on the x-axis of a graph and then connects the points with lines. A line graph is a particularly effective way to visualize a metric over a time-based dimension.

**Log Entry Condition**

A condition that determines whether an event data record (a log entry) will be included in the dataset. For example, a log entry condition might specify that only event data records associated with a particular Web site are to be admitted to the dataset. Log entry conditions are specified in the log processing configuration file on the data workbench server.

**Many-to-Many Dimension**

In the Adobe Platform, a dimension that has a many-to-many relationship with a parent Countable dimension. A many-to-many dimension represents a set of values for each element of its parent dimension. For example, in Site, the Search Phrase dimension has a many-to-many relationship to its parent, the Session dimension (that is, a Session can have any number of Search Phrases, and a Search Phrase can have any number of Sessions.)

**Masking**

A feature in data workbench that enables analysts to temporarily hide elements that they do not want to include in an analysis.

**Mean**

The arithmetic average of a set of numbers. The sum of the data divided by the sample size.

**Median**

A number that separates the highest half of a sample, a population, or a probability distribution from the lowest half. Half of the population will have values less than or equal to the median, and half of the population will have values equal to or greater than the median.

**Metric**

In Adobe, a named formula that describes how to calculate a quantitative value from the data in the dataset. In Site, for example, the “Sessions per Visitor” metric represents a formula that divides the count of Sessions by the count of Visitors.

**Metric Legend**

A window in data workbench that displays the metrics defined by the active profile. A Metric legend displays the value of each metric as calculated from the dataset or the current selection (if a selection is active in the workspace, the Metric legend displays the values for the selected subset instead of the entire dataset.) Like any window in data workbench, Metric legends can be generated and distributed by Report.

**Metric Worksheet**

A window in data workbench that enables analysts to define their own metrics for a dataset. A Metric worksheet is similar to a spreadsheet. Using data workbench formula syntax, analysts can enter expressions describing the quantitative values that they want to derive from the dataset. For example, an analyst might define a metric that displays the percentage of Visitors who viewed a page from a particular domain. Like regular metrics, formulas in a Metric worksheet operate on the selected subset when a selection is active in the workspace. Like any window in data workbench, Metric worksheets can be generated and distributed by Report.

**New Visitor Condition**

The condition that determines whether a new tracking ID is created when data workbench server is presented with an event data record.

**Node**

A grouping of one or more discrete items into a single logical entity. In a configuration file (.cfg), a node is an item containing related parameters. See also Parameter and Vector. In data workbench, a node on a Process Map represents a single page or defined group of pages.

**Numeric Dimension**

In the Adobe Platform, a dimension that has ordered, numerical values and has a one-to-many relationship with a parent Countable dimension. Generally, a Numeric dimension represents a numeric property of the elements of the parent dimension. Numeric dimensions are often used to define “sum” metrics.

**One-to-Many Relationship**

A relationship between two data dimensions in which a single element in one dimension is (or can be) related to one or more elements in the other dimension.

**Ordinal**

Being or denoting a numerical order in a series. (Source: `http://wordnet.princeton.edu/perl/webwn?s=ordinal`) If a dimension is sorted ordinally in data workbench, the elements of the dimension are displayed in the order in which they are represented internally.

**Outliers**

In a set of data, a value so far removed from other values in the distribution that its presence cannot be attributed to the random combination of chance causes.

**Page Overlay**

A type of visualization in data workbench that color-codes the links on an image of a Web page according to a specified metric. You can use a Page Overly visualization to quickly identify which links on a page attract visitors attention (and take them to other pages on your site) and which do not. You can also use it understand the “value” (as measured by value events) that the various links on a page generate for your site.

**Page View Condition**

An option in an data workbench server transformation that enables event records to be included or excluded as page views based on their content type or actual content. You might use this option, for example, to exclude event records pertaining to unsuccessful HTTP requests (for example, ones that produced a 404 status code) or requests that return certain content types (for example, image requests). If an HTTP event record is not filtered out by the Page View Condition option, that event record will represent a page view in the dataset.

**Path Browser Visualization**

A type of visualization in data workbench that enables an analyst to interactively explore a sequences of events (such as Page Views) in a Visitor Session or across Visitor Sessions.

**Primary Server**

In a data workbench server cluster, the data workbench server that brokers communications between clients (such as data workbench and Report) and the other servers in the cluster. The primary server also functions as the administrative focal point for the cluster. Using the data workbench server’s profile synchronization capabilities, changes that an administrator makes to the primary server are automatically propagated to the other servers in the cluster. A primary server is an data workbench server DPU.

**Process Map**

A type of visualization in data workbench that enables an analyst to understand the flow of traffic among pages or nodes on a Web site. A process map depicts information about specific pages (such as the number of sessions during which the pages were viewed) and also illustrates traffic volume between pages or nodes.

**Processing Server**

In a data workbench server cluster, the data workbench servers that are controlled by the configuration information on the primary server. A processing server processes event data into a dataset and responds to queries from clients such as data workbench and Report. When responding to a query, a processing server divides (“partitions”) responsibility for fulfilling the query among the servers in the cluster. When the other servers complete there portions of the query, the processing server combines (“departitions”) their results and returns the combined result to the client.

**Profile**

A set of configuration files that contains the rules for creating a dataset for a specific analysis purpose. A profile also defines articles such as metrics, derivative dimensions, workspaces, reports, visualizations, and legends that enable analysts to interact with the dataset and obtain information from it. A profile can be structured generally for a Web site (as in a profile for www.mysite.com) or it can be tailored for a particular type of user (such as the “Marketing” user profile or the “Finance” user profile).

**Profile Manager**

An interactive administrative tool in data workbench that enables an administrator or other user to manage the configuration files associated with a profile.

**Regular Expression**

A formula that describes or matches a set of strings according to certain syntax rules. Regular expressions (often abbreviated as regexp, regex, or regxp) are used to search and manipulate bodies of text based on certain patterns. Regular expression notation originated in early Unix editors and gained widespread use in other Unix utilities such as vi and Perl. Today, regular expressions are supported by many text editors, scripting languages, and other text-manipulation tools. Data workbench server includes a regular expression engine.

**Retention Map**

A type of visualization in data workbench that plots elements on the x-axis according to the value of the Retention metric.

**Scatter Plot**

A type of visualization in data workbench that represents bi-variate data as points on a graph. A scatter plot has two pieces of data for each element being graphed. For example, a scatter plot of the Conversion Rate and Visitors metrics for a set of 10 pages would result in 10 separate points in the plot.

**Selection**

A feature in data workbench that enables an analyst to restrict the set of data retrieved and displayed for reporting or analysis. A selection can be made interactively within data workbench by clicking elements displayed in one or more dimensions (left-click selects an element, right-click deselects an element). Selections can also be made by defining filters that select certain elements in specified dimensions.

**Simple Dimension**

In the Adobe Platform, a dimension that has a one-to-many relationship with a parent countable dimension. For example, Visitor Referrer is a simple dimension whose parent is the countable dimension, Visitor. A Visitor has only one Visitor Referrer. However, a Visitor Referrer can have multiple Visitors (that is, one Visitor Referrer can be related to many Visitors).

**Smoothing**

A mathematical inference of a curve across multiple points in a line graph, which is used to illustrate a more meaningful trend line across relatively sparse data points.

**Source**

On data workbench server, a resource containing event data that can be used to create a dataset. Adobe decoders look to sources for event data to decode for use by data workbench server.

**Source Data**

On data workbench server, data that is the input to one of its decoders. Source data can be input to the Sensor decoder (which loads source data from various versions of Sensor), the Regular Expression decoder (which loads source data from delimited flat files), and the ODBC Decoder (which loads source data from ODBC data sources).

**Table Graph**

A type of visualization in data workbench that displays data in tabular format. The metric values in a table graph can be expressed numerically or represented in bar format.

**Time Series**

A graph that shows how a given property or value changes over time.

**Tracking ID**

An identifier that uniquely distinguishes the primary entities being analyzed in an Adobe dataset. A tracking ID can be constructed from various sources including a unique ID from a Web client cookie, an IP number and user-agent hash, or an x.509 name. Although these are some common sources for a tracking ID, any value that is capable of uniquely identifying the entities populating the Visitor dimension in the dataset can be used.

**Transformation**

A method of changing the value of a variable using some mathematical operation. On the data workbench server, for example, analysts can use the split transformation to break the name-value pairs in a query string into individual variables.

**Two-Dimensional Bar Graph**

A type of visualization in data workbench that simultaneously displays two dimensions and up to two metrics in a three-dimensional graphical view.

**Value Legend**

A window in data workbench that enables an analyst to associate a monetary value with a selected event and view the results when that monetary value is summed for all instances of the selected event in the dataset.

**Visitor**

The dimension in the dataset that identifies the entity that generated the event. Each member of the Visitor dimension is identified by a unique tracking ID. In Site, for example, the tracking ID is typically derived from a unique ID within the client’s cookie. In Call, the tracking ID might be the caller’s a telephone number.

**Visitor Referrer**

The first HTTP referrer for a Visitor within the time span of an Adobe dataset.

**Visitor Splitting**

A feature in data workbench server that allows visitors with large amounts of event data to be split between two tracking IDs. Visitor splitting is used to prevent event data from being filtered from the dataset when a visitor exceeds the maximum configured number of events per visitor (a parameter that is set to ensure correct system performance). Although visitor splitting artificially increases the number of visitors in the dataset, it does not inflate the total number of event records, which ensures that the total number of countable events (for example, page views, bookings) remains accurate.

**VSL**

Log file. The type of file in which data workbench server store event data that they receive from Sensor. VSL files are compressed, but can be output in uncompressed form using data transformation functionality. VSL is the file extension for a log file.

**What-If Analysis**

A type of analysis used to understand the consequences of changing certain variables in a data model by observing the effect that changes to those variables have on other data in the model.

**Workspace**

In data workbench, a workspace is a container for a particular analysis and visualization task. A workspace can contain multiple visualizations), all of which operate against a common set of data (that is, all visualizations in the workspace render the same set of query results). When an analyst performs a subsetting or filtering operation in one visualization, the selected subset is reflected throughout the entire workspace.

**Worktop**

The “home” area within the data workbench user interface that enables you to organize and access all of your workspaces and reports. It also enables you to create and save new and updated workspaces and reports to the data workbench server so that others using the same profile can access them as well.
