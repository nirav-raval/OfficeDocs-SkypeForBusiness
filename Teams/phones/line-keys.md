---
title: Manage line keys for speed dial on Teams phones
author: mstonysmith
ms.author: tonysmit
manager: pamgreen
ms.reviewer: prashibadkur
ms.date: 11/04/2024
ms.topic: article
audience: Admin
appliesto:
- Microsoft Teams
ms.service: msteams
ms.subservice: itpro-devices
ms.collection:
  - teams-rooms-devices
  - Teams_ITAdmin_Devices
  - Tier1
f1.keywords:
  - NOCSH
search.appverid: MET150
ms.localizationpriority: medium
description: Learn how to set up and manage line or speed dial keys on Microsoft Teams certified phones for quick access to custom contacts and speed dial.
---

# Line or speed dial keys on Microsoft Teams certified phones

This article provides you with guidance on setting up and managing line keys (or speed dial keys) on Microsoft Teams certified phones. This feature allows your users to use a phone line key to set up speed dial for their contacts and phone numbers for quick access using buttons on nontouch devices and sidecars.

> [!IMPORTANT]
> This feature is only available on non touch Teams phones and not on touch-enabled Teams phones.

A phone line key is one of the keys used to designate individual lines on a phone. Depending on the model and manufacturer, phones typically have between 2 and 12 phone line keys.

## Steps to use line keys to set up speed dial

To set up a line key for speed dial, follow these steps:

1. **Update the Teams phone to version 1449/1.0.94.2024101709**. After updating the phone, you notice a new home screen experience on your device with a dedicated place for your line keys. To update your Teams phones, see [Update your phones remotely](remote-update-teams-phones.md).  Verify that you're running Android version 1449/1.0.94.2024101709.

    You can see the versioning information in the Teams admin center or on the Teams phone.

    To see it in the Teams admin center:

    1. Sign in to the Teams admin center.
    2. Go to **Teams devices** > **Phones** > then select the phone you want to look at.
    3. Then in the table under **Software type** look for **Teams** and in the **Current version** column you can see the version.

       To see the versioning information on the Teams phone itself: Go to the **Profile** icon > **Settings** > **About**.

       > [!IMPORTANT]
       > With this update, you can use line keys to set up speed dial for contacts and phone numbers only.

       > [!NOTE]
       > With this update, line keys are available for nontouch Teams phone and Teams phones with sidecars.

2. **To assign a contact for speed dial:** Select on **Assign line key** and search for an existing contact including with an external phone number, or add a new one.

    - When you first start to assign line keys, you see:

      :::image type="content" source="./media/nontouch-line-keys-empty.jpg" alt-text="Screenshot of a non touch phone with line keys."

    - Find an available line key for you to use, and select **Assign line key**.
  
      :::image type="content" source="./media/nontouch-line-keys-assign.jpg" alt-text="Screenshot of an available line key on a Teams phone."
  
    - Press and hold on a line key to assign a contact or phone number:

      :::image type="content" source="./media/nontouch-line-keys-help.jpg" alt-text="Screenshot of how to long press a line key to set it up."

    - After you assign a contact or phone number to the line key, you'll see:
  
      :::image type="content" source="./media/nontouch-line-keys-assigned.jpg" alt-text="Screenshot of how to long press a line key that is assigned."

3. **To modify or manage an assigned line key:** Long press an existing line key to see a detailed menu with the following options:

     :::image type="content" source="./media/nontouch-line-keys-manage.jpg" alt-text="Screenshot of line key management options."

    - **Unassign line key:** - Use this setting to remove an assigned line key.
    - **Reassign line key:** - Use this setting to modify the contact assigned to this line key.
    - **Manage line key:** - Use this setting to access more management options.
  
4. **To place a call:** Press or select on the key to place a call to the user or number assigned to that line key.

## Frequently Asked Questions

**Question:**   When will line keys be supported on touch Teams phones?  
**Answer:**  Support for touch Teams phone is coming soon. Check the public roadmap for timelines, see [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=In%20development%2CLaunched%2CRolling%20out%2CMicrosoft%20Teams).

**Question:**  Can line keys be configured on the Teams Admin Center with this update?  

**Answer:**  No, currently configuration support is only on the Teams phone.

**Question:**  What other functions can I perform using line keys?  

**Answer:**  With this update, you can use line keys for quick access to speed dial only. In the future, we support line keys for call controls and offer enhancements for shared line configuration.

**Question:**  Does this change the existing functionality of sidecars?  

**Answer:**  Before the Teams application update to 1449/1.0.94.2024101709, users were able to add contacts to sidecars if the account was marked as a Favorite, speed dial, or assigned as a Boss. Additionally, users could pin groups to sidecars. With this update, contacts on sidecars can only be added by configuring them as line keys on the sidecar. Saved configurations continue to appear on the sidecar with this app. We'll make changes to streamline this experience on sidecars in the future.

### Related articles

- [Microsoft Certified Teams phones](../devices/teams-phones-certified-hardware.md)
- [Phones for Microsoft Teams](phones-for-teams.md)
