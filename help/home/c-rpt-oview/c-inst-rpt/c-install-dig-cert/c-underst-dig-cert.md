---
description: Adobe uses X.509 digital certificates to identify and authenticate the client and server components that make up an implementation.
solution: Analytics
title: Understanding Digital Certificates
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
---
# Understanding Digital Certificates{#understanding-digital-certificates}

Adobe uses X.509 digital certificates to identify and authenticate the client and server components that make up an implementation.

When you install [!DNL Report Server], you must install the digital certificate that authorizes a named individual (for example, Jane Smith) to use the installed client application.

>[!NOTE]
>
>If you need to migrate [!DNL Report Server] to another machine or another named user, you must obtain a new certificate from Adobe. To do so, contact Adobe Customer Care.

[!DNL Report Server] presents this digital certificate to gain access to a server component. An administrator of the server component can restrict access to server resources based on the common name or organizational unit values that appear in the client’s certificate.

The X.509 digital certificates installed with Adobe applications also enable its client and server components to exchange information over Secure Sockets Layer (SSL). SSL secures transmissions over HTTP using a public-and-private key encryption system. Adobe’s implementation of SSL supports 1024-bit RSA keys and uses a 128-bit RC4 encryption algorithm.

In addition to security, the digital certificate that you install also functions as a license key that enables you to run the installed [!DNL Report Server]. To function properly, a digital certificate must be node-locked and current, or the application will not start.

## Node-locked Certificates {#section-3338f1558e7844888dced8f395888744}

A node-locked certificate is a digital certificate that has been registered to the machine on which it is installed. Node locking permanently associates a certificate with a specific node identifier (a value that uniquely identifies a particular machine). To node lock your certificate, your machine must have Internet access to the Adobe License Server or to a proxy server that has access to the License Server.

If you are installing on a machine that cannot access the Internet, you must obtain and install a special pre-locked certificate as described in [Using Digital Certificates on Machines Without Internet Access](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) on this page.

If you are installing on a machine that can access the Internet, your digital certificate is node-locked automatically the first time that you start [!DNL Report Server]. After being node-locked, the certificate cannot be used on any other machine. If you need to migrate [!DNL Report Server] to another machine, you must obtain a new, unlocked certificate from Adobe.

## Current Certificates {#section-b4053ab714514dfb97ea7f61bbb8da1e}

Besides being node-locked, a digital certificate must be current. To remain current, your certificate must be revalidated on a regular basis, (generally every 30 days, but can vary depending on your agreement with Adobe). If your machine has Internet access, the revalidation process is completely transparent. [!DNL Report Server] automatically connects to the License Server and revalidates the certificate when necessary. If your machine does not have Internet access, you need to manually install updated certificates as described in the following section.

## Using Digital Certificates on Machines Without Internet Access {#section-18cce05e2204407bb2b6b75deab9197d}

If you are installing on a machine that cannot access the Internet, you must request a pre-locked certificate for your installation of [!DNL Report Server]. A pre-locked certificate is a digital certificate that Adobe manually locks to the node identifier for the machine.

To request a pre-locked certificate, you need to send the node identifier and your certificate number to Adobe Customer Care. To obtain the node identifier for your machine, contact Adobe Customer Care to request the Adobe [!DNL Node Identifier] utility. You also can obtain the node identifier from the alert that [!DNL Report Server] issues when it attempts to connect to the License Server and cannot. When you receive the pre-locked certificate, install it as described in the last two steps of [Digital Certificate Installation Procedures](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d).

When the certificate needs to be re-validated, you must download a new validated certificate from the License Server and reinstall it on your machine (unless your agreement with Adobe states otherwise).
