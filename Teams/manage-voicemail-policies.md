---
title: Manage Voicemail Policies
author: mkbond007
ms.author: mabond
manager: pamgreen
ms.reviewer: vijurtse, colongma
ms.date: 12/13/2024
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: 
  - M365-voice
  - m365initiative-voice
  - Tier1
audience: Admin
appliesto: 
  - Microsoft Teams
  - Skype for Business
ms.localizationpriority: medium
f1.keywords: 
  - CSH
ms.custom: 
  - Phone System
description: Learn how to manage Cloud Voicemail policies for your users.
---

# Manage Cloud Voicemail policies for your users

> [!WARNING]
> For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.

Voicemail policies allow you to configure and assign existing or new voicemail policies to groups of users for features such as call answering rules, voicemail transcription, transcription profanity masking, transcription translation, and system prompt language.

Before specifying policies, you should read [Set up Cloud Voicemail](set-up-phone-system-voicemail.md). For information on managing settings for individual users, see [Manage Voicemail settings](manage-voicemail-settings.md).

To manage voicemail policies, you can use the Teams admin center or the New-CsOnlineVoicemailPolicy PowerShell cmdlet.

The default policies for users are:

- Voicemail transcription is enabled.
- Voicemail transcription translation is enabled.
- Voicemail transcription profanity masking isn't enabled.
- The maximum recording duration is set to five minutes.
- Editing call answering rules is enabled.
- Primary and secondary system prompt languages are set to null and the user's voicemail language setting is used.
- No pre- or postamble configured.

You can use the global (Org-wide default) policy that's created automatically or create and assign custom policies.

> [!IMPORTANT]
> The voicemail service in Microsoft 365 caches voicemail policies and updates the cache every 5 minutes. So, policy changes that you make can take up to 5 minutes to be applied.

## Use Teams admin center

> [!NOTE]
> Managing Voicemail Policies through the Teams admin center isn't currently available in GCC High and DoD environments.

### Create a custom voicemail policy

Follow these steps to create a custom voicemail policy.

1. In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voicemail policies**.

2. Select **Add**.

3. Turn on or turn off the features that you want to use in your voicemail policy.

4. Select **Save**.

### Edit a voicemail policy

Follow these steps to edit an existing voicemail policy.

1. In the left navigation of the Microsoft Teams admin center, select **Voice** > **Voicemail policies**.

2. Select next to the policy that you want to modify, and then select **Edit**.

3. Make the changes that you want, and then select **Save**.

> [!IMPORTANT]
> You can't edit or remove the pre-configured policy instances called TranscriptionDisabled and TranscriptionProfanityMaskingEnabled.

### Assign a custom voicemail policy to users

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## Use PowerShell

You can also use PowerShell to configure and assign existing or new voicemail policies. To manage policies by using PowerShell, use the following cmdlets:

- [New-CsOnlineVoicemailPolicy](/powershell/module/teams/new-csonlinevoicemailpolicy)

- [Set-CsOnlineVoicemailPolicy](/powershell/module/teams/set-csonlinevoicemailpolicy)

- [Get-CsOnlineVoicemailPolicy](/powershell/module/teams/get-csonlinevoicemailpolicy)

- [Grant-CsOnlineVoicemailPolicy](/powershell/module/teams/grant-csonlinevoicemailpolicy)

- [Remove-CsOnlineVoicemailPolicy](/powershell/module/teams/remove-csonlinevoicemailpolicy)

## Voicemail policy settings

- **Users can edit call answering rules** - This setting controls whether the user is allowed to configure voicemail call answering rules in Microsoft Teams.
- **Maximum recording duration** - The maximum recording length controls the maximum time a voicemail can be recorded. The default is 5 minutes.
- **Primary prompt language** and **Secondary prompt language** - By default, the voicemail system prompts are presented to callers in the language selected by the user when setting up their voicemail. If there is a business requirement to have the voicemail system prompts presented in two languages, a primary and secondary language can be set.
- **Voicemail transcription** - This setting controls whether the Cloud Voicemail service generates a text transcription of the recorded voicemail and include it in the voicemail message. The transcription is done based on the language detected in the recorded voicemail.
- **Translation for transcriptions** - This setting controls whether the Cloud Voicemail service translates the transcription of the recorded voicemail. The translation is attempted in the preferred language of the voicemail receiver.
- **Mask profanity in voicemail transcription** - This setting controls whether the Cloud Voicemail service masks profanity found in the transcription of the voicemail.
- **Users can share data for service improvement** - This setting specifies whether voicemail and transcription data is shared with the service for training and improving accuracy. If set to false, voicemail data isn't be shared, regardless of user choice.
- **Play preamble audio file before voicemail greeting** - The audio file to play to the caller before the user's voicemail greeting is played.
- **Play postamble audio file after voicemail greeting** - The audio file to play to the caller after the user's voicemail greeting has played and before the caller is allowed to leave a voicemail message.
- **Disconnect the call if preamble or postamble audio can't be played** - Is playing the Pre- or Postamble mandatory before the caller can leave a message.

> [!NOTE]
> When transcription is turned off, the email users receive contains a message indicating that the audio quality wasn't good enough for transcription to take place.


## Related articles

[Configure calling policies](teams-calling-policy.md)

[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)

[Manage Voicemail settings](manage-voicemail-settings.md)
