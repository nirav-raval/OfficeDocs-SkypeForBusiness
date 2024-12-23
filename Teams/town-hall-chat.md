---
title: Manage event chat for Microsoft Teams town halls 
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.reviewer: chbalaki
ms.date: 11/11/2024
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: 
ms.collection: 
  - M365-collaboration
  - m365initiative-meetings
  - highpri
  - Tier1
description: Learn how to manage which organizers can use event chat for their Microsoft Teams town halls.
---

# Manage event chat for Microsoft Teams town halls

**APPLIES TO:** ![Image of a x for no](/office/media/icons/cancel-teams.png)Meetings ![Image of a x for no](/office/media/icons/cancel-teams.png)Webinars ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Town halls

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

> [!NOTE]
> This feature is currently in Public Preview.

In Microsoft Teams town halls, only presenters, organizers, and co-organizers can use chat. If town hall organizers have a Teams Premium license, they can turn on **Event chat** in their **Meeting options** to allow attendees to a chat and interact with each other. Event chat is only available during the town hall. Organizers, presenters, and co-organizers can still chat separately.

As an admin, you can manage whether town hall organizers with a Teams Premium license can turn on event chat for their attendees.

For details on how your users use event chat for town halls, see [Chat in a town hall in Microsoft Teams](https://support.microsoft.com/office/chat-in-a-town-hall-in-microsoft-teams-a4a0e102-ca45-4605-a0a8-83a884547338).

## Manage event chat for your organizers

To manage whether town hall organizers with a Teams Premium license can turn on event chat for their attendees, use the **`-TownhallChatExperience`** parameter within the PowerShell [**CsTeamsEventsPolicy**](/powershell/module/teams/set-csteamseventspolicy) cmdlet.

The following table shows the behaviors of the settings for the **`-TownhallChatExperience`** parameter:

|Setting value| Behavior|
|---------|---------------|
|Optimized| **This is the default value.** Town hall organizers with this policy can turn on event chat for their attendees. |
|None| Town hall organizers with this policy can't turn on event chat for their attendees.|

### Turn off event chat

To turn off event chat, use the following script:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallChatExperience None
```

### Turn on event chat

To turn on event chat, use the following script:

```powershell
Set-CsTeamsEventsPolicy -Identity <policy name> -TownhallChatExperience Optimized
```

## Event chat eDiscovery and storage

Messages for event chat in town halls are only stored in the organizer's mailbox for up to 30 days. During this time, if you do a content search for the organizer, you can see all the messages that were sent in that event chat.
However, if you place the organizer’s mailbox on legal hold, the mailbox continues to keep the event chat messages for longer.

When the organizer leaves the company anytime from when the event is scheduled to 30 days after the town hall ends, the following details apply:

- Event chat might be unavailable during the town hall.
- Chat might be available during the event, but might not get sent to the organizer’s mailbox.
- Some messages aren't e-Discoverable in the organizer’s mailbox depending on when the organizer leaves the company.

If a town hall organizer leaves the company, you should reschedule the town hall.

You can't see which users viewed specific messages during the event. You also can't search for event chat messages in an attendee's mailbox.

Learn more, see [Get started with Content search](/purview/ediscovery-content-search).

## Limitations

- If a town hall restarts, event chat isn't available in the new town hall.
- Attendees can only send up to 200 characters of text and emojis into the Event Chat.  
- All other message composition options that are available in a [Teams Meeting chat](manage-meeting-chat.md) like sending pictures, sending GIFs, attaching files, or formatting text aren't supported. Hyperlinks are only supported if they're fewer than 200 characters.  
- Attendees can't use `@` to mention others, reply to other chat messages using the 'Reply' function, or 'React' to messages.
- Event Chat is only available for attendees, presenters, and organizers during the town hall. Event chat isn't available before or after the town hall.
- During the town hall, attendees can only see the last 200 messages.
- Attendees sending chat messages might experience a 15-30 second latency from the presenters and organizers.

## Related articles

- [Plan for town halls](plan-town-halls.md)
- [Manage meetings chat](manage-meeting-chat.md)
- [Attendance report for meetings and webinars in Microsoft Teams](teams-analytics-and-reports/meeting-attendance-report.md)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
