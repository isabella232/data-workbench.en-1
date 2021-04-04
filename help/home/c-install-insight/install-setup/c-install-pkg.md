---
description: Files included in the Data Workbench installation package.
title: Files Included in the Installation Package
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
---
# Files Included in the Installation Package{#files-included-in-the-installation-package}

Files included in the Data Workbench installation package.

The following directories are included in the Insight package.

## Program Files {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

The Workstation executable (**[!DNL Insight.exe]**) and supporting files are installed by default to this folder.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> The Data Workbench client executable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Set language and the path for the <span class="filepath"> Appdata </span> folder. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data workbench now supports an Input Method Editor (IME) as a secondary text entry process that allows you to enter international characters from your keyboard using a floating text box. Data workbench will support English by default but also allows you to load other files to support international languages, such as a virtual Chinese keyboard (Pinyin IME). </p> <p>A new dictionary file <span class="filepath"> (Insight.zbin </span>) is required by the client application to support the IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Executable to uninstall Workstation and delete files. </td> 
  </tr> 
 </tbody> 
</table>

## AppData Files {#section-afddeedf8d29451f996fa46b2dfe932c}

Data Files (**[!DNL Insight.cfg]**, Profiles, Certificates, trace logs, and user files) are saved by default to: 

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> The Data Workbench configuration file. Defines parameters within which Data Workbench operates. See <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuring the Connection to Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Contains the program files for Data Workbench. </p> <p> <p>Note:  You should not remove or alter any of these files. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificates </span> </b> </td> 
   <td colname="col2"> Contains the certificate file, <span class="filepath"> trust_ca_cert.pem </span>, and the named user digital certificate for Data Workbench. See <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Downloading and Installing the Digital Certificate </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Configuration </span> </b> </td> 
   <td colname="col2"> Contains the files that are used for Workstation configuration. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geography </span></b> </td> 
   <td colname="col2"> Files for graphic rendering of geographical visualizations. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Trace </span></b> </td> 
   <td colname="col2"> Log files generated from the Workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profiles </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Predictive Analytics</i> and other profile configuration files. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Setup wizard to install additional client computers in the <b> <span class="filepath"> Software/Insight </span></b> folder. </td> 
  </tr> 
 </tbody> 
</table>
