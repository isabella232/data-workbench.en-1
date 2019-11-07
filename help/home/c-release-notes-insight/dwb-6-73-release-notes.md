---
description: New features and fixes in Data Workbench 6.73.
title: Data Workbench 6.73 Release Notes
uuid: bba63a8c-9cb7-4334-b66a-22db92153066
---

# Data Workbench 6.73 Release Notes{#data-workbench-release-notes}

New features and fixes in Data Workbench 6.73.

## Data Workbench 6.73 Release Notes {#topic-7655534554ac4a4b816af1bd73b06aad56757}

New features and fixes in Data Workbench 6.73.

## Fixes {#section-160baf6ea04c45a993777ee4260691ed}

* Fixed an issue in Workstation where users were unable to sign in on some hardware with high resolution and high DPI. 
* Fixed an issue in the server where Email was missing in Archive file names when using IMS login. 
* Updated OpenSSL to version 1.1.0h which includes several vulnerability fixes and new SSL Ciphers. 
* Updated the below listed open source libraries to the latest stable versions

    * libssh2 1.8.0 
    * Apache Xerces 3.2.1 
    * Apache Xalan 1.11 
    * libpng 1.6.34 
    * libarchive 3.3.2 
    * zlib 1.2.11 
    * pcre 8.42

* Added error logging when Lookup file row count exceeds more than supported 357913908 rows.

## Known issue {#section-f2cb932f6225457a872fb916a78df89a}

* Data Workbench Workstation version 6.73 does not connect to Data Workbench Servers versions 6.61 and older. The reason is, older server versions use a weak form of ciphers not supported in version 6.73. To enable support for older versions

    1. Override default SSL Ciphers list on the server with a strong cipher list supported by OpenSSL version 1.0.1h. To override, add key ‘SSL Ciphers’ in the ‘Communications.cfg’ files available in ‘Components’ and ‘Components for Processing Servers’ directories. For example: `SSL Ciphers = string: !aNULL:AESGCM`     
    
       >[!NOTE]
       >
       >Ensure that the key is placed at the same level as the SSL Port. For details refer to [Communications Configuration Settings](https://marketing.adobe.com/resources/help/en_US/insight/svrprod/c_comm_cfg_stgs.html)

    1. Place the latest trust_ca_cert.pem file on the server 6.61 and older servers. This setting is applicable to all Workstation 6.7x versions.

See [archived release notes](https://marketing.adobe.com/resources/help/en_US/insight/insight_release_notes_prev.pdf) for Data Workbench 5.3 to 5.52. 
