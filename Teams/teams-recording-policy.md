---
title: Introduction to recording Microsoft Teams calls and meetings
ms.author: scottfrancis
author: sfrancis206
manager: pamgreen
ms.date: 11/11/2024
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ritikag
ms.localizationpriority: medium
search.appverid: MET150
description: Learn about Teams recordings for calling, meetings, town halls, webinars, and live events.
f1.keywords:
- CSH
ms.custom: 
 - Adopt
 - seo-marvel-mar2020
ms.collection: 
- Teams_ITAdmin_Adopt
- M365-collaboration
- tier3
- m365initiative-meetings
- m365initiative-voice
- purview-compliance
appliesto: 
- Microsoft Teams
---

# Introduction to Teams recording

**APPLIES TO:** ![Image of a checkmark for yes](/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/office/media/icons/success-teams.png)Webinars ![Image of a checkmark for yes](/office/media/icons/success-teams.png)Town halls ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Calls ![Image of a checkmark for yes](/office/media/icons/success-teams.png) Live events

## Overview

In Microsoft Teams, your users can record calls and meetings to reference later and share with others. Communications can also be automatically preserved for industry compliance reasons. Call and meeting recordings capture media shared during the session (audio, video, and screen sharing activity), and are stored according to your policies.  

There are two recording features that can be enabled with policy:

- **Convenience recording**- an ad-hoc recording of a call or meeting that a user starts and manages.

- **Compliance recording**-calls and meetings that are automatically recorded without user intervention and owned by the company, using a third-party solution.

The following table compares convenience and compliance recording.

| Property           | Native Convenience Recording | Third-party Compliance Recording |
| ---------------------- | :------------------: | :---------------: |
| Recording initiator              | Licensed Teams user, enabled with meeting / calling policy            | Admin (system)  |
| Storage and access owner          | [Meeting storage and permissions](tmr-meeting-recording-change.md)               | Admin / compliance officer    |
| Participant notification enforced | Yes                | Yes             |
| Participant consent supported    | Yes    | No |
| Media recorded    | Voice, video, screen share, PPT Live    | Voice, video, screen share |
| Retention policy      | [Meeting storage and permissions](tmr-meeting-recording-change.md) | Configurable with partner solution |
| Recording policy                | Configurable with Teams Admin Center (Meeting policy + Calling policy) | Configurable with user policy        |

- Guests can't initiate convenience recordings.

- Users in trusted organizations can’t initiate convenience recordings when they join meetings in your organization.  

- Users in trusted organizations can initiate convenience recordings of unscheduled, 1:1 calls originated by either party. If they initiate, the recording adheres to the calling policy defined in the trusted organization's tenant.

- Users assigned with Edu A1 license only, can record manually but can't use meeting options to auto-record.

Meeting recordings don't capture:

- More than four peoples' video streams at once
- Whiteboards and annotations
- Shared notes
- Content shared by apps
- Videos or animations embedded in PowerPoint Live presentations
- Multi-screen share

Calls in Teams are unscheduled, peer-to-peer Teams client sessions (encompassing internal and external Teams users). In convenience and compliance recording, policy scope for calls includes Teams PSTN calls, if the user has one of the following licenses: Microsoft 365 E5, Office 365 E5, or Microsoft/Office 365 E3 with Teams Phone Add-on license.

> [!TIP]
> To learn and share more about recording options that you may allow your users to control, refer to [Record a meeting in Microsoft Teams](https://support.microsoft.com/office/record-a-meeting-in-microsoft-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24).  

## Managing recording policies

Navigate to these sections for more specific details on convenience and compliance recording:

| Meeting convenience recording    | Call convenience recording    | Meeting and call compliance recording |
| :------------------: | :---------------: | :---------------: |
| [Manage Teams recording policies for meetings](./meeting-recording.md)| [Manage Teams recording policies for calls](./call-recording-transcription-captions.md)    | [Teams compliance recording for meetings and calls](./teams-recording-compliance.md)    |

### Related topics

- [Teams settings and policies reference - Microsoft Teams | Microsoft Learn](settings-policies-reference.md)
