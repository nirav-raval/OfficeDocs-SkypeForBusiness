---
title: Set up Facilitator in Microsoft Teams for collaborative AI notes
author: DaniESmith
ms.author: danismith
manager: jtremper
ms.reviewer: solomon.alex, grace.culver
ms.date: 11/27/2024
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: 
  - M365-collaboration
  - magic-ai-copilot
ms.custom:
  - admindeeplinkTEAMS
f1.keywords:
- NOCSH
appliesto: 
  - Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Learn about how Facilitator in Microsoft Teams can take collaborative AI-generated notes powered by Copilot.
---

# Set up Facilitator in Microsoft Teams for collaborative AI-generated notes

> [!IMPORTANT]
> This feature is currently in Teams Public preview.
>
> Features in preview might not be complete and could undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.

Facilitator is a collaborative communication agent available to your users in Teams conversations. It combines the power of large language models (LLMs) and Teams data to record notes and help users be productive during collaboration. Stay in the flow of conversation and receive powerful, AI-generated notes within a single workspace. No need for users to switch from reference to reference or app to app.

Use Facilitator in peer-to-peer:

- Chats
- Meetings

Unlike an individual user's queries to Copilot in Teams, Facilitator displays Copilot's notes within the group's conversation. Users can focus on the conversation and let Facilitator take care of the note-taking for everyone.

Facilitator also continuously updates as the conversation progresses. For example, the AI-generated notes display the options being considered by the team and then replace those options with a single choice once the group decides. Now, that's intelligent collaboration right in Teams.

> [!IMPORTANT]
> Facilitator's notes are communally shared between collaborators.
>
> However, when an individual user queries Copilot in Teams using the Copilot in Teams pane, their queries and responses from Copilot remain private to that user.
>
> Users are shown a notice when their queries are private or shared with others.

