---
description: If clients can reach an Insight Server through multiple networks (for example, through the corporate intranet and through the Internet), the address file must define a separate network location for each of the server's IP addresses.
solution: Insight
title: Multiple IP Addresses for an Insight Server
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
---

# Multiple IP Addresses for an Insight Server{#multiple-ip-addresses-for-an-insight-server}

If clients can reach an Insight Server through multiple networks (for example, through the corporate intranet and through the Internet), the address file must define a separate network location for each of the server's IP addresses.

 For example, if server [!DNL VS01.myCompany.com] has an IP address of 10.2.1.70 on an internal network, and an IP address of 65.196.125.167 on the Internet, the address file would include a network location for each of the addresses as illustrated in the example below:

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

When users connect to an [!DNL Insight Server], they use the NetworkLocation parameter (in the client user interface) to specify the network location through which they want the server’s common name resolved. For example, given an address file with the two NetworkLocations shown above, a user would set the NetworkLocation parameter to “MyCorporate Intranet” to connect to [!DNL Insight Server] through the internal network and to “Internet” to connect to the server through the Internet. 
