---
description: Sensor, when used on a server, can collect fields of event data from any valid HTTP request or response header or variable available to it through the server’s API.
solution: Analytics
title: Extensible Fields
uuid: 91b9857e-44a4-497f-b157-51afd30306fe
---

# Extensible Fields{#extensible-fields}

Sensor, when used on a server, can collect fields of event data from any valid HTTP request or response header or variable available to it through the server’s API.

To collect such fields of data, you must specify the desired header fields or variables in the [!DNL txlogd.conf] configuration file for [!DNL Sensor].

* [Request Headers](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f) 
* [Server Variables](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-74b258bc3e8a4a93a0ee9fb01c067e4b)

## Request Headers {#section-22766692b45546d8bfc93dbe3bc9368f}

Following is the syntax for specifying a request header field to be collected (for example, Host, Accept-Encoding, Keep-Alive, and so on) in [!DNL txlogd.conf]: 

```
LogHeader RequestHeaderName
```

The collected data is recorded by [!DNL Sensor] to a field named “cs(RequestHeaderName)” in the [!DNL .vsl] files created by the [!DNL data workbench server]. For example, to collect the specific request header value from the request header “Host,” you would type “LogHeader Host” in [!DNL txlogd.conf]. The data is recorded to the field “cs(Host)” in the event data record.

## Server Variables {#section-74b258bc3e8a4a93a0ee9fb01c067e4b}

[!DNL Sensor] can collect fields of data from response headers or API-accessible server variables using SpecialLogField entries that you include in the [!DNL txlogd.conf] file. You can also use “SpecialLogField” entries in addition to or instead of “LogHeader” entries to collect request headers. See [Request Headers](../../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-ex-flds.md#section-22766692b45546d8bfc93dbe3bc9368f). The request headers option remains available for backward compatibility.

Following is the syntax for specifying a “SpecialLogField” in [!DNL txlogd.conf]: 

```
SpecialLogField cs(log field) = serverVariable stage
```

The following table includes descriptions of the components of a “SpecialLogField” entry.

<table id="table_053D5F34D56E4B15A85CA3B4FAD6E1B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Component </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(log field) </td> 
   <td colname="col2"> The name of the field to which the collected data is recorded in the event data record and the <span class="filepath"> .vsl </span> files created by the <span class="keyword"> data workbench server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> serverVariable </td> 
   <td colname="col2"> <p>Any server variable that is available to <span class="wintitle"> Sensor </span> through the server’s API </p> <p>Example: response.p3p </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stage </td> 
   <td colname="col2"> <p>Either vys_log or vys_cookie </p> <p>Specifying the stage requires that you know which server variables are available for vys_log and vys_cookie. </p> <p>Example: For the serverVariable response.p3p, you would enter vys_log. </p> </td> 
  </tr> 
 </tbody> 
</table>

For help configuring [!DNL Sensor] to collect extensible event data record fields, contact Adobe Consulting Services. 
