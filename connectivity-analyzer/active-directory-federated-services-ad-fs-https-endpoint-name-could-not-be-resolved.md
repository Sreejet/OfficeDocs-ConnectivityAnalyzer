---
title: Active Directory Federated Services (AD FS) HTTPS endpoint name could not be resolved
author: bradhugh
ms.author: bradhugh
manager: tpolitis
audience: ITPro 
ms.topic: article 
ms.service: remote-connect-tool
ms.localizationpriority: medium
description: 'The Remote Connectivity Analyzer returns the following warning if the DNS entry cannot be found for the STS endpoint: The host name could not be resolved in DNS.'
ms.date: 20/12/2023
---

# Active Directory Federated Services (AD FS) HTTPS endpoint name could not be resolved


_**Topic Last Modified:** 2011-06-21_

The Microsoft Remote Connectivity Analyzer tool queries the Authentication Platform in the cloud to perform a simulation of the token retrieval process from the on-premises ADFS server. To perform the test, the tool queries the STS endpoint that it received from the previous domain realm discovery step that it performed. This step is done to ensure that an external DNS entry is set for the STS endpoint so that external clients can resolve the endpoint.

The Remote Connectivity Analyzer returns the following warning if the DNS entry can't be found for the STS endpoint:

The host name could not be resolved in DNS.

This message might indicate either of the following scenarios:

  - The Security Token Service (STS) endpoint host record isn't added to the External DNS registrar.

  - The STS endpoint host record isn't replicated yet.

## Corrective Actions

  - Use nslookup to verify that the Host (A) record exists on the DNS server. For more information, see [To verify A resource records exist in DNS](https://go.microsoft.com/fwlink/?linkid=63001).

  - If the Host (A) resource record doesn't exist or is incorrect, manually add or modify the host record. If a non-Microsoft provider hosts your external DNS zone, you can contact that company or use custom tools to make these DNS modifications.

## More Information

For information about how to troubleshoot DNS, see [Troubleshooting DNS](https://go.microsoft.com/fwlink/?linkid=63003).

Sometimes, you might have to verify the URL that is used for the AD FS endpoint for Office 365 identity federation. For a procedure to determine the value to which the endpoint is currently set, see the “More Information” section of [Internet Explorer cannot display the Microsoft Online Portal webpage when a federated user tries to sign in](https://support.microsoft.com/kb/2419389).
