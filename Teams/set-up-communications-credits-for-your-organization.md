---
title: Set up Communication Credits for your organization
ms.author: danismith
author: DaniEASmith
manager: jtremper
ms.reviewer: dachocro
ms.date: 11/18/2024
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: 
  - M365-voice
  - m365initiative-voice
  - highpri
  - Tier1
audience: Admin
appliesto: 
  - Skype for Business
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom: 
  - Licensing
  - admindeeplinkMAC
  - admindeeplinkTEAMS
description: Learn how to set up Communication Credits licenses for your users and organization.
---

# Set up Communication Credits for your organization

Set up Communication Credits for your **Microsoft Teams Calling Plan** (Domestic, International, or Pay-As-You-Go) and **Audio Conferencing** users who need to dial out to **any destination**.

When you sign up for Calling Plans and/or Audio Conferencing, you get some minutes depending on your country/region. For more information, see [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization).

If you don't set up Communication Credits, and your organization runs out of minutes, users won't be able to make calls or dial out from Audio Conferencing meetings. Learn more at [What are Communication Credits?](what-are-communications-credits.md)
  
For more information about plans and pricing, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523).

> [!IMPORTANT]
> Microsoft Customer Agreement (MCA) customers don't need to purchase Communication Credits. Instead, MCA customers need to turn of Communication Credits automatic recharge. For instructions on how to turn off Communication Credits auto recharge, see [Turn off Communication Credits auto recharge for Microsoft MCA customers](turn-off-communication-credits-auto-recharge-mca-customers.md).

To set up Communication Credits for your organization, follow these steps:

1. [Assign an Audio Conferencing and/or Teams Calling Plan license to your users](#step-1-assign-an-audio-conferencing-andor-a-teams-calling-plan-license-to-your-users).
2. [Set up Communication Credits for your organization](#step-2-set-up-communication-credits-for-your-organization).
3. [Assign Communication Credits licenses to users](#step-3-assign-communication-credits-licenses-to-users).

You can update your payment options at any time. On the **Billing** > **Your products** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Communication Credits** and make your updates.

## Step 1: Assign an Audio Conferencing and/or a Teams Calling Plan license to your users
  
Communication Credits are enabled for users who have either an **Audio Conferencing** license or **Teams Calling Plan** license.
  
- Assign an **Audio Conferencing** license to your users. See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

  After you assign this license, you need to set up Audio Conferencing. For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).

- Assign **Teams Phone** licenses and a **Domestic**, **International**, or **Pay-As-You-Go** Calling Plan license to your users. See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
  After you assign these licenses, you need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).
  
## Step 2: Set up Communication Credits for your organization

1. Sign in to [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) using your admin credentials.
1. In the left navigation menu, go to **Marketplace** > **All products**.
1. Search for **Communication Credits**.
1. Select the **Details** button under **Communication Credits** to add funds.
    1. You can add funds manually at any time.
    1. Funding Communication Credits also adds **Communication Credits** licenses to your tenant to assign to users.
1. Fill in your billing details.
1. Select the **Apply auto-recharge** hyperlink.
1. On the **Auto-recharge settings** pane, check the **Auto-recharge settings** box.
1. Choose your auto-recharge options:
   - **Add this amount**: Enter the amount to add to your account when the auto-recharge happens.
   - **When balance is below**: Enter in the amount that *triggers* the auto recharge. Once your balance falls below this amount, the recharge amount is added automatically to your account.
1. Select the **Save** button.
1. Double check all of your billing information and subscription options.
1. Select the **Place order** button.

### Considerations when setting up Communication Credits

- Funds apply only to Communication Credits at Microsoft published rates when the services are used. Any funds not used within *12 months* of the purchase date expire and are forfeited.

- When using the auto-recharge function, invoicing for Communication Credits is generated when the trigger amount is reached and a recharge transaction is processed. Communication credit amounts are used in a first-in, first-out manner.

## Step 3: Assign Communication Credits licenses to users

If you don't assign **Communication Credits** licenses to your users, those users can't make calls or dial out from Audio conferencing meetings.

A large amount of **Communication Credits** licenses are automatically added to your tenant when funding your Communication Credits balance, which you can then assign to users.

Assign a Communication Credits license to each user by following these steps, even to users assigned an **Microsoft 365 E5** plan:

1. Sign into the [**Microsoft 365 admin center**](https://go.microsoft.com/fwlink/p/?linkid=2024339) using your admin credentials.
1. In the left navigation menu, select **Users** > **Active Users**.
1. Select a user's name from the list.
1. Select the **Licenses and apps** tab.
1. Check the **Communication Credits** license checkbox.
1. Select the **Save changes** button.

Also, you can use [PowerShell](/powershell/module/teams/) to assign licenses to multiple users in bulk.

## Related articles

- [What are Communication Credits?](what-are-communications-credits.md)
- [Turn off Communication Credits auto recharge for Microsoft MCA customers](turn-off-communication-credits-auto-recharge-mca-customers.md).
- [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
- [Set up Calling Plans](set-up-calling-plans.md).
- [Calling Plans for Microsoft 365](calling-plans-for-office-365.md).
