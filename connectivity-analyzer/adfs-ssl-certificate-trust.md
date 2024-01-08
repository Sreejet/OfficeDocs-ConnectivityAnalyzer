---
title: ADFS SSL Certificate Trust
author: bradhugh
ms.author: bradhugh
manager: tpolitis
audience: ITPro 
ms.topic: article 
ms.service: remote-connect-tool
ms.localizationpriority: medium
description: "The Remote Connectivity Analyzer displays a warning when the certificate that is used for SSL can't be trusted up to the root."
ms.date: 12/20/2023
---

# ADFS SSL Certificate Trust


_**Topic Last Modified:** 2011-06-06_

The Microsoft Remote Connectivity Analyzer tool queries the Authentication Platform in the cloud to perform a realm discovery. When that process is finished, the Authentication Platform passes to the requesting client the ADFS endpoint URL that the client requires for authentication. The endpoint is a Secure Sockets Layer (SSL) connection, which has a certificate in place. The tool evaluates the fully qualified domain name (FQDN) that was assigned to the certificate (for example, STS.Contoso.com).

The Remote Connectivity Analyzer displays a warning when the certificate that is used for SSL can't be trusted up to the root. This indicates that the certificate isn't trusted by the Office 365 environment. In many cases, this condition exists because the certificate is a self-signed certificate that isn't valid for this form of authentication.

The certificate trust warning means that users might not be able to authenticate correctly to their Office 365 resources. If this issue occurs, the passive (Internet Explorer) access to the Office 365 services display a certificate warning when the user accesses the services. Only after the certificate warning is accepted can the Passive client connect. The Outlook client isn't presented with this certificate security warning, and the client fails to connect.

## More information

For information about how to troubleshoot this issue, see the Microsoft Knowledge Base article, [You receive a certificate warning when you try to access Microsoft Office 365 resources by using an identity-federated account](https://support.microsoft.com/kb/2523494).

For more information planning for identity federation, see [Prepare for single sign-on](https://onlinehelp.microsoft.com/office365-enterprises/ff652540.aspx).

For help with upgrading your current Exchange 2010 environment, see [Exchange Server Deployment Assistant](https://technet.microsoft.com/exdeploy2010/default.aspx).
