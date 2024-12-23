---
title: Require a watermark for sensitive Teams meetings
ms.author: wlibebe
author: wlibebe
manager: pamgreen
ms.topic: article
ms.service: msteams
ms.reviewer: maahma
ms.date: 11/12/2024
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection: 
  - m365solution-compliantmeetings
  - m365initiative-meetings
  - highpri
  - Tier1
appliesto: 
  - Microsoft Teams
description: Learn how to enable or require watermarks on attendee video and shared content in sensitive Teams meetings.
---

# Require a watermark for sensitive Teams meetings

**APPLIES TO:** ![Image of a checkmark for yes](/office/media/icons/success-teams.png)Meetings ![Image of a checkmark for yes](/office/media/icons/success-teams.png)Webinars ![Image of a x for no](/office/media/icons/cancel-teams.png)Town halls

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

As an admin, can allow organizers with a Teams Premium license to turn on watermarks in Teams meetings both for content shared on screen and for participant's video. The watermark displays the email address of the meeting participant. Each participant sees their own email address overlaid on the meeting video or shared content. Watermarks deter participants from taking unauthorized screenshots of the meeting content. To understand how your organizers use watermarks, see [Watermark for Teams meetings](https://support.microsoft.com/office/watermark-for-teams-meetings-a9166432-f429-4a19-9a72-c9e8fdf4f589).

Watermarks are supported on Teams desktop, mobile, and Microsoft Teams Rooms. Users joining meetings from unsupported platforms have an audio-only experience.

The following participants have an audio-only experience when a watermark is in use:

- Virtual Desktop Infrastructure (VDI) participants
- Anonymous participants
- Overflow participants
- Older Teams clients
- [Direct Guest Join on Microsoft Teams Rooms devices](/microsoftteams/rooms/third-party-join)

:::image type="content" source="media/watermark-small.png" alt-text="Screenshot of Contoso Education's meeting theme featuring their brand logo, image, and colors." lightbox="media/watermark-expand.png":::

> [!NOTE]
> Meeting settings in sensitivity labels and custom meeting templates require a Teams Premium license.

Meeting watermarks are managed in the Teams admin center. After you turn on watermarks, organizers with a Teams Premium license can add them to their meetings, or you can enforce watermarks with a template or sensitivity label.

The following table shows where watermarks are configured:

|Setting|Admin policy|Sensitivity label|Template|Meeting organizer|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Apply a watermark to shared content|Yes|Yes|Yes|Yes|
|Apply a watermark to everyone's video feed|Yes|Yes|Yes|Yes|

When a watermark is being used in a meeting, the following features are turned off:

- Large gallery
- Together mode
- Content from camera

## Watermarks for sensitive and highly sensitive meetings

Watermarks can be useful for protecting confidential information shared in meetings. This is most useful when sharing information with users who don't normally have access to the information. For example, a member in the finance organization might use watermarks when sharing quarterly estimates with managers from different divisions.

Watermarks are designed to reduce the chances that confidential information being transferred out. Using watermarks in meetings where all the participants have direct access to the content being shared might not add to security.

For information about using watermarks with other meeting features to help protect confidential information in meetings, see [Configure Teams meetings with protection for highly sensitive data](/microsoftteams/configure-meetings-highly-sensitive-protection).

## Meeting recordings

If a meeting with a watermark is recorded, Microsoft Stream applies the watermark at playback time. Viewers of the recording see their own email address as a watermark on the video. If the recording file is edited or moved, the watermark isn't available at playback time.

By default, download of the meeting recording (.mp4) file is turned off for watermarked meeting recordings. However, the user who recorded the meeting can change that permission. Downloaded .mp4 files don't contain a watermark.

## Manage watermarks

You can turn on watermarks for your organizers in the Teams admin center. You can use sensitivity labels to enforce watermarks even if you turn them off for the meeting organizer in this meeting policy.

To manage watermarks for meetings, follow these steps:

1. In the Teams admin center, expand **Meetings** and select **Meeting policies**.
2. Either select an existing policy or create a new one.
3. Within your chosen policy, navigate to the **Content Protection** section.
4. For watermarks on attendee video, toggle **Watermark videos** to **On** (default) or **Off**.
5. For watermarks on content shared on screen in a meeting, toggle **Watermark shared content** to **On** or **Off**.
6. To set the watermark pattern or transparency, or see a preview, select **Edit settings**. Select **Apply** if you make changes.
7. Select **Save**.

You can also turn watermarks on or off by using PowerShell. Use the [Set-CsTeamsMeetingPolicy](/powershell/module/teams/set-csteamsmeetingpolicy) cmdlet with the **`-AllowWatermarkForCameraVideo`** and **`-AllowWatermarkForScreenSharing`** parameters.

For example:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## Related topics

- [Configure Teams meetings with three tiers of protection](configure-meetings-three-tiers-protection.md)
- [Use Teams meeting templates, sensitivity labels, and admin policies together for sensitive meetings](meeting-templates-sensitivity-labels-policies.md)
- [Teams policies reference - Watermark](settings-policies-reference.md#content-protection)
