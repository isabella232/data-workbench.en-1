---
description: The first step is to enable the IIS role on your dashboard server.
title: Enabling IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
---
# Enabling IIS{#enabling-iis}

The first step is to enable the IIS role on your dashboard server.

1. Under **[!UICONTROL Administrative Tools]**, open the **[!UICONTROL Server Manager]**.
1. Right-click the Roles menu item in the left-hand portion of the **[!UICONTROL Server Manager]** window.
1. Select **[!UICONTROL Add Roles]**.
1. Select **[!UICONTROL Web Server (IIS)]** and continue with the **[!UICONTROL Add Roles Wizard]**. Make sure that the following Role Services are enabled:

   |  Common HTTP Features  |
   |---|
   |  Static Content  |
   |  Default Document  |
   |  Directory Browsing  |
   |  HTTP Errors  |
   |  HTTP Redirection  |

   |  Application Development  |
   |---|
   |  ASP.NET  |
   |  .NET Extensibility  |
   |  ISAPI Extensions  |
   |  ISAPI Filters  |

   |  Health and Diagnostics  |
   |---|
   |  HTTP Logging  |
   |  Logging Tools  |
   |  Request Monitor  |
   |  Tracing  |
   |  Custom Logging  |

   |  Security  |
   |---|
   |  Basic Authentication  |
   |  Windows Authentication  |
   |  URL Authentication  |
   |  Request Filtering  |
   |  IP and Domain Restrictions  |

   |  Management Tools  |
   |---|
   |  IIS Management Console  |
   |  IIS Management Script and Tools  |
   |  Management Service  |

1. Follow the Wizard to complete the installation.
