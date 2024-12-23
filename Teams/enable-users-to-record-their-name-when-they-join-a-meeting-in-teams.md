---
title: "Allow users to record their name for a meeting"
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: oscarr
ms.date: 11/1/2024
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-audio-conferencing
search.appverid: MET150
ms.collection: 
  - M365-collaboration
  - Tier1
  - m365initiative-meetings
audience: Admin
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom: 
  - Audio Conferencing
  - seo-marvel-mar2020
description: "Learn how to manage whether your users can record their names when they join a meeting in Microsoft Teams."
---

# Allow users to record their name when they join a meeting in Microsoft Teams

When you set up Audio Conferencing in Microsoft 365 or Office 365, you get phone numbers for your users through an audio conferencing bridge. A conferencing bridge can have one or more phone numbers that are included at the bottom of the meeting invite. These phone numbers allow users to join Microsoft Teams meetings by dialing in.

As an admin, you can manage whether callers who dial in can record their name before joining a meeting.

## Allow callers to record their name in the Teams admin center

Using the Microsoft Teams admin center:

1. Navigate to **Meetings** > **Conference Bridges**.

2. At the top of the **Conference Bridges** page, select **Bridge settings**.

3. Toggle **Meeting entry and exit notifications** to on.

4. For **Entry/exit announcement type** select **Names or phone numbers** from the dropdown.

5. Toggle **Ask callers to record their name before joining a meeting** to **On**.

6. Select **Save**.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## Manage whether callers can record their names with PowerShell

To manage whether callers can record their names with PowerShell, use the **`-EnableNameRecording`**. **`-EntryExitAnnouncementsType`**, and **`-EnableNameRecording`** parameters, within the PowerShell [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/teams/set-csonlinedialinconferencingtenantsettings) cmdlet. For script examples, see [Set-CsOnlineDialInConferencingBridge](/powershell/module/teams/Set-csonlinedialinconferencingtenantsettings).

## Related topics

- [Change the settings for an audio conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)
- [Turn on or off entry and exit announcements for meetings in Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)
