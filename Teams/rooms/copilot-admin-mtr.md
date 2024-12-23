---
title: Admin guide to Copilot in Teams
author: mstonysmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: elaineho
ms.date: 10/23/2024
ms.topic: article
audience: admin
appliesto: 
  - Microsoft Teams
ms.service: msteams
ms.subservice: itpro-rooms
ms.collection: 
  - M365-collaboration
  - teams-rooms-consoles
  - Tier1
  - magic-ai-copilot
f1.keywords: 
  - NOCSH                           
search.appverid: MET150
ms.localizationpriority: medium
description: Learn more about how to set up Copilot and AI-based features in Microsoft Teams Rooms.
---

# Teams Rooms and Copilot overview

When you're considering deploying Copilot and AI-based features for your Teams users, there are many things to consider. The number and type of AI-based features is dependent on the type of license you assign to your Teams users, the devices you're using for Teams Rooms, and the type of license assigned to your Microsoft Teams Rooms resource account.

There are four separate sets of AI-based features that can be deployed to your users when you assign a specific license for those users and Teams Rooms.

- **Copilot** - Copilot bot integration. Adding it to all the apps including Teams. Ask questions to resolve issues, catch up during meetings (meeting recap), organize meeting points.
- **Teams Rooms** - Live transcripts and captions. Intelligent Speaker - identify in-room participants.
- **Meetings and collaboration** - Policy changes for transcription, captions, and recording.
- **Microsoft Teams** - AI-based noise suppression and video optimization. Cameo overlay. Voice isolation. Speaker attribution, face, and voice enrollment.

To see more about these features, see [Get more out of hybrid meetings with Teams Rooms and Copilot](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/get-more-out-of-hybrid-meetings-with-teams-rooms-and-copilot/ba-p/4057302).

## Getting started with Copilot

