---
title: The Client and Server Versions are Not Compatible
author: bradhugh
ms.author: bradhugh
manager: tpolitis
audience: ITPro 
ms.topic: article 
ms.service: remote-connect-tool
ms.localizationpriority: medium
description: 'Error: "The client and server versions are not compatible. The client protocol version is older than that required by the server."'
ms.date: 20/12/2023
---

# The Client and Server Versions are Not Compatible


_**Topic Last Modified:** 2011-02-10_

The Microsoft Remote Connectivity Analyzer attempts to connect to the Exchange Server via RCP over HTTP (Outlook Anywhere). If the version of the Outlook client attempting the connection is either not compatible or not allowed by the Exchange Server, then the following error can be displayed.

"The client and server versions are not compatible. The client protocol version is older than that required by the server."

## For More Information

Theoretically, you shouldn't encounter this error using the Microsoft Remote Connectivity Analyzer. Microsoft Remote Connectivity Analyzer emulates a client-side connection based on version 12.0.4228.0. If you do receive this error, then it could be possible that you modified the following value in the registry of your Exchange server and changed it to a value higher than 12.0.4228.0. If this was intentional, then you can encounter this error when using Microsoft Remote Connectivity Analyzer and any Outlook clients with a lower protocol version.

HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\MSExchangeIS\\ParametersSystem

DWORD Value: Disable MAPI Clients

For more information, see Microsoft Knowledge Base article [How to disable MAPI client access to a computer that is running Exchange Server](https://go.microsoft.com/fwlink/?linkid=3052%26kbid=288894).

The Microsoft Remote Connectivity Analyzer has limited documentation currently. To improve the documentation for each of the errors you might receive, we would like to solicit additional information from the community. Use the Community Content section to post more reasons why you failed at this point. If you need technical assistance, create a post in the appropriate [Exchange TechNet forum](https://go.microsoft.com/fwlink/?linkid=73420) or contact [support](https://go.microsoft.com/fwlink/?linkid=8158).
