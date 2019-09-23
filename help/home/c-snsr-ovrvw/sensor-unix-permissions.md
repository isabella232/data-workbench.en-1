---
description: Information about Sensor UNIX file permissions such as the collector module, the transmitter process, the configuration file, and more.
seo-description: Information about Sensor UNIX file permissions such as the collector module, the transmitter process, the configuration file, and more.
seo-title: Sensor UNIX File Permissions
title: Sensor UNIX File Permissions
uuid: 04d159b5-6569-48b6-a2db-9a0b40118ffe
---

# Sensor UNIX File Permissions{#sensor-unix-file-permissions}

Information about Sensor UNIX file permissions such as the collector module, the transmitter process, the configuration file, and more.

## The Collector Module {#section-49c855baece24c4695184bfcbeeddebf}

<table id="table_0B972ABD2A5342CA8A6FE80EB666298A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Quality </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>File name </p> </td> 
   <td colname="col2"> <p>mod_visual_sciences.so (on Apache web servers and IBM HTTP servers) </p> <p>libvisual_sciences.so and J2EECollector.jar (on J2EE application servers) </p> <p>aol_visual_sciences.so (on AOL web servers) </p> <p>saf_visual_sciences.so (on Sun Java web servers) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Permissions </p> </td> 
   <td colname="col2"> <p>rwx r-x r-x (IBM HTTP and Apache 1.3.x) </p> <p>rwx rwx r-x (Apache 2.0.x) </p> <p>rwx --x --x (J2EE, AOL, and Sun Java web servers) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Read by </p> </td> 
   <td colname="col2"> <p>The web server, which sometimes runs as the root user, but more often runs under a specific user account </p> <p>If the web server runs under a non-root account, the permissions on this file must allow that account to read it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Runs as </p> </td> 
   <td colname="col2"> <p>A child process in the web server </p> <p>Child processes run under a user account specified in your web server configuration. On many servers, this is a special account with very limited privileges called “nobody” — but not all web servers use this account. Check your web server’s configuration file to determine what user account is set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reads from </p> </td> 
   <td colname="col2"> <p>txlogd.conf </p> <p>The diskQueue file </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Writes to </td> 
   <td colname="col2"> The diskQueue file </td> 
  </tr> 
 </tbody> 
</table>

## The Transmitter Process {#section-8af432472e9d4bd9a42270bf27adf33a}

<table id="table_3028CC9640D54016BD8CA7F9CAA34280"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Quality </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Permissions </p> </td> 
   <td colname="col2"> <p>rw- r-- r-- (IBM HTTP, AOL, and Sun Java web servers) </p> <p>rw- rw- r-- (Apache web servers and J2EE application servers) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Read by </td> 
   <td colname="col2"> The transmitter program </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Written by </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## The Configuration File {#section-341d85f2abf34a69970a0ff91b7e9123}

<table id="table_79AC614F5435443CB3CFB457B8375704"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Quality </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> txlogd.conf </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Permissions </p> </td> 
   <td colname="col2"> <p>rw- r-- r-- (IBM HTTP, AOL, and Sun Java web servers) </p> <p>rw- rw- r-- (Apache web servers and J2EE application servers) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Read by </td> 
   <td colname="col2"> <p>The collector module </p> <p>The transmitter program </p> <p>The administrator responsible for installing, configuring, and maintaining Sensor </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Written by </td> 
   <td colname="col2"> The administrator responsible for installing, configuring, and maintaining Sensor </td> 
  </tr> 
 </tbody> 
</table>

## The Certificate Authority File {#section-2818dff887b8456992bdc589fd8510f3}

<table id="table_ED8BEEEFA91245C3A6645D27B148A5A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Quality </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> trust_ca_cert.pem </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Default Permissions </p> </td> 
   <td colname="col2"> <p>rw- r-- r-- (IBM HTTP, AOL, and Sun Java web servers) </p> <p>rw- rw- r-- (Apache web servers and J2EE application servers) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Read by </td> 
   <td colname="col2"> The transmitter program </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Written by </td> 
   <td colname="col2"> -- </td> 
  </tr> 
 </tbody> 
</table>

## The Disk Queue {#section-0407c52744de41af867d0b7933a69256}

<table id="table_35DB32228E7443FF90BE24AB14CBE54B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Quality </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File name </td> 
   <td colname="col2"> User defined </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Default Permissions </td> 
   <td colname="col2"> rw- rw- rw- (All server types) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Read by </p> </td> 
   <td colname="col2"> <p>The collector module </p> <p>The transmitter program </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Written by </p> </td> 
   <td colname="col2"> <p>The collector module </p> <p>The transmitter program </p> </td> 
  </tr> 
 </tbody> 
</table>

