---
title: Third-party meetings on Teams Rooms
author: mstonysmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: naforer
ms.date: 08/22/2024
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
description: This article discusses how to configure your organization and Teams Rooms devices to support third-party meeting joining to Cisco Webex and Zoom.
---

# Third-party meetings on Teams Rooms

Microsoft Teams Rooms devices support a one-touch and join by ID experiences for connecting to third-party online meetings. This capability comes in two forms: Direct Guest Join (DGJ) or Cross-Platform meetings via SIP (Session Initiation Protocol) join. When third-party join is enabled, you can use Teams Rooms to join meetings hosted on other meeting platforms as easily as you can join meetings hosted on Microsoft Teams. Third-party meeting providers drive the experience of their platform on the Teams Room device.

Before you can join third-party meetings from Teams Rooms, you need to do the following steps:
1.	Understand which third-party meeting join solution is right for your organization.
2.	Configure the Teams Rooms' resource accounts Exchange mailbox to process invites for third-party and externally scheduled meetings. 
3.	Ensure no tenant policies are blocking devices from connecting to third-party meeting services.
4.	Configure Teams Rooms devices to allow third-party meetings.

## Step 1: Determine which third-party meeting join solution is right for your Teams Rooms

Teams Rooms offer two ways for connecting to third-party meetings: a SIP video based solution known as cross-platform meeting via SIP join and a WebRTC based solution known as Direct Guest Join. These solutions have different requirements and capabilities which are noted in the table. Review the table and determine which is right for your organization.

| Supported Functionality | Cross-Platform Meetings via SIP | Direct Guest Join
|--------|----------|---------|---------|
| Join Button &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp; | Amazon Chime <br>Cisco Webex <br>Google Meet <br>GoToMeeting <br>RingCentral <br>Zoom <br>Other SIP services &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp; | Cisco Webex <br>Zoom &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp; |
| Join by ID | Amazon Chime <br>Cisco Webex <br>Google Meet <br>GoToMeeting <br>RingCentral <br>Zoom <br>Other SIP services via SIP URI | Zoom |
| Events & Webinars | Cisco Webex* <br>Zoom* | Not available |
| Receive video quality | Up to 1080p / 30 fps | Up to 720p / 30 fps |
| Send video quality | Up to 1080p / 30 fps | Up to 720p / 30 fps |
| Receive content | Available | Available |
| Send content with HDMI | Available | Not available |
| Send content with [content camera](content-camera.md) | Available | Not available |
| Maximum front of room displays | Two displays | One display |
| Layout controls | Available* | Available* |
| List participant | Available* | Available* |
| View chat | Available* | Available* |
| Breakout rooms | Available* | Available* |
| View reactions | Available* | Available* |
| Send reactions | Not available | Not available |
| View content annotations | Not available | Not available |
| View transcript | Not available | Not available |
| Recording notification | Available | Available |
| Whiteboard view | Available* | Available* |
| Whiteboard interaction | Not available | Not available |
| Lobby control | Available* | Not available |
| Lobby authentication / bypass | Not available | Not available |
| Microphone mute sync | Not available | Not available |
| Teams Rooms coordinated join | Not available | Not available |
| SIP paid dialing plan required | Yes | No |
| Direct internet access required | No | Yes |
| Teams Rooms license | Teams Rooms Pro | Teams Rooms Basic <br>Teams Rooms Pro |
| Teams Rooms platform | Teams Rooms on Windows | Teams Rooms on Windows <br>Teams Rooms on Android |

> [!NOTE]
> *Third party platform features listed were available at the time this article was last updated and may vary from platform to platform. Microsoft periodically reviews these features to keep this document current but other platforms may make changes which can impact these features.<br>

> [!NOTE]
> To join a Cisco Webex meeting from a Teams Rooms device using Direct Guest Join, the Cisco meeting needs to be hosted in Webex Meetings Pro using Cisco Webex web application version WBS 40.7 or later.

## Step 2: Allow Exchange to process third-party meetings and externally created invites

When a Teams Room joins a Teams Meeting, it utilizes hidden properties in the Outlook meeting invite to know the meeting link to join. But when joining third-party meetings, Teams Rooms read the calendar invite message body so you need to retain the meeting invite body to ensure a join button can be generated for third-party meeting platforms. Similarly, a typical use case for third-party meeting join is for meetings created outside of your organization, in which case, you want users to be able to forward the externally scheduled meeting invite to their preferred meeting space and have the room accept the invite. 

To enable these scenarios, you need to modify the Exchange calendar processing rules on the room resource account. To set these room mailbox options using the [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing) cmdlet, do the following steps:

1. Connect to Exchange Online PowerShell. For more information, [Connect to Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell).

