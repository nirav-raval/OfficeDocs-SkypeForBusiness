---
title: Turn off Communication Credits auto recharge for Microsoft MCA Customers
ms.author: danismith
author: DaniEASmith
manager: jtremper
ms.reviewer: dachocro
ms.date: 11/18/2024
ms.topic: article
ms.assetid: 691c9301-1f66-41fe-9b2c-ca24ae987463
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
  - M365-voice
  - m365initiative-voice
  - highpri
  - Tier1
appliesto: 
  - Skype for Business
  - Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
 - CSH
ms.custom:
  - Licensing
  - admindeeplinkMAC
description: Learn how to turn off Communication Credits automatic recharge if you're a Microsoft Customer Agreement (MCA) customer.
---

# Turn off Communication Credits auto recharge for Microsoft Customer Agreement (MCA) customers

Microsoft Customer Agreements (MCA) allow customers to pay for services *after* the services were consumed, also known as post-usage billing.

Because Communication Credits are a prepaid budget to support outgoing minutes, they're not available to purchase for customers with MCA Calling and Audio Conferencing subscriptions.

- For more information about the types of billing accounts, see [Understand your Microsoft business billing account](/microsoft-365/commerce/manage-billing-accounts).
- To learn how to check if your tenant has an MCA calling subscription, see [View my billing accounts](/microsoft-365/commerce/manage-billing-accounts#view-my-billing-accounts).

Most customers not using an MCA have the *Automatic Top Up* (ATU) flag enabled within their account. The ATU flag automatically refills your Communication Credit balance to the threshold you selected. **MCA customers need to turn this setting off.**

## How to turn off the auto-recharge setting

When switching to an MCA, you need to disable this ATU option. Otherwise, the Communication Credit balance indefinitely refills itself, and the commerce system doesn't switch to the post-usage mechanism under an MCA.

If you're moving to an MCA subscription, turn off automatic recharge by completing the following steps:

1. Sign into the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339) with your admin credentials.
1. In the left navigation menu, navigate to and select **Your products**.
1. Select **Communication Credits** in your listed products.
1. On the **Communication Credits** page, find the section titled **Billing settings** and select **Edit auto recharge settings**.
1. On the **Auto-recharge settings** page, uncheck the box next to **Auto recharge**.
1. Select the **Save** button.

When this process is complete, you can transition to an MCA before your Communication Credit balance is empty. Even as an MCA customer, the commerce system consumes your Communication Credit balance before changing to post-usage billing. There's no extra action needed by you to ensure this switch happens.

## Related articles

- [What are Communication Credits?](what-are-communications-credits.md)
- [Set up Communication Credits for your organization](set-up-communications-credits-for-your-organization.md).
