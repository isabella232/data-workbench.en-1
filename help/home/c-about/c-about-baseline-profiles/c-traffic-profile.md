---
description: The Traffic profile contains the following metrics to identify visitor traffic.
seo-description: The Traffic profile contains the following metrics to identify visitor traffic.
seo-title: Traffic Profile Metrics
solution: Analytics
title: Traffic Profile Metrics
topic: Data workbench
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
index: y
internal: n
snippet: y
---

# Traffic Profile Metrics{#traffic-profile-metrics}

The Traffic profile contains the following metrics to identify visitor traffic.

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Metric Formula and Level </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Entries </td> 
   <td colname="col2">Formula: <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>Level: Page View </p></td> 
   <td colname="col3"> The number of sessions that entered the site on each page. This metric is evaluated over the Page dimension only. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Exit Rate </td> 
   <td colname="col2">Formula: <span class="filepath"> Exits/Page_Views </span><p>Level: Page View </p></td> 
   <td colname="col3"> The percentage of sessions that exited the site from each page. The Exit Rate metric can only be evaluated over the page dimension. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Exits </td> 
   <td colname="col2">Formula:<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>Level: Page View </p></td> 
   <td colname="col3"> The number of sessions that exited the site from each page. This metric is evaluated over the Page dimension only. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">Formula: <span class="filepath"> (raw(Visitors) - ((raw(Visitors) + .69)^0.5 * 1.281551 - 1.2269))*(Visitors/raw(Visitors))</span><p>Level: Visitor </p></td> 
   <td colname="col3"> A measure of the lowest number of possible visitors as reported by Insight. Mathematically, it specifies the lowest number of visitors with a 90% probability. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Page View Duration </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> sum (exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>Level: Page View </p> </td> 
   <td colname="col3"> The average length of time (MM:SS) spent on a particular page or group of pages. This metric is evaluated over the Page dimension only. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Page Views per Session </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Page_Views/ (Sessions by Page_View) </span></p> <p>Level: Session </p> </td> 
   <td colname="col3"> The average number of page views in each session that has page views. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Page Views </td> 
   <td colname="col2">Formula: <span class="filepath"> sum(One, Page_View)</span><p>Level: Page View </p></td> 
   <td colname="col3"> The number of page views. A page view is a request for a defined page (access to images and other types of filtered content are not counted). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Pct of Page Views </td> 
   <td colname="col2">Formula: <span class="filepath"> Page_Views/total(Page_Views) </span><p>Level: Page View </p></td> 
   <td colname="col3"> The percentage of page views. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Pct of Sessions </td> 
   <td colname="col2">Formula: <span class="filepath"> Sessions/total(Sessions)</span><p>Level: Session </p></td> 
   <td colname="col3"> The percentage of sessions. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Pct of Visitors </td> 
   <td colname="col2">Formula: <span class="filepath"> Visitors/total(Visitors) </span><p>Level: Visitor </p></td> 
   <td colname="col3"> The percentage of visitors. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Pct Referred Visitors </td> 
   <td colname="col2"> <p>Formula: Referred_Visitors/Visitors </p> <p>Level: Visitor </p> </td> 
   <td colname="col3"> The percentage of visitors that were referred to this site from another site. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Referred Sessions </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessions[Referrer&lt;&gt; 'None' and Referrer&lt;&gt;'bookmarks']</span></p> <p>Level: Session </p> </td> 
   <td colname="col3"> The number of sessions that were referred to this site from another site. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Referred Visitors </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitors[Visitor_ Referrer&lt;&gt;'None' and Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>Level: Visitor </p> </td> 
   <td colname="col3"> The number of visitors that were referred to this site from another site. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Retention </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessions[shift(None,Ses sion,Visitor,1) = ""] / Sessions</span></p> <p>Level: Session </p> </td> 
   <td colname="col3"> The percentage of sessions that are not the visitors last sessions. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Session Duration </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> (sum (Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>Level: Session </p> </td> 
   <td colname="col3">The average length of time (MM:SS) a visitor spends in a session. <p><p>Note: You can use this metric with the <a href="http://marketing.adobe.com/resources/help/en_US/insight/client/index.html#Segment_Export" format="http" scope="external"> Segment Export</a> feature. </p></p></td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Sessions by Page View </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Sessions by Page_View</span></p> <p> Level: Session </p> </td> 
   <td colname="col3"> The number of sessions that had a page view. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Sessions </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> sum(One, Session)</span></p> <p>Level: Session </p> </td> 
   <td colname="col3"> A count of visitor sessions. A session is a period of activity for one visitor of a web site. Individual sessions for each visitor are identified using cookies, timeouts, and other heuristics. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> confidence(Sessions) * 1.281551 / Sessions</span></p> <p>Level: Visitor </p> </td> 
   <td colname="col3"> A measure of confidence of the Sessions metric as reported by data workbench. Mathematically, it is a +/- percentage specifying the range within which the actual answer will lie 80% of the time. As a rule-of-thumb, doubling the SCI80 percentage will give a range within which the actual answer will lie 99% of the time. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> (((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) + raw(Visitors))*( Visitors/raw(Visitors))</span></p> <p>Level: Visitor </p> </td> 
   <td colname="col3"> A measure of the highest number of possible visitors as reported by Insight. Mathematically, it specifies the highest number of visitors with a 90% probability. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">Formula: <span class="filepath"> ((raw(Visitors) + .68)^0.5 * 1.281551 + 1.2269) / raw(Visitors)</span><p>Level: Visitor </p></td> 
   <td colname="col3"> A measure of confidence of the Visitors metric as reported by Insight. Mathematically, it is a +/- percentage specifying the range within which the actual answer will lie 80% of the time. As a rule-of-thumb, doubling the VCI80 percentage will give a range within which the actual answer will lie 99% of the time. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Visitors by Page View </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitors by Page_View</span></p> <p>Level: Page View </p> </td> 
   <td colname="col3"> The number of visitors that had a page view. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Visitors by Session </td> 
   <td colname="col2"> <p>Formula: <span class="filepath"> Visitors by Session </span></p> <p>Level: Session </p> </td> 
   <td colname="col3"> The number of visitors that had a session. </td> 
  </tr> 
 </tbody> 
</table>

