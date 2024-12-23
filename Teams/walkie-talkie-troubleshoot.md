---
title: Troubleshoot Walkie Talkie issues
author: lana-chin
ms.author: v-chinlana
manager: jtremper
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: yinchang
description: Use this guidance to help you troubleshoot common issues for the Walkie Talkie app in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords: NOCSH
ms.collection: 
- M365-collaboration
- m365-frontline
- teams-1p-app-admin
- highpri
appliesto: 
  - Microsoft Teams
  - Microsoft 365 for frontline workers
ms.date: 12/06/2024
---

# Troubleshoot Walkie Talkie issues

This article provides guidance for troubleshooting common issues that users might encounter when using the Walkie Talkie app in Microsoft Teams. Use this information to identify and address issues to help with more effective troubleshooting for a smooth communication experience.

## Identify issues

Use the following table to help identify the source of issues, along with recommended actions to take.

|Is it...  |Try...|Recommended action  |
|---------|---------|---------|
|Network|In Teams, go to **Settings** > **Walkie Talkie** > **Test Network Quality**, and check the network connection strength.|If the results show a poor connection, go to an area with stronger network coverage.|
|Device|Check whether the issue occurs on only one device or across multiple devices.|If the issue occurs only on the one device, swap or replace the device.|
|Headset|Try a different headset.|If the issue occurs only with a particular headset, swap out or replace the headset.|
|All apps|Test to see whether the issue happens only when using Walkie Talkie or if it happens across all apps. Try to reproduce the issue in other apps. For example, test using the Calls app or Meeting app within Teams, and with apps outside of Teams.|If the issue can be reproduced in other apps, investigate possible hardware or software issues that might be impacting device.|
|Walkie Talkie app| Check whether the issue occurs for all people in a channel, several people, or only one person.|If possible, first try to [update Teams](https://support.microsoft.com/office/update-microsoft-teams-535a8e4b-45f0-4f6c-8b3d-91bca7a51db1#ID0EBBD=Mobile) to the latest version. If the issue persists, [send logs to Microsoft for investigation](#send-logs-to-microsoft-for-investigation) and include the number of people who are experiencing the issue. If possible, include a video that shows the steps to reproduce the issue.|

## Troubleshoot common issues

### Incoming transmissions not received

If a user hears an audio tone or a notification that a transmission is incoming but they don't receive the transmission, ask the user to try the following steps:

1. Make sure the audio volume is set to at least 50 percent and the headset is connected properly.
1. [Run the network test in Walkie Talkie](#run-the-network-test-in-walkie-talkie) to make sure they have a good network connection.
1. Disconnect and reconnect to the Walkie Talkie channel.

If the issue persists, [send logs to Microsoft for investigation](#send-logs-to-microsoft-for-investigation).

### Missing transmissions

If users experience issues in which they're not receiving transmissions, try the following steps:

1. Check the participant list to verify that both the sender and receiver are connected to the same Walkie Talkie channel.
1. [Run the network test in Walkie Talkie](#run-the-network-test-in-walkie-talkie) to make sure they have a good network connection.
1. Disconnect and reconnect to the channel.
1. Restart Teams to refresh the connection.
1. Check whether the user's status is set to **Do not disturb**, in focus time, or in quiet time in Teams on the device. These modes might block transmissions.

    If the user is in any of these modes, have the user switch out of that mode. Make sure that notifications are turned on, and then restart Teams to ensure that any changes to notification settings take effect.

### Participants list for a Walkie Talkie channel is inaccurate

The participants list is the list of users who are actively connected to a Walkie Talkie channel and can potentially hear transmissions. Sometimes this list can become inaccurate. For example, a user doesn't appear in the list even though they're connected to the channel. This issue can sometimes occur because of network issues or when a user's status is set to **Do not disturb**.

If the participants list in a channel doesn't accurately reflect the users who are actively connected to the channel, ask the users who aren't appearing on the list to try the following steps:

1. Disconnect and reconnect to the Walkie Talkie channel.
1. Switch channels.
1. Send at least two transmissions. This action can potentially add the user back to the participants list.
1. Close, and then reopen Walkie Talkie (if on an iOS device).

### Network connectivity issues

Poor network connectivity can lead to interruptions, delays, or loss of communication.

#### Run the network test in Walkie Talkie

To check the network connection, ask users to run the network test in Walkie Talkie. Have them go to their profile picture in Teams, and then tap **Settings** > **Walkie Talkie** > **Test Network Quality**.

The following network conditions are required for an optimal experience. To learn more, see [Manage the Walkie Talkie app in Teams](walkie-talkie.md#network-considerations).

|Metric |Values| More information|
|---|---|---|
|Latency|< 300 ms|Latency is measured in round trip time (RTT). If latency is high, connecting to Walkie Talkie takes longer, and jitter is also higher. Latency > 500 ms indicates poor network quality.|
|Jitter |< 30 ms |If jitter is high, users will hear crackling sounds or audio breaking up.|

Here's an example of network test results that indicate a poor connection.

:::image type="content" source="media/walkie-talkie-troubleshooting-network-test.png" alt-text="Screenshot of the network test page in Walkie Talkie." lightbox="media/walkie-talkie-troubleshooting-network-test.png":::

#### Troubleshoot network connection issues

If results of the network quality test indicate a poor connection, have the user try the following steps:

- Move to an area with better network coverage.
- Switch between WiFi and cellular data to determine which provides a more stable connection.
- Close any other apps that might be using network bandwidth.
- Restart the device to reset the network connection.

### Device issues

To troubleshoot device issues:

- Make sure the device has the latest possible firmware update installed.
- Check that the device has adequate battery life and isn't overheating.
- Update the device operating system to the latest version.
- Reset the device settings to use the default settings, if persistent issues occur.
- If possible, [update Teams](https://support.microsoft.com/office/update-microsoft-teams-535a8e4b-45f0-4f6c-8b3d-91bca7a51db1#ID0EBBD=Mobile) to the latest version.

### Headset issues

Malfunctioning or incompatible headsets can cause poor audio quality or connectivity issues. To troubleshoot headset issues:

- Examine the headset for any physical damage or connectivity issues.
- Make sure the microphone and speaker are clean and unobstructed.
- Make sure the headset is properly connected to the device.
- Make sure wireless headsets are fully charged.
- Check whether the headset has noise cancellation and voice isolation capabilities.
- Test the headset with another app to see if the issue persists.

Additionally, try adjusting the audio settings in Walkie Talkie to improve sound quality.

### Permissions issues

Make sure Teams has permissions to access the microphone, network, and notifications on the device.

1. Go to Settings on the device and check whether Teams has access to the microphone, network, and notifications.
1. Grant access to Teams to the items in step 1 for which Teams doesn't already have access.
1. Restart Teams.
1. If permissions issues continue to occur, reinstall Teams on the device.

### Walkie Talkie not appearing in Teams

#### Make sure Walkie Talkie is pinned to Teams

To access Walkie Talkie in Teams, Walkie Talkie must be pinned to the app bar in Teams. The pinning behavior of Walkie Talkie depends on the license users have.

##### Microsoft 365 F license

For users with a Microsoft 365 F license, Walkie Talkie is pinned to Teams by default through the [tailored frontline app experience](/microsoft-365/frontline/pin-teams-apps-based-on-license). Users can see and access Walkie Talkie in Teams without any action needed by an admin.

##### Microsoft 365 E license

For users with a Microsoft 365 E license, you must use an app setup policy to pin Walkie Talkie to Teams. Users won't see Walkie Talkie in Teams until they're assigned an app setup policy that includes Walkie Talkie as a pinned app. If you're pinning more than 10 apps, Walkie Talkie must be added to one of the first 10 apps in the list when you set up the policy.

You manage app setup policies in the Teams admin center. You can edit the global (Org-wide default) policy or create and assign a custom policy to users. To learn more, see [Use app setup policies to pin and install apps for users](teams-app-setup-policies.md).

> [!NOTE]
> If users with a E license are enabled for Teams [public preview](public-preview-doc-updates.md) or Teams private preview, Walkie Talkie is pinned to Teams by default. Users can see and access Walkie Talkie in Teams without needing an app setup policy assigned to them to pin the app.

###### Check the app setup policy assigned to a user

If users with an E license don't see Walkie Talkie in Teams, check the app setup policy assigned to them.

1. In the left navigation of the Teams admin center, go to **Users** > **Manage users**, and then search for the user.
1. Select the user, and then go to the **Policies** tab.
1. Next to **App setup policy**, select the policy, and then make sure that Walkie Talkie is added as one of the first 10 apps in the **Pinned apps** list.

More policy troubleshooting:

- Currently, Walkie Talkie must be added as a pinned app and doesn't support being added as an "installed app" in the app setup policy.
- Assigning only an app permission policy isn't sufficient. You must also assign an app setup policy to pin Walkie Talkie to Teams for users who have an E license.

#### Walkie Talkie not appearing even though it's pinned to Teams

If a user doesn't see Walkie Talkie even though it's pinned to Teams, have them try the following steps:

1. In the Teams app bar at the bottom of the screen, tap **More ...**, find and then tap **Walkie Talkie** to open it.
1. If Walkie Talkie still isn't showing up, restart Teams.

### Proxy servers

Using a proxy server with Walkie Talkie isn't recommended.

Performance-related issues can be introduced to the environment through latency and packet loss by attempting to route Teams traffic through a proxy server. These issues can occur if the proxy is unable to handle the amount of traffic passing through it, or incorrectly routes traffic to a Microsoft network service front door location that's further away from users.

However, if you need to use a proxy server, make sure it's set up correctly. To learn more, see:

- [Proxy servers for Teams](proxy-servers-for-skype-for-business-online.md)
- [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

## Send logs to Microsoft for investigation

If users are still experiencing issues, they can send us a feedback report about the issue in Teams, and [attach logs](https://support.microsoft.com/topic/86dea1fe-ba14-456a-a7b9-b76c48011316) in the feedback report.

> [!NOTE]
> For users to attach logs, you must enable the option in the Teams feedback policy. To learn more, see [Manage feedback policies in Teams](manage-feedback-policies-in-teams.md).

Ask users to reproduce the issue. In the feedback report, mention "Walkie Talkie", include a detailed description of the issue they're experiencing, and choose the option to attach logs.

Users can send us feedback using either the following options:

- Shake and send. This feature must be enabled at the tenant level in Teams.
- **Send feedback**. The default feedback option. In Teams, tap the profile picture, and then tap **Settings** > **Help & feedback** > **Send feedback**. To learn more, see [Give feedback in Teams](https://support.microsoft.com/office/give-feedback-in-microsoft-teams-c0fb6297-22af-4db5-b19b-69e0a6720927#ID0EBBD=Android).

> [!NOTE]
> If you're in direct contact with Microsoft, include the number of people who are experiencing the issue. If possible, include a video that shows the steps to reproduce the issue.

## Known limitations

- Walkie Talkie doesn't support switching channels from the device lock screen. If users are using the **Listen to multiple channels** feature in Walkie Talkie and selected multiple channels, they can hear activity across all their selected channels. When the phone is locked, users can send transmissions only on their active channel. If a user needs to switch channels, they can do so from within Walkie Talkie.

- Audio static:
  - iOS devices: Walkie Talkie doesn't support noise cancellation or voice isolation. Users might hear some background noise during communications.
  - Android devices: If the user's device supports noise cancellation, they can turn it on in Walkie Talkie settings.

- The Walkie Talkie app isn't supported on Teams desktop. It's available on Teams mobile on Android and iOS devices.

## Related articles

[Manage the Walkie Talkie app in Microsoft Teams](walkie-talkie.md)