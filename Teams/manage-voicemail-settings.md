---
title: Manage Cloud Voicemail settings
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
description: Manage Voicemail settings for your users.
---

# Manage Cloud Voicemail settings for users

Voicemail settings allow you to configure voicemail settings for individual users.

Before configuring voicemail settings for your users, you should read [Set up Cloud Voicemail](set-up-phone-system-voicemail.md). For information about setting policies for groups of users, see [Manage Voicemail policies](manage-voicemail-policies.md).

The default settings for Cloud Voicemail are:

- Voicemail is enabled.
- The prompt language is set to the user's preferred language.
- The out-of-office greeting isn't enabled.
- The out-of-office greeting, when automatic replies are set in Outlook, isn't enabled.
- The out-of-office greeting, when the calendar in Outlook shows out-of-office, isn't enabled.
- Sharing of voicemail and transcription data with the service for training and improving accuracy purposes isn't enabled.
- The call answering rule is set to Regular Voicemail.
- The default greeting prompt overwrite isn't set.
- The default out-of-office greeting prompt overwrite isn't set.
- The transfer target isn't set.
- Play out-of-office greetings isn't enabled.

To manage Cloud Voicemail features for your users, you can use the Teams admin center or PowerShell. Your end users can also configure these settings in the Teams client by going to **Settings -> Calls -> Configure Voicemail.**

## Use Teams admin center

In the Teams admin center:

1. In the left navigation, go to **Users > Manage users** and select the user.

2. On the user details page, go to the **Voicemail** tab.

3. Change the settings.

4. Select **Save**.

## Use PowerShell

You can also use PowerShell to manage voicemail settings as follows:

- To manage Cloud Voicemail settings for individual users, use the [Set-CsOnlineVoicemailUserSettings](/powershell/module/teams/set-csonlinevoicemailusersettings) cmdlet.

- To view settings, use the [Get-CsOnlineVoicemailUserSettings](/powershell/module/teams/get-csonlinevoicemailusersettings) cmdlet.

- You can disable Cloud Voicemail for a user by using the [Set-CsOnlineVoicemailUserSettings](/powershell/module/teams/set-csonlinevoicemailusersettings) cmdlet and setting the `-VoicemailEnabled` parameter to `$false`.

## Voicemail settings

- **Voicemail  ** - This setting controls whether Cloud Voicemail is enabled for the user. If the setting is false, Cloud Voicemail service isn't available for the user, and a voicemail isn't recorded for the user.
- **Prompt language** - This setting specifies the language used for the prompts in the Cloud Voicemail. For more information, see [Change the default language for greetings and emails](change-the-default-language-for-greetings-and-emails.md).
- **Call answering mode** - This setting specifies the call answering rule. The rule can be:
  - *Caller can leave a voicemail* - The relevant greeting (normal or out-of-office) is played and the caller can leave a voicemail.
  - *Play an outgoing message to the caller* - Only the relevant greeting (normal or out-of-office) is played. The caller can't leave a voicemail.
  - *Service declines the call with no message* - The system disconnects the caller.
- **Call transfer** - This setting specifies the user or phone number that the caller is transferred to.
- **Default greeting prompt** - This setting specifies the text-to-speech greeting that plays if the user doesn't have a greeting recorded.
- **Default out-of-office prompt** - This setting specifies the text-to-speech greeting that plays if the user is out-of-office and doesn't have a recorded out-of-office greeting recorded.
- **Play out-of-office greetings** - This setting specifies whether or not to play the out-of-office greeting in a voicemail deposit scenario where a user has automatic replies set in Outlook.
- **Share data for service improvements** (PowerShell only) - This setting pecifies whether voicemail and transcription data is shared with the service for training and improving accuracy. If set to false, voicemail data isn't shared, regardless of user choice.

## Related articles

[Set up Cloud Voicemail](set-up-phone-system-voicemail.md)

[Manage Cloud Voicemail policies for your users](manage-voicemail-policies.md)

[Change the default language for greetings and emails](change-the-default-language-for-greetings-and-emails.md)

[Teams languages for voicemail greetings and messages](languages-for-voicemail-greetings-and-messages.md)

[Set-CsOnlineVoicemailUserSettings](/powershell/module/teams/set-csonlinevoicemailusersettings)