2. Using the resource account mailbox's user principal name (UPN), run the following command. Replace `<UserPrincipalName>` with the room mailbox's UPN:

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False
    ```

## Step 3A: Configure URL rewrite policies to not modify third party meeting links

To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite by the Teams Room device. If your organization uses [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/safe-links) safe links, or if you use a third-party solution that scans all URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device. To ensure invites work, you need to add the third-party meeting service's URLs to the [Defender for Office 365 Safe Links **Don't rewrite** list](/microsoft-365/security/office-365-security/safe-links), or the third-party URL rewrite exception list. If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.

Here are some example entries that you may need to add to a rewrite exception list:

- **Cisco Webex** `*.webex.com/*`
- **Zoom** `*.zoom.us/*`, `*.zoom.com/*`, `*.zoomgov.com/*`

> [!CAUTION]
> Only add URLs that you trust to your *don't rewrite* exception list.

## Step 3B: If you're utilizing Direct Guest Join, ensure your network connections are optimized to connect to your desired platform

When using Direct Guest Join, Teams Rooms devices connect directly to the website of that third-party platform. Because of this direct connection, your Teams Rooms devices need to be able to connect to that third party website. Ensure your organization’s firewalls or web filters allow the traffic without authentication and that the web traffic is in an appropriate QoS class (if applicable). Refer to the third-party meeting platforms documentation for the correct URLs and IPs to allow.

## Step 4: Enable third-party meetings on your Teams Rooms devices 

The last step you need to take is to allow Teams Rooms to join third-party meetings with Teams Rooms device settings. If the username and email address that you wish to use to join meetings is different than the device's resource account, you can configure that while enabling third-party meeting join.

## [Teams Rooms on Windows](#tab/MTRW)

If you wish to utilize the cross-platform SIP join capability, you need to enable SIP video calling on your Teams Rooms following these instructions: [SIP and H.323 Dilaing](meetings-with-sip-h323-devices.md). Once SIP calling is enabled, the Teams Room automatically uses SIP instead of WebRTC to join the enabled third-party meetings. To ensure SIP calling enabled Teams Rooms can always join a meeting, Teams Rooms will automatically use Direct Guest Join over WebRTC if the third party meeting invite doesn't contain a SIP dial string. Lastly, if SIP calling isn't enabled, Teams Rooms on Windows devices will only utilize Direct Guest Join over WebRTC for third-party meetings.

> [!NOTE]
> Automatic fallback to WebRTC DGJ works for meetings using the calendar join button. If users attempt to use join by ID and the meeting does not have SIP capabilities, the call will fail. Only enable SIP dialing in your organization if third-party meetings you join have SIP capabilities or educate your users on the fall back options with the calendar join buttons.

#### Using the Pro Management Portal

1. Log in to the [Teams Pro Management Portal](enrolling-mtrp-managed-service.md)
2. Select **Rooms**
3. Select your desired room
4. Select **Settings**
5. Select **Meetings**
6. Toggle your desired meeting platforms
7. Select **Apply**

#### Using the local device settings

To configure Teams Rooms on Windows using the touchscreen console, do the following steps:

1. On the Microsoft Teams Rooms console, select **More**.
2. Select **Settings**, and then enter the device administrator username and password.
3. Go to the **Meetings** tab and select a third-party meeting provider you wish to enable (for example, **Cisco Webex**, **Zoom**, etc.).

     :::image type="content" source="../media/use-device-settings.png" alt-text="Turning on and off third party providers.":::

4. If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.
5. If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.
6. Select **Save and exit**. Your device restarts.

     ![Meetings](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/assets/63427703/6503b72c-4482-4ec4-9492-610503d02c36)

#### Use the SkypeSettings.xml configuration file

For more information about the `SkypeSettings.xml` file, see [Manage Microsoft Teams Rooms settings with an XML configuration file](xml-config-file.md).

To enable the various platforms, set the XML element to **True**, as follows.

  ```xml
  <WebexMeetingsEnabled>True</WebexMeetingsEnabled>
  <ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
  ```

You can optionally specify a custom username and email address to join third-party meetings using the following XML elements. If the values you provide aren't valid, the Teams Rooms device defaults to use room mailbox username and email address.

  ```xml
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
  ```

## [Teams Rooms on Android](#tab/MTRA)

To configure Teams Rooms on Android locally on the device, do the following steps:

1. On the Microsoft Teams Rooms device, select **More**.
2. Select **Settings**.
3. Open **Teams admin settings**. Enter the device administrative credentials
4. Select **Meetings**.

    ![Meetings settings for MTR on Android](..\media\step-3b-enable-third-party-meetings-on-teams-rooms-on-android.png)

5. Select the toggle next to the third-party meeting providers you want to enable.
6. If you want to join meetings with a custom username and email address, select **Join with custom name and email**. To update custom personal info, press **Edit custom info** and input your preferred name and email address.
