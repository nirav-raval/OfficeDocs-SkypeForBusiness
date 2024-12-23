---
title: Admin - authentication requirements and functionality of the Teams Meeting add-in in Outlook
ms.author: wlibebe
author: wlibebe
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: mfoland
ms.date: 10/31/2024
ms.localizationpriority: medium
search.appverid: MET150
description: IT Admins - Learn about the requirements and policy settings for the Teams Meeting add-in in Outlook
f1.keywords:
- CSH
ms.custom: 
  - NewAdminCenter_Update
ms.collection: 
  - M365-collaboration
  - m365initiative-meetings
  - Tier2
appliesto: 
  - Microsoft Teams
---

# Admin - authentication requirements and functionality of the Teams Meeting add-in in Outlook

The Teams Meeting add-in lets users schedule a Teams meeting from Outlook. This add-in is available for Outlook on Windows, Mac, web, and mobile. The add-in is for scheduled meetings with specific participants, not for meetings in a channel. Your users must schedule channel meetings within Teams.

This article details authentication requirements and functionality of the Teams Meeting add-in in Outlook for your users. Additionally, it provides guidance on enabling private meetings and managing policy settings for users in Island Mode.

If you're having issues with the add-in, see our [Resolve issues that affect the Teams Meeting add-in for classic Outlook](/MicrosoftTeams/troubleshoot/meetings/resolve-teams-meeting-add-in-issues).

## Prerequisites

- [Webview2](/microsoft-edge/webview2/concepts/distribution) and .NET 4.8 installation is required to avoid a degraded experience with the Teams Meeting add-in.
- User permissions to execute the Regsvr32.exe file is a minimum requirement to install the Teams Meeting add-in on the computer. This prerequisite doesn't apply to new Teams.
- The Teams Meeting add-in requires an Exchange mailbox for the meeting organizer. Your users need east one Exchange mailbox set up in their Outlook profile and use it to schedule Teams meetings with the add-in. For Exchange requirements, see [How Exchange and Teams interact](exchange-teams-interact.md).

> [!NOTE]
> The add-in doesn't work if an Authentication Proxy is in the network path of the user's PC and Teams Services.

### Required meeting policies

To deploy the add-in, you must turn on **Allow the Outlook Add-in** and **Allow scheduling for private meetings**.

Use the following steps to turn on these settings:

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting Policies**.
4. Either select an existing policy or create a new one.
5. Navigate to the **Meeting scheduling** section
6. Toggle **Allow the Outlook Add-in** and **Allow scheduling for private meetings** to **On**.
7. Select **Save**

:::image type="content" source="media/meeting-schedule-small.png" alt-text="Screenshot of Teams meeting scheduling policies in the Teams admin center." lightbox="media/meeting-schedule-expand.png":::

The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.

> [!NOTE]
> Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.

## Teams Meeting add-in in Outlook for Windows

The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, Office 2019, or Office 2021 installed on their Windows PC. Your users see the Teams Meeting add-in on the Outlook Calendar ribbon.

![Screenshot of Teams Meeting add-in on Outlook ribbon.](media/Teams-add-in-for-Outlook.png)

If you're using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported. Users who need this add-in should install Click-to-Run version of Office. For details on installing theClick-to-Run version of Office, see [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f).

If your users don't see the Teams Meeting add-in, they should follow these steps:

1. Close both Outlook and Teams.
2. Restart the Teams client.
3. Sign in to Teams.
4. Restart the Outlook client.

They can also check **Add/Remove programs** for the Teams Meeting add-in; it shows up as "Microsoft Teams Meeting Add-in for Microsoft Office.

> [!IMPORTANT]
>
> - There's **no direct URL** that links to the Teams add-in.
> - If your organization runs both Teams and Skype for Business, the Teams add-in might not be available in Outlook. For details, see [Upgrade from Skype for Business to Teams](upgrade-to-Teams-on-prem-tools.md).

## Teams Meeting add-in in Outlook for Mac

The Teams Meeting button in Outlook for Mac appears in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.

The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user selects **Send**.  

