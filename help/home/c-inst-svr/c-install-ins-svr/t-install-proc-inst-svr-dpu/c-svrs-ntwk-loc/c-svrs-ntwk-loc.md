---
description: Insight Server’s clients (Report and Insight) use common names to refer to Insight Servers.
title: Defining the Server's Network Location
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
---
# Defining the Server's Network Location{#defining-the-server-s-network-location}

Insight Server’s clients (Report and Insight) use common names to refer to Insight Servers.

 For example, when you connect [!DNL Insight] or [!DNL Report] to an [!DNL Insight Server], you identify the server by its common name (for example, [!DNL Server.MyCompany.com]). Internally, the client resolves the common name to a numeric IP address before sending a request to the server.

To resolve common names to IP addresses, [!DNL Insight Server’s] clients use a local lookup file called the address file. The address file lists the common names of [!DNL Insight Servers] installed at your organization and identifies their numeric IP addresses. A client automatically receives a copy of the address file when it opens a profile on the [!DNL Insight Server].

When a client issues a request to an [!DNL Insight Server], it attempts to resolve the server’s common name through the address file. If the address file identifies an IP address for the requested server, the client routes the request to the specified address. If the address is not defined (for example, the address file does not define the server’s common name), the request fails. Optionally, you can configure clients to resolve addresses through the operating environment’s normal Domain Naming Service (DNS) mechanism if a name is not defined in the client’s address file. For instructions, see the Parent parameter in the [NetworkLocation Parameters table](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) in the following section.
