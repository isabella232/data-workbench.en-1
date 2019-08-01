---
description: The Traffic profile contains the following dimensions to help identify visitor actions.
seo-description: The Traffic profile contains the following dimensions to help identify visitor actions.
seo-title: Traffic Profile Dimensions
solution: Analytics
title: Traffic Profile Dimensions
topic: Data workbench
uuid: f427b9f4-302d-4d07-a68f-85867ec441ab
index: y
internal: n
snippet: y
---

# Traffic Profile Dimensions{#traffic-profile-dimensions}

The Traffic profile contains the following dimensions to help identify visitor actions.

The dimensions in the following table are defined in the transformation dataset include files in the Traffic\Dataset\Transformation directory.

|  Name  | Type  | Level  | Description  |
|---|---|---|---|
|  Day  | Simple  | Session  | The day of the first log entry of the session.  |
|  Day of Week  | Simple  | Session  | The day of week of the first log entry of a session.  |
|  Exact Page Duration (Hidden)  | Numeric  | Page View  | The duration in milliseconds of page view as measured by subtracting the time of the next page view from the time of that page view. The exact duration of the last page view in a session is always 0.  |
|  Hour  | Simple  | Session  | The hour of the first log entry of a session.  |
|  Hour of Day  | Simple  | Session  | The hour of day of the first log entry of a session.  |
|  Month  | Simple  | Session  | The month of the first log entry of a session.  |
|  Page View  | Countable  | Session  | A log entry or “Event Data Record” satisfying the Page View Condition.  |
|  Referrer  | Simple  | Session  | The second level domain of the referrer of the first log entry of the session (or None if it is an internal referrer domain).  |
|  Session  | Countable  | Visitor  |A period of related contiguous activity by a Visitor. It is delimited by a 30-minute period of inactivity and an external referrer domain or a maximum 48-hour Session Duration. Both of those timeouts and the set of domains that are considered internal can be configured in the [!DNL Transformation.cfg] file.  |
|  URI  | Simple  | Page View  | The URI stem of a page view. The URI dimension can be redefined using the ReplaceURI, PrependURI, and AppendURI transformations.  |
|  Visitor  | Countable  | N/A  | A unique value of x-trackingid. Usually corresponds to a unique browser if persistent cookies are used. The x-trackingid can be otherwise based on IP number or some other unique identifier such as x.509 common name.  |
|  Week  | Simple  | Session  | The week of the first log entry of a session.  |

The dimensions in the following table are defined in the Dimension directory of the Traffic profile: 

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col03" class="entry"> Level </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Browser </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> The type of user agent used by the visitor, including the version number (for example, MSIE 6.0.) </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Browser Type </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> The type of user agent used by the visitor (for example, MSIE). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Search Engine </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>FIRST ROW </p></td> 
   <td colname="col3"> The first search engine in a visitor’s session when a visitor has searched from a named search engine. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Next URI </td> 
   <td colname="col2"> Derived (ShiftDim based on URI dimension) </td> 
   <td colname="col03"> Page View </td> 
   <td colname="col3"> The URI of the next URI after the currently selected URI. This derived dimension is used to conduct analysis about what visitors do next after any given URI. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Onetime vs Repeat </td> 
   <td colname="col2"> Derived (SegmentDim based on Repeat Visitors and One-time Visitors metrics) </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> The type of visitor: one-time or repeat. One-time visitors have had only one session on the site, while repeat visitors have had more than one session. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Page </td> 
   <td colname="col2"> Derived (RenameDim based on URI dimension) </td> 
   <td colname="col03"> Page View </td> 
   <td colname="col3"> The name of each page visited during a session. Initially, each page’s name is the same as the URI but can be changed for easier interpretation. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Referrer </td> 
   <td colname="col2"> Inherited from the built-in Referrer dimension </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The second level domain name of the web site that first referred a session to the site (as supplied by the visitor’s browser.) </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Search Phrase </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03">Session <p>FIRST ROW </p></td> 
   <td colname="col3"> The first search phrase in a visitor’s session as passed on by a search engine when a visitor has searched from a named search engine. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Search Term </td> 
   <td colname="col2"> Many-to-Many </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Each search term as passed on by a search engine when a visitor has a search referrer click-through from a named search engine. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Session Duration </td> 
   <td colname="col2"> Derived (MetricDim based on Exact Page Duration metric) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The duration of a session in 30-second increments. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Session Number </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The number of times a visitor has visited the site. For example, first-time visitors have a Session Number of “1”, second-time visitors have a Session Number of “2”, etc. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Session Page Views </td> 
   <td colname="col2"> Derived (MetricDim based on Page Views metric) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The number of page views in a session. For example, selecting “3” in the Session Page Views dimension would select all sessions with exactly 3 page views. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Search Engine </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The second level domain name of the first web site that is a named search engine that referred a visitor to the site during a session (as supplied by the visitor’s browser.) </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Time Dimensions </td> 
   <td colname="col2"> Simple </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> The hour, day, hour of day, week, day of week, month, quarter or year in which a Session began. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Time Reporting Dimensions </td> 
   <td colname="col2"> Derived (LastN and Rename dimensions based on built-in time dimensions) </td> 
   <td colname="col03"> Session </td> 
   <td colname="col3"> Dimensions including Days Ago, Days of Last Month, Days of Last Week, Days of This Month, Days of This Week, Hours of Today, Hours of Yesterday, Last 12 Months, Last 2 Months, Last 2 Weeks, Last 24 Hours, Last 3 Months, Last 4 Weeks, Last 6 Months, Last 7 Days, Last 7 Days and Today, Last 8 Weeks, Last 9 Months, Last Month, Last Week, Months Ago, This Month, This Week, This and Last 14 Days, This and Last 6 Months, This and Last 8 Weeks, Today, Today Reporting, Today and Last 30 Days, Weeks Ago and Yesterday provide a convenient way to build a Workspace or Report which always shows a portion of data in the Dataset. Each is based upon when a session began. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> Inherited from the built-in Dimension URI </td> 
   <td colname="col03"> Page View </td> 
   <td colname="col3"> The URI of each page viewed. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Visitor Page Views </td> 
   <td colname="col2"> Derived (MetricDim based on Page Views metric) </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> The number of page views to date for a visitor. For example, selecting “3” in the Visitor Page Views dimension would select all visitors with exactly 3 page views across all of their sessions. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Visitor Referrer </td> 
   <td colname="col2"> Inherited from the built-in dimension Referrer </td> 
   <td colname="col03"> Visitor </td> 
   <td colname="col3"> The second level domain name of the web site that first referred a Visitor to the site for their first session (as supplied by the visitor’s browser). </td> 
  </tr> 
 </tbody> 
</table>

