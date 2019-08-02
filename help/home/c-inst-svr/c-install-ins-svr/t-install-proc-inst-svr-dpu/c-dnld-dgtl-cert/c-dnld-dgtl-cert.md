---
description: General information about digital certificates, and procedures to download and install them.
seo-description: General information about digital certificates, and procedures to download and install them.
seo-title: Downloading and Installing the Digital Certificates
solution: Insight
title: Downloading and Installing the Digital Certificates
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
index: y
internal: n
snippet: y
---

# Downloading and Installing the Digital Certificates{#downloading-and-installing-the-digital-certificates}

General information about digital certificates, and procedures to download and install them.

* [Understanding Digital Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b) 
* [Node-locked Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485) 
* [Current Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5) 
* [Using Digital Certificates on Machines Without Internet Access](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa) 
* [Digital Certificate Installation Procedures](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## Understanding Digital Certificates {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe uses X.509 digital certificates to identify and authenticate the client and server components that make up an implementation.

When you install a server component ( [!DNL Insight Server] or [!DNL Repeater]), you must install the digital certificate that Adobe has issued for the component. If you need to migrate your Adobe application to another machine, you must obtain a new certificate from Adobe. To do so, contact Adobe Customer Care.

The common name that appears on this certificate identifies the server by a specified domain name (for example, [!DNL vs001a.mycompany.com]). When a server client connects to this server, the server presents this certificate as proof that it is, indeed, the server that the client requested.

Similarly, when you install a server client (for example, [!DNL Insight] or [!DNL Report]) you must install the digital certificate that authorizes a named individual (for example, Jane Smith) to use the installed client application. If you need to migrate your Adobe application to another machine or another named user, you must obtain a new certificate from Adobe. To do so, contact Adobe Customer Care.

The client application presents this digital certificate to gain access to a server component. An administrator of the server component can restrict access to server resources based on the common name or organizational unit values that appear in the client’s certificate.

The X.509 digital certificates installed with Adobe applications also enable its client and server components to exchange information over Secure Sockets Layer (SSL). SSL secures transmissions over HTTP using a public-and-private key encryption system. Adobe’s implementation of SSL supports 1024-bit RSA keys and uses a 128-bit RC4 encryption algorithm.

In addition to security, the digital certificates that you install also function as license keys that enable you to run the installed Adobe software. To function properly, a digital certificate must be node-locked and current, or the application does not start.

## String Encryption {#section-8abe6b2d95704d38a04137d5c4602f0b}

See [String Encryption](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) for encrypting passwords.

## Node-locked Certificates {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

A node-locked certificate is a digital certificate that has been registered to the machine on which it is installed. Node locking permanently associates a certificate with a specific node identifier (a value that uniquely identifies a particular machine). To node lock your certificate, your machine must have Internet access to the Adobe License Server or to a proxy server that has access to the License Server.

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa).

If you are installing on a machine that can access the Internet, your digital certificate is node-locked automatically the first time that you start your Adobe product. After being node-locked, the certificate cannot be used on any other machine. If you need to migrate your Adobe product to another machine, you must obtain a new, unlocked certificate from Adobe.

## Current Certificates {#section-15aabaa8625c46edaa7436e1f3fc29c5}

Besides being node-locked, a digital certificate must be current. To remain current, your certificate must be revalidated on a regular basis (generally every 30 days, but can vary depending on your agreement with Adobe). If your machine has Internet access, the revalidation process is completely transparent. Your Adobe product automatically connects to the License Server and revalidates the certificate when necessary. If your machine does not have Internet access, you need to manually install updated certificates as described in the following section.

## Using Digital Certificates on Machines Without Internet Access {#section-809366329a7d4e198f95fe06c1f534fa}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Insight Server]. A pre-locked certificate is a digital certificate that Adobe manually locks to the node identifier for the machine.

To request a pre-locked certificate, you need to send the node identifier and your certificate number to Adobe Customer Care. To obtain the node identifier for your machine, contact Adobe Customer Care to request the Adobe Node Identifier utility. You also can obtain the node identifier from the alert that the Adobe software issues when it attempts to connect to the License Server and cannot.

When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b). When the certificate needs to be revalidated, you must download a new, validated certificate from the License Server and reinstall it on your machine.

## Digital Certificate Installation Procedures {#section-19f31676aad344a98e26e4fca1fad03b}

**To download and install the digital certificate**

1. Open your web browser to [https://aap.adobe.com](https://aap.adobe.com ).

   >[!NOTE]
   >
   >Your browser might prompt you to present a digital certificate at this point. If it does, simply click **[!UICONTROL Cancel]** to dismiss the dialog box.

1. On the login screen, enter the **[!UICONTROL Account Name]** and the **[!UICONTROL Password]** that you received from Adobe, then click **[!UICONTROL login]**. 

1. Locate the certificate that has been issued for your [!DNL Insight Server], then click the icon associated with that certificate.

   >[!NOTE]
   >
   >Make a note of the common name that is assigned to this certificate. You use this name in a later step.

1. When prompted to save the certificate, click **[!UICONTROL Save]**. (Note that the name of the file matches the common name associated with the certificate.) 
1. Download the file to the [!DNL Certificates] folder in the directory where you installed [!DNL Insight Server]. This folder already contains a certificate file named [!DNL trust_ca_cert.pem]. This certificate file must always be present. 

1. Rename the downloaded certificate file to:

[!DNL server_cert.pem]

