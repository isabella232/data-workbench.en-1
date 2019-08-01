---
description: Marketing your website may involve the placement of advertisements in the form of image or other rich media files (served from your web server) on third-party websites.
seo-description: Marketing your website may involve the placement of advertisements in the form of image or other rich media files (served from your web server) on third-party websites.
seo-title: Measuring Advertisement Impression
solution: Analytics
title: Measuring Advertisement Impression
topic: Data workbench
uuid: a7dabf80-1e30-440e-9444-e54ac72785b1
index: y
internal: n
snippet: y
---

# Measuring Advertisement Impression{#measuring-advertisement-impression}

Marketing your website may involve the placement of advertisements in the form of image or other rich media files (served from your web server) on third-party websites.

 In such cases, you might want to measure both the impression of the advertisement on a browser and the subsequent click-through, if one occurs, to the advertisement’s target URL on your website.

For advertisements in the form of images, appending [!DNL Log=1] to the query string results in the image request, and thus the advertisement impression, being captured by [!DNL Sensor] for analysis purposes.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->

```

|  Data Collected  | Explanation  | Example  |
|---|---|---|
|  v_ic=  | Value denoting the Impression Campaign  | v_ic=”CAMPAIGN1”  |
|  v_ica=  | Value denoting the Impression Campaign Asset  | v_ica=”72890ab”  |
|  v_icr=  | Value denoting the Impression Campaign Referrer  | v_icr=”http://money.cnn.com/markets/  |

In addition to appending [!DNL Log=1] to the image request, an identifier should be added to the URL leading from the advertisement to the target page within your website to track the advertisement that led to the click-through and to track the click-through back to the particular campaign for that advertisement.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> Data Collected </th> 
   <th colname="col2" class="entry"> Explanation </th> 
   <th colname="col3" class="entry"> Example </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Value denoting the Click-through Campaign </td> 
   <td colname="col3"> v_c=”CAMPAIGN1” </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Value denoting the Click-through Campaign Asset </td> 
   <td colname="col3"> v_ca=”72890ab” </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Value denoting the Click-through Campaign Referrer </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr=”http://money.cnn.com/</span> </p> <p>markets/ </p> </td> 
  </tr> 
 </tbody> 
</table>

