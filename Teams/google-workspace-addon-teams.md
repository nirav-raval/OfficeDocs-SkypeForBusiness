---
title: Set up Microsoft Teams meeting add-on for Google Workspace
ms.author: wlibebe
author: wlibebe
ms.reviewer: jason.hochstadt
ms.date: 10/31/2024
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
  - Microsoft Teams
search.appverid: MET150
description: Learn how to Set up Microsoft Teams meeting add-on for Google Workspace.
ms.localizationpriority: medium
ms.custom:
  - has-azure-ad-ps-ref
  - azure-ad-ref-level-one-done
f1.keywords:
- NOCSH
ms.collection: 
  - M365-collaboration
  - m365initiative-meetings
appliesto: 
  - Microsoft Teams
---

# Set up Microsoft Teams meeting add-on for Google Workspace

The Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace. These get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.

The Microsoft Teams meeting add-on for Google Workspace is on by default. To learn about how your users use the Microsoft Teams meeting add-on for Google Workspace, see [Install the Microsoft Teams meeting add-on for Google Workspace](https://support.microsoft.com/office/install-the-microsoft-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60).

## Turn the Microsoft Teams meeting add-on for Google Workspace on or off in the Azure portal

As an admin, you can turn the Microsoft Teams meeting add-on for Google Workspace on or off using the Azure portal.

1. Sign in to the Azure portal.
2. Select **Enterprise applications** > **All applications**.
3. Search for **Microsoft Teams meeting add-on for Google Workspace**.

   ![Azure portal showing all applications.](media/aad-add-google-workspace.png)

4. Select **Yes**.

   ![Azure portal showing the google workspace properties.](media/google-workspace-properties.png)

5. (Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.

## Turn the Microsoft Teams meeting add-on for Google Workspace off using PowerShell

```powershell
Connect-MgGraph -Scopes "Application.ReadWrite.All"

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'
```

## Check if a service principal already exists for the app

```powershell
$ServicePrincipalUpdate =@{
  "accountEnabled" = "false"
}

$servicePrincipal = Get-MgServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Update-MgServicePrincipal -ServicePrincipalId $servicePrincipal.Id -BodyParameter $ServicePrincipalUpdate
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    $servicePrincipal = New-MgServicePrincipal -AppId $appId -DisplayName $displayName
    Update-MgServicePrincipal -ServicePrincipalId $servicePrincipal.Id -BodyParameter $ServicePrincipalUpdate
    Write-Host "Created and disabled the Service Principal \n"
}
```

For more information, see [Create a service principal with Microsoft Graph PowerShell](/powershell/module/microsoft.graph.applications/new-mgserviceprincipal).

## Delete the Microsoft Teams meeting add-on for Google Workspace

See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.

## Create the Microsoft Teams meeting add-on for Google Workspace using PowerShell

In case the Microsoft Teams meeting add-on isn't present in your tenant, you can create it using PowerShell:

```powershell
Connect-MgGraph -Scopes "Application.ReadWrite.All"

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-MgServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-MgServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```

## Related topics

- [Plan for Teams meetings](plan-meetings.md)
