---
title:  Uninstallation script for the classic Teams client
ms.author: heidip
author: MicrosoftHeidi
manager: jtremper
ms.topic: article
ms.date: 11/12/2024
ms.service: msteams
audience: admin
ms.collection: 
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: asgupta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Documenting for a downloadable uninstall script for the classic Teams client which allows you to manually shut off and remove the classic Teams client after moving to the new Teams client on non-VDI devices.
appliesto: 
- Microsoft Teams
ms.localizationpriority: medium
---

# Uninstall the classic Teams client using a script

Microsoft has an [uninstallation script](https://download.microsoft.com/download/d/f/c/dfc1a7ce-e3da-4e12-94fc-bea60ba3d9ba/UninstallClassicTeams.ps1) designed to uninstall the classic Teams client from all user profiles found on devices in your organization. This script can be run on all devices apart from Virtualized Desktop Infrastructure (VDI). If the classic Teams client is running for any user on the machine at the time the script is run, this script also ends the existing classic Teams running instance.

## Using the script

### Running the script on a single device

If you want to have the uninstallation script run for a single device, run it on that device [in administrative mode](/powershell/scripting/learn/ps101/01-getting-started#how-to-launch-powershell). After you run the script, the classic Teams client is uninstalled from all user profiles of the specified device.

## Running the script with device management software

If you need to have this uninstallation script run across all devices in your organization, run this script using device management software, like Intune. We have [sample instructions](https://github.com/microsoft/MDE-PowerBI-Templates/blob/master/ASR_scripts/AddShortcuts_with_Intune.md) for running the script in Intune.

If the script is run in Intune or other device management software:

- Admins get results in the form of .JSON that indicates different parameters, like how many instances of classic Teams there are, how many have been uninstalled from devices, and so on.
- Admins can download these results as a .CSV file.

> [!NOTE]
> After the uninstallation of classic Teams, new Teams and Teams meeting add-in (TMA) might not work together. See [this article](/microsoftteams/troubleshoot/meetings/teams-meeting-add-in-missing#cause) for more information.

### Teams meeting add-in issue resolution

To address the TMA issue when it does occur, Microsoft has [an additional script](https://download.microsoft.com/download/d/f/c/dfc1a7ce-e3da-4e12-94fc-bea60ba3d9ba/DetectAndUninstallTMA.ps1) to resolve the issue.

> [!NOTE]
> If the new Teams client is running and the TMA issue is detected by this script, it can't fix the issue. If you need to have this TMA script run across all devices in your organization in user context, please refer to these [sample instructions](https://github.com/microsoft/MDE-PowerBI-Templates/blob/master/ASR_scripts/AddShortcuts_with_Intune.md) for running the script in Intune. (User context can be selected by setting **Run this script using the logged-on credentials** to **Yes**.)