[Microsoft 365 Copilot](https://www.microsoft.com/microsoft-365/blog/2023/03/16/introducing-microsoft-365-copilot-a-whole-new-way-to-work) is an AI-powered productivity tool that uses large language models (LLMs) and integrates your data with the Microsoft Graph and Microsoft 365 Apps.

Microsoft 365 provides the ability for users to find and access their content through natural language prompting. Copilot ensures data security and privacy by adhering to existing obligations and integrating with your organization's policies. To get the most out of Copilot, you should consider optimizing data and content for Search, to ensure optimal secure access. To learn more about privacy with Microsoft 365 Copilot, see [Data, Privacy, and Security for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-privacy).

To get started with Microsoft 365 Copilot, see [Get started with Microsoft 365 Copilot - admin guide](/copilot/microsoft-365/microsoft-365-copilot-setup).

## Requirements for Microsoft 365 Copilot

The integration of Microsoft 365 Copilot and Microsoft 365 Apps enables Copilot experiences to take place inside individual apps, such as Word, PowerPoint, Teams, Excel, Outlook, and more. As a result of this integration, the requirements for using Microsoft 365 Copilot are nearly identical to the requirements for using Microsoft 365 Apps.

To see more videos on [Copilot, see Microsoft Mechanics--Podcast](<https://www.youtube.com/playlist?list=PLXtHYVsvn_b8MTl8mD8FBJIB_cSGkEaT9>).

Learn more: [Service Descriptions for Copilot](/copilot/microsoft-365/microsoft-365-copilot-requirements).

## Admin set up for Teams Rooms

Within your organization, there are several settings that you'll either need to turn on (they're off by default) or verify that they're turned on to let end users get the full advantages of Copilot in Microsoft Teams Rooms specifically. Settings like transcriptions, captioning, recording, voice isolation, voice enrollment are a few of the settings that you want to set up or turn on for your end users in your organization in order for users to benefit from Copilot and Microsoft Teams Rooms.

### Assign your licenses

After you've prepared your organization for Copilot, you can manage your Microsoft 365 licenses from the Microsoft 365 admin center. You can assign licenses to individual users or to groups of users and reassign licenses to other users depending on the level of AI support that would be needed.

#### Feature vs license comparison

| Feature | Microsoft Teams | Microsoft Teams Premium | Copilot for M365 |
|:-----|:-----|:-----|:-----|
|AI-based noise suppression|Yes|||
|AI-based video optimization (brightness and backgrounds)|Yes|||
|Suggested replies|Yes|||
|Live meeting captions and transcript|Yes|||
|Cameo video overlay on screen share and PowerPoint Live|Yes|||
|Real-time translation of meeting captions and transcripts||Yes||
|Intelligent recap (after recording) - standardized AI notes and AI tasks||Yes|Yes|
|Intelligent recap (after recording) - video, speaker, chapter markers||Yes|Yes|
|Ask any question during meeting?|||Yes|
|How did the team react to proposal?|||Yes|
|Does this plan's timeline have any conflicts?|||Yes|
|Create a table with pros and cons|||Yes|
|Microsoft Copilot UX|||Yes|
|Other: AI-powered web grounding and Microsoft 365 Graph grounding|||Yes|
|Other: Microsoft Copilot and Copilot Studio|||Yes|
|Other: Copilot in core Microsoft 365 apps|||Yes|

Learn more: [Set up Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-setup).

In Teams, there are different types of user licenses that you must assign. First, you must assign at least one user license to your users depending on what features you want available to your Teams users. Second, to take advantage of all of the AI-based features you must then assign a Microsoft Teams Pro license to each Teams Rooms console in your organization.

Learn more: [Understand licensing requirements for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-licensing)

#### Assign user licenses

For business users, a user must have a Microsoft 365 Business Basic, Business Standard, Business Premium, E3, E5, F1, or F3 and Microsoft 365 Copilot subscriptions.

To assign and manage licenses, you can use the Microsoft 365 admin center.

1. Sign in to the Microsoft 365 admin center, go to Marketplace and purchase Microsoft 365 Copilot from the list. =

1. After you purchase the subscription, go to **Billing** > **Licenses** > select **Microsoft 365 Copilot.**

1. In the product details page, assign the licenses to users and manage their access to Microsoft 365 Copilot and other apps and services.

Learn more: [Assign licenses for Copilot](/copilot/microsoft-365/microsoft-365-copilot-enable-users)

### Assign a Teams Room Pro license

To assign a Microsoft Teams Rooms Pro license, you can use the Microsoft 365 admin center.

1. Sign in to the Microsoft 365 admin center and go to **Users** > **Active users** > Select the **resource account** you created earlier.
1. In the right pane, select **Licenses and Apps**.

1. Assign a Teams Room Pro license.

1. To assign a Microsoft Teams Rooms Pro license, you can use the Microsoft 365 admin center.

   1. Sign in to the Microsoft 365 admin center and go to **Users** > **Active users** > Select the **resource account** you created earlier.
   1. In the right pane, select **Licenses and Apps**.

Learn more: [Enable users for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-enable-users).

### Update your Teams Rooms devices

Microsoft Teams Rooms on Windows supports Intelligent Speaker. Intelligent Speaker (speaker recognition or speaker attribution) is used in live meetings and in meeting transcripts to identify each the speaker. With Copilot, Teams Rooms not only enhance the overall meeting experience with Intelligent Speaker, it enables better support for collaboration and works together by adding meeting summaries and Intelligent Recap.

To support these features, you want to verify that all Teams Rooms on Windows devices are updated and have the hardware to support Intelligent Speaker or speaker recognition.

To update Teams Rooms running Windows, see [Teams Rooms app and Windows versioning support](rooms-lifecycle-support.md). Verify that all of your Teams Rooms are running the latest Windows updates.

> [!CAUTION]
> Intelligent Speaker isn't yet available for Teams Rooms on Android. It's only supported on Teams Rooms on Windows.

Although you don't get Intelligent Speaker as a features on Teams Rooms on Android yet, it's important that if you have Teams Rooms on Android devices you still will get other AI-based features like noise suppression. To see what features are available, see [Teams Rooms and panels feature comparison](teams-devices-feature-comparison.md?tabs=Commercial).

To support those features, make sure you have updated the firmware on all of your Teams Rooms on Android devices. See [Teams Rooms on Android supported firmware](../devices/certified-hardware-android.md?tabs=Android).

### Voice and face enrollment

#### Turn on voice and face enrollment

You can turn on or off voice and face enrollment for specific users, or groups using the [Set-CsTeamsMeetingPolicy](/powershell/module/teams/set-csteamsmeetingpolicy) policy. You can see the meeting settings, [Get-CsTeamsMeetingPolicy](/powershell/module/teams/get-csteamsmeetingpolicy).

You can use a new meeting policy you create or use the Global (Org-wide default) policy to turn on voice and face enrollment using the Teams admin center or PowerShell.

By default, voice and face enrollment is disabled for all users in the organization, but admins can change this setting using PowerShell.

To use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -EnrollUserOverride Enabled
```

Learn more: [Set-CsTeamsMeetingPolicy](/powershell/module/teams/set-csteamsmeetingpolicy)

To turn on or off voice and face enrollment for specific users, you can either assign a custom meeting policy to the users.

You can use PowerShell to apply the setting to a custom policy:

```PowerShell
Grant-CsTeamsMeetingPolicy -Identity <PolicyName> -EnrollUserOverride Enabled

```
Learn more: [Grant-CsTeamsMeetingPolicy](/powershell/module/teams/grant-csteamsmeetingpolicy)

> [!NOTE]
> There isn't a way to set this in Teams admin center. You must use PowerShell.

Learn more: [Voice recognition](/microsoftteams/rooms/voice-recognition)

> [!NOTE]
> Voice and face enrollment settings will be moving over to **TeamsAIPolicy** cmdlet.

#### Set up voice and face recognition profiles

Tell your users to set up a voice and face profile in the Teams app. Each person who is attending in the meeting room (as opposed to remotely) sets up their digital voice profile in the system so that they'll be identified in the transcription.

1. Go to your profile picture select **More options** > **Settings** and look under **Language** and make sure that your Teams language is set to **English**. To see the languages that are supported, see [Supported languages](voice-and-face-recognition.md#supported-languages-for-enrollment).
2. Under **Settings** again, select **Recognition** and then **Create voice profile.**
3. On the next screen, select the microphone, then select **Create voice profile** and read the text that is in the box.

Learn more: [Identify in-room meeting participants](https://support.microsoft.com/office/use-microsoft-teams-intelligent-speakers-to-identify-in-room-participants-in-a-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00#bkmk_setupvoiceprofile)

### Setting up noise suppression and isolation

#### Noise suppression

Noise suppression is identifying non human voices or noise in an environment and then minimizing or completely eliminating them from an audio stream. Part of the AI process for voice isolation is telling the difference between background chatter in a café and a user is simply listening in and if they also want to be heard clearly if they're speaking in the meeting from their device.

Noise suppression of background noise is turned on by default (and can be turned off) when you install the Microsoft Teams app but their microphone must also support it. If it does, noise suppression of background noise will significantly reduce the amount of background noise from a meeting participant, and it greatly enhances the microphone's audio quality.

:::image type="content" source="../media/mtr-devices/noise-suppression.png" alt-text="Screenshot of the noise suppression setting that is turned on." lightbox="../media/mtr-devices/noise-suppression.png"::: 

However, if you want to also isolate or have Teams be able to tell the difference between background nose and a human's voice, each user will then set up a voice profile and enable voice isolation in the Teams app.

#### Turn on voice isolation

You can manage how voice and face profiles are used to turn off Voice Isolation for users to enhance noise and voice background reduction admins can switch off voice isolation with PowerShell in the meeting policy or users can turn it on themselves in the Teams app.

:::image type="content" source="../media/mtr-devices/voice-isolation.png" alt-text="Screenshot showing the setting for voice isolation in the Teams app." lightbox="../media/mtr-devices/voice-isolation.png":::

> [!TIP]
> If you are using Bring Your Own Device (BYOD) meeting rooms and rooms audio we will turn on voice isolation automatically.

Learn more: **[Manage voice isolation for your users](/microsoftteams/voice-isolation)**

Voice Isolation is on by default in an organization. Check to make sure that it's on and if it isn't, you can use PowerShell to turn it on for all of your users.

```Powershell
Set-CsTeamsMeetingPolicy -Identity Global -VoiceIsolation Enabled
```

Each user must set up a voice profile to turn it on in their Teams app. This can be turned off or on either before or during a meeting.

If you have turned on Face profiles in your organization, the **Create face profile** button is available to end users. When they select the button, they can then set up their face profile that is used in meetings.

### Turn on Copilot for your Teams users

When you want to add Copilot to Teams, you'll need to turn it on, enable transcriptions, and meeting recordings for your end users. After you turn it on, users will see the Copilot icon and options but transcription for meetings will also need to be turned on as well.

To pin a Copilot icon to the Teams app, see [Pin Microsoft Copilot to the navigation bar](/copilot/microsoft-365/pin-copilot).

To turn on Copilot for your Teams users.

1. In the [Teams admin center](https://admin.teams.microsoft.com/), go to **Meetings** from the navigation pane > **Meeting Policies**.
2. Either select an existing policy or create a new one. Select **On** or **On only with retained transcript** from the dropdown for the **Copilot** setting.

You can use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -Copilot Enabled
```

Learn more: [Meeting transcription](/microsoftteams/copilot-teams-transcription)

### Set up meeting transcription, captions, and recording

Transcription allows users to play back meeting recordings with closed captions and review important discussion items in the transcript. Transcription and captions along with the meeting's recording help create inclusive content for viewers. It also helps Copilot to create meeting summaries, recaps, action items, and other features.

:::image type="content" source="../media/mtr-devices/captions-and-transcripts.png" alt-text="Screenshot with captions and transcriptions settings in the Teams app." lightbox="../media/mtr-devices/captions-and-transcripts.png":::

#### Turn on meeting transcriptions

To turn on meeting transcription.

1. In the [Teams admin center](https://admin.teams.microsoft.com/), go to **Meetings** > select **Meeting Policies**.
2. Either select an existing policy or create a new one. 
3. On the meeting policy page, under **Recording & transcription**, turn on **Meeting recording**. This setting is off by default.

> [!NOTE]
> Under **Recording & transcription**, there are several other recording options that are available for you to set. Review all of the settings to ensure that they meet the needs of your organization.

You can use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowTranscription $true
```

Learn more: [Meeting transcription](/microsoftteams/meeting-transcription-captions)

#### Turn on meeting recording

Recording meetings is optional, however, there are many cases that you want to allow meetings to be recorded. Meeting recordings as you imagine is recording a stream of audio and video for a meeting, but in
the case with Copilot, it's used to help generate meeting summaries, recaps, and other information after the meeting has ended. When a meeting is recorded:

- It gets uploaded to OneDrive (private meetings) or SharePoint (channel meetings).
- People invited to the meeting have permissions to the recording (guests and external attendees can view the recording only if the recording is explicitly shared with them).
- Microsoft Purview compliance features apply to the meeting recording files the same as with other files.
- It's linked in the chat for the meeting.
- It's displayed in the Recordings and Transcripts tab for the meeting in Teams calendar.
- It's added to various file lists across Microsoft 365: Shared with me, office.com, Recommended, Recent, etc.
- Microsoft 365 Search indexes it.

There's also an option for recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and review important discussion items in the transcript.

You can use a new meeting policy you create or use the Global (Org-wide default) policy to turn this on using the Teams admin center or PowerShell.

1. In the [Teams admin center](https://admin.teams.microsoft.com/), under **Meetings** > **Meeting policies**.
1. Select the policy that you want to edit. Turn **Meeting recording** On or Off.

You can use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity \<policy name\> -AllowCloudRecording Enabled
```

Learn more: [Meeting recording](/microsoftteams/meeting-recording?tabs=meeting-policy)

#### Turn on Live captioning

Teams has built-in closed captioning you can turn on from the meeting controls. Live captions can make your meeting more productive and inclusive for participants who are deaf or hard-of-hearing, have different levels of language proficiency, or the meeting participant is in a noisy place during a meeting will all benefit from live captions.

Live captions and transcriptions can show you the text of a conversation in a Teams meeting. They can help you keep records or better understand what others are saying during a meeting.

It's available in the desktop version of the Teams app but users can set transcription and captioning options under **Settings** > **Captions and transcripts** in the Teams app.

:::image type="content" source="../media/mtr-devices/captions-and-transcripts.png" alt-text="Screenshot with the captions and transcriptions settings." lightbox="../media/mtr-devices/captions-and-transcripts.png":::

Learn more: [Live transcriptions](<https://support.microsoft.com/office/view-live-transcription-in-microsoft-teams-meetings-dc1a8f23-2e20-4684-885e-2152e06a4a8b>)

If your organization is using OneDrive for Business and SharePoint for meeting recordings, you should turn on **Allow transcription** in the Teams meeting policy and turn on the **Always show live captions in meeting** in the Teams app and encourage your users to start transcription in every meeting. This will make captions available in the post-meeting recording when it's generated by Copilot as well.

1. In the [Teams admin center](https://admin.teams.microsoft.com/).
2. Under **Meetings**, select **Meeting Policies**. Either select an
existing policy or create a new one.
3. On the meeting policy page, under **Recording & transcription**, set **Live captions** to **Off, but
organizers and co-organizers can turn them on.

You can use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowTranscription $true
```

#### Turn on Live transcriptions

By default, transcripts are shown in the language spoken during a meeting or event. Live translated transcription allows your users to translate the meeting or event transcript into the language they're most comfortable with.

You can use a new meeting policy you create or use the Global (Org-wide default) policy to turn this on using the Teams admin center or PowerShell.

To turn on Live transcription, **Transcription** but be set to **On**
first.

1. In the [Teams admin center](https://admin.teams.microsoft.com/).
2. Under **Meetings**, select **Meeting Policies**. Either select an existing
policy or create a new one.
3. On the meeting policy page, under **Recording & transcription**, turn on **Meeting recording**. This
setting is off by default.

You can use PowerShell to turn this on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <policy name> -Copilot Enabled -AllowTranscription $true
```

Learn more: [Meeting transcription and captions](/microsoftteams/meeting-transcription-captions)

### Turn it on so speakers will be identified in meetings

In meeting transcripts, live transcripts, captions and in meeting recaps using Copilot, you want users to be able to identify the person that is talking during the meeting or attribution. By default, this is turned on at the organization level (Global (Org-wide default) policy), but in the case you want to turn this off for another part of your organization, you can create a new meeting policy.

You can optionally tell users to go verify that it's turned on by going to in the Teams app to **Settings** > **Captions and transcripts** > **Automatically identify me in meeting captions and transcripts** and make sure it's turned on.

:::image type="content" source="../media/mtr-devices/auto-id.png" alt-text="Screenshot with the 'automatically ID me in meetings' setting." lightbox="../media/mtr-devices/auto-id.png":::

**Speaker Attribution Modes**:

- **Enabled**: Speakers are identified in transcription.
- **EnabledUserOverride**: Speakers are identified in transcription if enabled, however, users can change this setting and choose not to be identified in the Teams profile settings.
- **DisabledUserOverride:** Speakers are not identified in the transcription. If enabled, users can change this setting and choose to be identified in their Teams profile settings.
- **Disabled**: Teams won't identify and display speaker names next to audio streams in meetings.

You can use PowerShell to set this:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -SpeakerAttributionMode Enabled
```

### To identify in-room participants in a meeting transcription

Using [Microsoft Teams Rooms](https://rooms.microsoft.com/) on Windows you can hold meetings where in-room participants can be identified in live transcription and in meeting transcripts. When you enable Intelligent Speaker, during the meeting all participants can then easily see who's saying what, and the post-meeting transcript identifies both remote and in-room attendees.

Learn more: [Identify in-room meeting participants](https://support.microsoft.com/office/use-microsoft-teams-intelligent-speakers-to-identify-in-room-participants-in-a-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00#bkmk_setupvoiceprofile)

#### Enable Intelligent Speaker

Voice profile data is used in any meeting with an Intelligent Speaker. However, each user must set up a voice and face profile in the Teams app. See, [Voice and face recognition](voice-and-face-recognition.md) or [Set up voice and face profiles](copilot-admin-mtr.md#set-up-voice-and-face-recognition-profiles).

> [!NOTE]
> Intelligent Speaker is only available on Microsoft Teams Rooms for Windows.

Enabling people recognition or Intelligent Speaker requires you to set the CsTeamsMeetingPolicy to let individual voice and face profiles to be used for recognition in meetings.

Use PowerShell to turn it on:

```PowerShell
Set-CsTeamsMeetingPolicy -Identity <PolicyName> -RoomAttributeUserOverride Attribute
```

Learn more: [Set-CsTeamsMeetingPolicy](/powershell/module/teams/set-csteamsmeetingpolicy)

> [!NOTE]
> No special microphones are needed to use this feature. Microphones that are included in Teams Rooms for Windows devices all support Intelligent Speaker. However, there are also addtional hardware devices that can be used along side of Teams Rooms that support Intelligent Speaker. To see which devices are certified and can be used, see [Certified Intelligent Speakers](certified-hardware.md?tabs=Devices).

## Related articles

- [Manage Microsoft 365 Copilot settings in the Microsoft 365 admin center](/copilot/microsoft-365/microsoft-365-copilot-page)
- [Manage Microsoft 365 Copilot in Teams meetings and events](/microsoftteams/copilot-teams-transcription)
- [Microsoft 365 reports in the admin center – Microsoft 365 Copilot usage](/microsoft-365/admin/activity-reports/microsoft-365-copilot-usage)