## Teams Meeting add-in in Outlook Web App

The Teams Meetings button in Outlook Web App appears as part of new event creation if the user is using Outlook on the web. To learn more, see [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) .

![Screenshot of Teams Meeting add-in in Outlook Web App.](media/teams-meeting-add-in-web.png)

The meeting coordinates (the Teams join link and dial-in numbers) are added to the meeting invite after the user selects **Send**.  

## Teams Meeting add-in in Outlook mobile (iOS and Android)

The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.

![Screenshot of Teams Meeting add-in in Outlook mobile.](media/teams-meeting-add-in-mobile.png)

The meeting coordinates (the Teams join link and dial-in numbers) are added to the meeting invite after the user selects **Send**.  

## Teams Meeting add-in and FindTime for Outlook

FindTime is an Outlook add-in that creates a meeting poll, allowing participants to select available times so organizers can choose a suitable meeting time. Once the meeting invitees provide their preferred times, FindTime sends out the meeting invite for the organizer. If the **Online meeting** option is selected in FindTime, FindTime schedules a Skype for Business or Microsoft Teams meeting. FindTime uses the default online meeting channel that your organization sets.

> [!NOTE]  
> If you saved a Skype for Business setting in your [FindTime dashboard](https://support.microsoft.com/office/findtime-organizer-dashboard-cfe12f76-d6f3-4af3-88a4-95f63b952721), FindTime uses that instead of Microsoft Teams. If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.

For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).

## Authentication requirements

The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication. If users don't use this method to sign in, they can still use the Teams client, but they can't schedule [Teams online meetings](https://www.microsoft.com/microsoft-teams/online-meetings) using the Outlook add-in. If your users run into this issue, you can do one of the following options:

- If Modern Authentication isn't configured for your organization, you should configure Modern Authentication.
- If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct your users to sign in again using Multifactor Authentication.

These requirements are only valid for Outlook Classic with Teams Meeting Add-in.

To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).

## Allow private meetings

To allow private meetings, following these steps:

1. Open the Teams admin center.
2. Expand **Meetings** from the navigation pane.
3. Under **Meetings**, select **Meeting Policies**.
4. Either select an existing policy or create a new one.
5. Navigate to the **Meeting scheduling** section
6. Toggle **Allow scheduling for private meetings** to **On**.
7. Select **Save**

## Teams upgrade policy and the Teams Meeting add-in for Outlook

As an admin, you can allow  your users to use Teams alongside Skype for Business (Islands mode). When your users who are in Island mode schedule a meeting in Outlook, they can usually choose whether to schedule a Skype for Business or a Teams meeting. In Outlook on the web, Outlook Windows, and Outlook Mac, by default, users see both Skype for Business and Teams add-ins when in Islands mode.

You can use a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.

Outlook mobile can only support creating Skype for Business **or** Teams meetings. See the following table for details.

| Coexistence mode in the Teams admin center | Default meetings provider in Outlook mobile |
| --------------------------------------|---------------------------------------------|
| Islands | Skype for Business |
| Skype for Business only | Skype for Business |
| Skype for Business with Teams collaboration | Skype for Business |
| Skype for Business with Teams collaboration and meetings | Teams |
| Teams only | Teams |

To learn more, see [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).

### Manage Outlook meeting add-in availability for users on Islands mode

As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*. You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook. You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy. For steps on how to set this policy, see [Meeting policy settings - General](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode).

Determines the Outlook meeting add-in availability to users on Islands mode. With the default value of TeamsAndSfb, users see both the Skype for Business and Teams add-ins. If you set this value to Teams, the Skype for Business add-in is removed and only the Teams add-in is shown.

You can use the **Preferred app for users to join Skype for Business meetings** to control the Outlook meeting add-in availability for users on Islands mode. To learn more, see [Configure the Skype Meetings App to work with Teams](configure-skype-meetings-app-to-work-with-teams.md). For details on managing this setting through PowerShell, see [Teams settings and policies reference](settings-policies-reference.md#audio--video).

Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

## Related topics

- [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams)
- [Schedule a Teams meeting from Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
