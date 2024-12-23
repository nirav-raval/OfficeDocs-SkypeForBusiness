---
title: SIP and H.323 dialing with Teams Rooms
author: mstonysmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: naforer
ms.date: 10/30/2024
ms.topic: article
audience: Admin
ms.service: msteams
ms.subservice: itpro-rooms
appliesto: 
  - Microsoft Teams
ms.collection: 
  - M365-collaboration
  - teams-rooms-devices
  - Tier1
f1.keywords: 
  - NOCSH
ms.localizationpriority: medium
description: Learn about how to set up Teams Rooms to receive and place calls using SIP and H.323.
---

# SIP and H.323 Dialing with Teams Rooms

SIP and H.323 dialing is available on Microsoft Teams Rooms on Windows devices licensed with a Microsoft Teams Rooms Pro license. This functionality uses a specific SIP-supporting plan from a Cloud Video Interop provider which you can enable in your tenant. 

This feature allows Teams Rooms devices to make audio, video, and screen sharing calls with other conferencing endpoints that support SIP or H.323 protocols, whether internal or external to your organization. By default, SIP and H.323 dialing is disabled. To enable it, follow the steps in this document using Microsoft Teams PowerShell. SIP and H.323 calls from Teams Rooms devices are routed through the Microsoft 365 cloud to your plan provider, requiring no additional network or firewall rules if you already have working Teams Rooms devices.

If you have multiple Teams Rooms all with Pro licenses deployed in your organization, you can configure SIP and H.323 dialing for one or all of those Teams Rooms. 

> [!IMPORTANT]
>
> This feature is exclusive to Microsoft Teams Rooms devices with a Teams Rooms Pro license and is only compatible with Teams Rooms on Windows devices. It does not support Teams Rooms on Android devices.

## Implementation Requirements

To enable your Teams Rooms device to use SIP and H.323 dialing:

1. The Teams Rooms resource account must have a Teams Rooms Pro license assigned.
2. You need an agreement with one of the certified [Cloud Video Interop providers](../cloud-video-interop.md) (CVI) which offer SIP & H.323 dialing capabilities. Refer to that link for a list of providers that enable SIP & H.323 dialing from Teams Rooms.
3. You need information from your SIP-supporting provider about the "AreaCode" to use when configuring SIP & H.323 dialing in Microsoft Teams Rooms. If you have CVI enabled, the "AreaCode" may match the "TenantKey" used when you configured it.
4. You must create and assign a SIP & H.323 Video Teleconferencing Policy to your Teams Rooms resource accounts.

## How to configure a SIP / H.323 Video Teleconferencing Policy

The Teams Room Video Teleconference Policy enables SIP & H.323 calling on Teams Rooms devices. You must first create a new Teams Room Video Teleconferencing policy and set the parameters to enable SIP and H.323 dialing. If you have multiple CVI providers in your tenant, you can configure multiple Video Teleconferencing policies, and assign different policies to different Teams Room resource accounts. Although you can only have one Global policy, individual policies take precedence if directly assigned to an account.

> [!Note]
>
> These features can only be configured using Microsoft Teams PowerShell module. 

### Creating a new Teleconference Policy

If necessary, update or install the Teams PowerShell module and sign in to Teams PowerShell following these instructions: [Microsoft Teams PowerShell](../teams-powershell-install.md). 

Once signed in, you need to create a new Video Teleconferencing policy, using the [Set-CsTeamsRoomVideoTeleConferencingPolicy cmdlet](/powershell/module/teams/set-csteamsroomvideoteleconferencingpolicy). You can create a single "Global" policy, which applies to all Teams Rooms resource accounts, allowing SIP & H.323 calling on all devices. Or you can create an individual policy, which needs to be assigned to each Teams Rooms resource account you want to have this ability.

Global Policy Example:

```PowerShell
New-CsTeamsRoomVideoTeleConferencingPolicy -Identity Global -Enabled $true -AreaCode "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx" -ReceiveExternalCalls Enabled -ReceiveInternalCalls Enabled
```

Individual Policy Example:

```PowerShell
New-CsTeamsRoomVideoTeleConferencingPolicy -Identity "TurnOnSIPH323" -Enabled $true -AreaCode "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx" -ReceiveExternalCalls Enabled -ReceiveInternalCalls Enabled 
```

>[!Important]
>
>The `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx` entry in the command is a placeholder for a GUID that is provided by the CVI provider that offers this feature.

>[!Note]
>
>If the Policy is set to `Enabled`, then the `AreaCode` parameter is required. This value is provided by the CVI provider that offers this feature.
>`ReceiveExternalCalls` and `ReceiveInternalCalls` parameters are disabled by default. They take only two values either `Enabled` or `Disabled`. 

### Viewing existing or newly created Teleconference Policies
Once you create a Teams Room Teleconferencing policy in your organization, or to view all existing policies, run the [Get-CsTeamsRoomVideoTeleConferencingPolicy cmdlet](/powershell/module/teams/get-csteamsroomvideoteleconferencingpolicy).

```PowerShell
Get-CsTeamsRoomVideoTeleConferencingPolicy
```
### Assigning a Teleconference Policy
To apply a policy to a Teams Rooms device, you need to run the [Grant-CsTeamsRoomVideoTeleConferencingPolicy cmdlet](/powershell/module/teams/grant-csteamsroomvideoteleconferencingpolicy).

```PowerShell
Grant-CsTeamsRoomVideoTeleConferencingPolicy -Identity "<resource account UPN>" -PolicyName "TurnOnSIPH323"
```

### Modifying a Teleconference Policy
If you wish to modify an existing policy, you can do so with the [Set-CsTeamsRoomVideoTeleConferencingPolicy cmdlet](/powershell/module/teams/set-csteamsroomvideoteleconferencingpolicy). This example blocks external inbound calling.

```PowerShell
Set-CsTeamsRoomVideoTeleConferencingPolicy -Identity `TurnOnSIPH323` -ReceiveExternalCalls `Disabled` 
```


