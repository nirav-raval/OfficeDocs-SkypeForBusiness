---
title: Turn off Teams Native File Upload policy
author: danieasmith
ms.author: danismith
manager: jtremper
ms.topic: article
ms.service: msteams
ms.reviewer: 
ms.date: 11/12/2024
search.appverid: 
description: Learn how to create, set, assign, and adjust the Teams Files Policy using PowerShell.
audience: admin
ms.localizationpriority: medium
appliesto: 
  - Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection: 
  - M365-collaboration
---

# Turn off Teams Native File Upload policy

Microsoft Teams uses OneDrive and SharePoint to store and share content, but some organizations and users might prefer to use third-party storage providers.  

If your organization chooses a third party for content storage, you need to turn off the `NativeFileEntryPoints` parameter in the Teams Files policy. This parameter is enabled by default, which shows the option to upload content from OneDrive or SharePoint to Teams chats or channels.

This article helps you create, set, assign, and remove the `NativeFileEntryPoints` parameter using PowerShell.

> [!NOTE]
> When the Teams Files policy is turned off, users don't see access points for OneDrive and SharePoint in Teams. However, the creation of new teams and channels continue to trigger the generation of matching SharePoint libraries. The **OneDrive app** in the left navigation pane in Teams isn't affected by the Files policy being turned off.

## Prepare to update the Teams Files policy

### Set up Microsoft PowerShell

Currently, this policy can't be changed in the Teams admin center. Your organization's tenant administrator has to make the changes using the PowerShell cmdlets detailed later in this article.

- To learn how to install the PowerShell Teams module using PowerShell Gallery, see [Install Microsoft Teams PowerShell Module](teams-powershell-install.md).
- To install or download the Teams PowerShell module, see [PowerShell Gallery for Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).
- For more information on how to set up PowerShell for Teams management, see [Manage Teams with Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### Allow third-party apps in Teams admin center

This step isn't required to change the Teams Files policy, but it's required when you're ready to integrate your third-party storage provider in your users' Teams experience.

Your tenant administrator needs to enable the *Allow third-party apps* policy in the Teams admin center.

To learn how to allow third-party or custom apps, see *Manage org-wide apps settings* in [Manage your apps in the Microsoft Teams admin center](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## Turn off `NativeFileEntryPoints` for your entire tenant

Setting the `-Identity` parameter to `Global` applies the policy settings to all users in your organization.

### Sample PowerShell policy cmdlet for entire tenant

The following sample PowerShell command sets the `NativeFileEntryPoints` parameter to `Disabled` for your entire tenant:

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### Check the status of your tenant  

To view the current status of your tenant's Teams Files policy, use the `Get-CsTeamsFilesPolicy` cmdlet.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### Turn on or turn off native file upload point

To turn on or turn off the native file upload point for your entire tenant, set the `NativeFileEntryPoints` parameter to either `Enabled` or `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### Remove the policy for your users

To remove the Teams Files policy for your users, use the `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## Turn off NativeFileEntryPoints for specific users

You can also update the Teams Files policy for specific users by creating a new Teams Files policy `-Identity` string and assigning the newly created policy to users.

### Sample PowerShell policy cmdlet for specific users

This sample PowerShell command creates a new `CsTeamsFilesPolicy` with the `-Identity` named as `UserPolicy` and the `NativeFileEntryPoints` parameter set to `Disabled`.

When a user is assigned the `CsTeamsFilesPolicy` with `-Identity UserPolicy`, their native file entry points are turned off.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### Assign a policy to user

Once you create the new policy, you can assign that policy to users using the `Grant-CsTeamsFilesPolicy` cmdlet.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### Update the policy

If you need to change the setting of the new Teams Files Policy `UserPolicy`, use the `Set-CsTeamsFilePolicy` cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### Remove the policy for the complete list of users

To remove the policy from all users assigned to the Teams Files policy `UserPolicy`, use the `Remove-CsTeamsFilesPolicy` cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```

>[!NOTE]
> Once you've made changes to the policy, allow up to 12 hours for the changes to show in users' Teams clients.
