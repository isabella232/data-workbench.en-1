---
description: The address file installed on Insight Server contains four pre-defined network locations.
title: The Address File Installed on Insight Server
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
---
# The Address File Installed on Insight Server{#the-address-file-installed-on-insight-server}

The address file installed on Insight Server contains four pre-defined network locations.

The procedure in the next section describes how to configure this file.

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0 is an empty, unnamed network location that you edit to associate the common name of your [!DNL Insight Server] to its IP address. If the server has multiple IP addresses, you create additional NetworkLocations. 
* NetworkLocation 1 is the [!DNL Insight] network location. If you do not explicitly set the NetworkLocation parameter, [!DNL Insight] resolves common names through this network location. 

* NetworkLocation 2 is the [!DNL Insight Server] network location. When [!DNL Insight Servers] operate in a cluster, they use this network location to resolve common names for inter-server communication. 

* NetworkLocation 3 is the [!DNL Report] Server network location. If you do not explicitly set the NetworkLocation parameter, [!DNL Report] resolves common names through this network location.

## To Configure the Address File {#section-10caab9854a244e39b09071946f7bd27}

The following procedure describes how to configure the address file to define a network location (or network locations) for your [!DNL Insight Server].

1. Navigate to the [!DNL Addresses] folder in the directory where you installed [!DNL Insight Server] (for example, [!DNL C:\Adobe\Server\Addresses)]. 

1. Locate the [!DNL server.address] file and rename this file to reflect the server’s common name. For example, if the common name were [!DNL server.mycompany.com], you would rename the file [!DNL server.mycompany.com.address]. 

1. Open the renamed file in a text editor such as Notepad. 
1. Edit NetworkLocation 0 to specify the common name and IP address of the [!DNL Insight Server] as shown below. If your server has multiple IP addresses, use NetworkLocation 0 to specify the server’s IP address on the local, non-routable network (for example, its location on the internal network). 

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> For this value... </th> 
   <th colname="col2" class="entry"> Specify </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP Address</i> </td> 
   <td colname="col2"> <p>The numeric IP address of the <span class="keyword"> Insight Server </span> machine. </p> <p>Example: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Common Name </i> </td> 
   <td colname="col2"> <p>The common name assigned to the digital certificate for <span class="keyword"> Insight Server </span>. </p> <p>Example: <span class="filepath"> server.mycompany.com </span></p> <p>Note: Be sure to type this name exactly as it appears on the certificate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>Network Location Name </i> </td> 
   <td colname="col2"> <p>The name you want to assign to the collection of common names and IP addresses that this NetworkLocation represents. The name must be unique within the address file. </p> <p>Example: Corporate Intranet </p> </td> 
  </tr> 
 </tbody> 
</table>

1. If your [!DNL Insight Server] has additional IP addresses, create an additional NetworkLocation for each address. (An easy way to do this is to make a copy of the NetworkLocation you created above and update the IP address in the copy.)

   You can add the new NetworkLocation to the end of the address file or insert it between existing NetworkLocation definitions. (The position of a NetworkLocation within the address file is not significant; however, the [!DNL Insight], [!DNL Insight Server], and [!DNL Report] Server NetworkLocations are typically placed at the end of the file.)

   After you have added the necessary NetworkLocations, do the following to renumber the items in the file:

    1. Update the item count for the Locations structure to match the total number of NetworkLocation definitions in the file. For example, if your file contains four NetworkLocation definitions, the Locations line would look as follows:

       ```    
       Locations = vector: 4 items
       ```

    1. Update the NetworkLocation item numbers so that NetworkLocations are numbered consecutively (starting from 0).

   For an example of an address file that defines an [!DNL Insight Server] with two IP addresses, see the example in this section. 

1. In the [!DNL Insight] and [!DNL Report] Server network locations, edit the Parent parameter as shown below to specify the name of the NetworkLocation that [!DNL Insight] and [!DNL Report] use as their default network locations. (For an example of what the Parent parameter looks like when it is configured, see the example in this section.) 

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
    
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   If your [!DNL Insight Server] has a single IP address and, therefore, has only one NetworkLocation, point the Parent parameter to that NetworkLocation. If your [!DNL Insight Server] has multiple IP addresses, point the Parent parameter to the NetworkLocation that defines the address to which your [!DNL Insight] and [!DNL Report] clients connect most frequently. 

1. In the [!DNL Insight Server] network location, edit the Parent parameter as shown below to point to the NetworkLocation that the server uses to resolve common names of other [!DNL Insight Servers] when it operates in a cluster. (Although this network location is not used unless an [!DNL Insight Server] operates in a cluster, it is a good practice, even in a single server configuration, to point the Parent parameter to a network location that identifies the server’s internal IP address.) 

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

The following example shows a completed address file. This file defines five network locations.

* NetworkLocation items 0 and 1 define network locations named “MyCorporateIntranet” and “Internet.” These network locations define two different IP addresses for a server named [!DNL VS01.myCompany.com]. 
* NetworkLocation item 2 is the [!DNL Insight] network location. This is the default network location used by [!DNL Insight]. In this example, the [!DNL Insight] network location inherits its AddressDefinitions from the “Internet” NetworkLocation. 

* NetworkLocation item 3 is the [!DNL Insight Server] network location. This is the default network location [!DNL Insight Server] uses when it communicates with other servers in a cluster. In this example, the [!DNL Insight Server] network location inherits its AddressDefinitions from the “MyCorporate Intranet” NetworkLocation. 

* NetworkLocation item 4 is the [!DNL Report] Server network location. This is the default network location used by [!DNL Report]. In this example, the [!DNL Report] Server network location inherits its AddressDefinitions from the “Internet” NetworkLocation. 

  ```
  Locations = vector: 5 items 
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
   
    2 = NetworkLocation:  
      Addresses = vector: 0 items 
      Name = string: Insight 
      Parent = string: Internet 
   
    3 = NetworkLocation:  
      Addresses = vector: 0 items 
      Name = string: Insight Server 
      Parent = string: MyCorporateIntranet 
   
    4 = NetworkLocation:  
      Addresses = vector: 0 items 
      Name = string: Report Server 
      Parent = string: Internet
  ```