For more information about how users can integrate AI-generated notes into their Teams chats, see [Keep track of chats with AI notes in Microsoft Teams](https://support.microsoft.com/office/keep-track-of-chats-with-AI-notes-in-Microsoft-Teams-0b7efbd0-fd3e-48e7-9a4b-4ea22cdc12c0).

For more information about how users can integrate AI-generated notes into their Teams meetings, see [Automate note-taking in Microsoft Teams meetings](https://support.microsoft.com/office/automate-notetaking-in-Microsoft-Teams-meetings-37657f91-39b5-40eb-9421-45141e3ce9f6).

## Security, Compliance, and Privacy

Facilitator, Copilot, and Microsoft 365 are built on Microsoft's comprehensive approach to security, compliance, and privacy.

When you use Microsoft Purview for your security and compliance management, AI-generated notes are supported by new [auditing events](/purview/audit-log-activities#microsoft-teams-activities) that surface in [Data Security Posture Management for AI](/purview/ai-microsoft-purview#data-security-posture-management-for-ai-provides-insights-policies-and-controls-for-ai-apps) and can be used by [eDiscovery with a KQL query](/purview/edisc-keyword-query-language).

To [automatically retain or delete](/purview/retention) AI-generated notes in chat, use a Microsoft Purview Data Lifecycle Management retention policy with the **Teams chat** location. Because AI-generated notes in meetings are [stored in OneDrive](#facilitator-note-storage), these notes can be automatically retained or deleted  with a retention policy or retention labels with the **OneDrive accounts** location.

Other Microsoft Purview solutions either aren't applicable for AI-generated notes or aren't yet supported.

For more information about security and privacy in Microsoft 365 Copilot, see the following articles:

- [Data, Privacy, and Security for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-privacy) for Microsoft 365 Copilot in your organization (work or school).
- [Microsoft Purview data security and compliance protections for generative AI apps](/purview/ai-microsoft-purview).
- [Copilot Pro: Microsoft 365 apps and your privacy](https://support.microsoft.com/office/copilot-pro-microsoft-365-apps-and-your-privacy-6f0d8d80-f4bb-4c9f-989e-64a4adfd62e5) for Microsoft 365 Copilot apps at home.

### Facilitator limitations

#### General Facilitator limitations

- Currently, AI-generated notes aren't supported in [external chats and meetings](trusted-organizations-external-meetings-chat.md).
- Retention labels aren't supported for cloud attachments in AI-generated notes.

#### AI-generated notes for meetings limitations

- AI-generated notes for meetings aren't automatically collected as cloud attachments in [Microsoft Preview eDiscovery](/purview/ediscovery-cloud-attachments) because it isn't currently supported.
- Meeting settings like [Prevent copy and paste](manage-chat-sensitive-meetings.md#prevent-copying-or-forwarding-of-chat) and [Watermarks](watermark-meeting-content-video.md) aren't applied to AI-generated notes in meetings.
- AI-generated notes for meetings don't inherit the meeting's sensitivity label; however, a sensitivity label can be applied to the notes' Loop component in the [Loop app or OneDrive](/purview/sensitivity-labels-loop).

## Prerequisites and licensing

The following list contains the prerequisites for users to be able to access Facilitator features in Teams chats and meetings. Users must meet all of the following requirements:

- An eligible *Microsoft 365* base license.
  - For the list of eligible base licenses, see [Understand licensing requirements for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-licensing).
- An eligible *Microsoft Teams* license.
  - Teams licenses may be included in your *Microsoft 365* subscription, or you may need to purchase a separate Teams license if you have *Microsoft 365 (no Teams)* licenses.
- A *Microsoft 365 Copilot* license.
  - For information on how to acquire *Microsoft 365 Copilot* licenses, see [Where can I get Microsoft Copilot?](https://support.microsoft.com/topic/where-can-i-get-microsoft-copilot-40a622db-6d25-4266-b008-4bbcb55cf52f)
- Be a Microsoft Teams Public preview participant.
  - For information on how to access Teams Public preview features, see [Microsoft Teams Public preview](/microsoftteams/public-preview-doc-updates).
- [Have Loop experiences in Teams for AI-generated notes in meetings turned on](#3-turn-on-loop-experiences-in-teams-for-ai-generated-notes-in-meetings).

## Facilitator note storage

AI-generated notes for meetings created by Facilitator are stored as a `.loop` file in a OneDrive folder titled **Meetings** of the user who initiated Facilitator in Teams. This data is treated as meeting transcript data.

AI-generated notes for chats created by Facilitator are stored as messaging data in each users' Exchange mailbox. This data is treated like all other Teams chat data.

## Turn on Facilitator for chats and meetings

As an admin, you control whether Facilitator is available to your entire organization or to a certain group of users.

Facilitator is turned on by default. However, if all apps are blocked for your organization, Facilitator will also be blocked.

To turn off or on Facilitator for users, complete the following steps:

### 1. Turn on Facilitator in the Teams admin center

1. Sign in to the [Teams admin center](https://admin.teams.microsoft.com/dashboard) with your Teams admin credentials.
1. In the left rail navigation, select **Teams apps** > **Manage apps**.
1. In the apps list's search box, search for **Facilitator**.
1. Select **Facilitator** from the app list.
1. In the actions menu, select **Allow** or **Block**.
1. In the pop-up, select the **Allow** or **Block** button.
    1. AI-generated notes are turned on when **Facilitator** is turned on.

You can also use [app centric management](/microsoftteams/app-centric-management) to allow and block, create policies, and assign users.

For more information about managing apps in Teams, see [Manage apps](manage-apps.md).

### 2. Allow Facilitator for a group of users

To allow Facilitator for users, a new app policy needs to be created and then assigned to users.

Follow the instructions at [Use app permission policies to control user access to apps](teams-app-permission-policies.md) to create a new app policy for Facilitator.

You can then assign the policy to your entire tenant or to a select group of users. Follow the instructions at [Add or modify app availability for users](/microsoftteams/app-centric-management#add-or-modify-app-availability-for-users) to assign the policy to users using app-centric management.

### 3. Turn on Loop experiences in Teams for AI-generated notes in meetings

Loop experiences in Teams need to be turned on in order for AI to generate notes in Teams meetings.

To turn on Loop experiences in Teams, follow the instructions at [Settings management for Loop functionality in Teams](/microsoft-365/loop/loop-components-configuration#settings-management-for-loop-functionality-in-teams).

## Related articles

- [What is responsible AI?](https://support.microsoft.com/topic/what-is-responsible-ai-33fc14be-15ea-4c2c-903b-aa493f5b8d92)
- [Frequently asked questions: AI, Microsoft Copilot, and Microsoft Designer](https://support.microsoft.com/topic/frequently-asked-questions-ai-microsoft-copilot-and-microsoft-designer-987b275d-f6f2-4d5d-94c5-e927cffae705)
- [Providing feedback about Microsoft Copilot with Microsoft 365 apps](https://support.microsoft.com/topic/providing-feedback-about-microsoft-copilot-with-microsoft-365-apps-c481c26a-e01a-4be3-bdd0-aee0b0b2a423?ocid=CopilotLab_SMC_Privacy_Feedback)
