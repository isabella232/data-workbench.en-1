---
description: The first step is to enable the IIS role on your dashboard server.
seo-description: The first step is to enable the IIS role on your dashboard server.
seo-title: Enabling IIS
solution: Analytics
title: Enabling IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
index: y
internal: n
snippet: y
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
