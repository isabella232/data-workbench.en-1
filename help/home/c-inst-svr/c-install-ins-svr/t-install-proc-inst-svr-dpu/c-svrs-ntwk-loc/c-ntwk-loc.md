---
description: Conceptually, the address file serves the same purpose as the ETC&bsol;HOSTS file on a networked machine.
solution: Analytics
title: Network Locations
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
---
# Network Locations{#network-locations}

Conceptually, the address file serves the same purpose as the ETC&bsol;HOSTS file on a networked machine.

However, unlike the HOSTS file, which describes a single collection of names, the address file contains multiple collections of names called network locations.

A network location is a named collection of address definitions. Each address definition in the collection associates a common name with an IP address.

In the address file, a network location is defined in a structure called a NetworkLocation. The NetworkLocation in the following example defines a network location called “MyCorporate Intranet.” It contains an address definition that maps the common name [!DNL VS01.myCompany.com] to the IP address “10.2.1.70.”

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

As shown in the example above, the NetworkLocation structure consists of three main parameters:

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Addresses </td> 
   <td colname="col2"> Defines zero or more AddressDefinitions. Each AddressDefintion associates a common name with an IP address. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Assigns a name to the NetworkLocation. The name assigned to a NetworkLocation must be unique within the address file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parent </td> 
   <td colname="col2"> <p>Specifies the name of another NetworkLocation whose members are included in this NetworkLocation. This parameter enables one NetworkLocation to extend another. </p> <p>You can set the Parent parameter to “DNS,” to extend a NetworkLocation to the client’s normal DNS system. </p> <p>Example: Parent = string: DNS </p> <p>When DNS is the parent, clients attempt to resolve a common name using the client machine’s DNS system when they cannot resolve the name through the NetworkLocation. </p> </td> 
  </tr> 
 </tbody> 
</table>
