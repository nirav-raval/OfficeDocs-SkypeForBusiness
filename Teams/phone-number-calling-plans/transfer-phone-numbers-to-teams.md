---
title: Transfer phone numbers to Microsoft Teams
author: sfrancis206
ms.author: scottfrancis
manager: pamgreen
ms.reviewer: leiaglezer
ms.date: 11/22/2024
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection: 
  - M365-voice
  - m365initiative-voice
  - highpri
  - Tier1
appliesto: 
  - Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Learn how to use the porting wizard to transfer your phone number from your current service provider to Microsoft Teams.
ms.custom: seo-marvel-mar2020
---

# Transfer phone numbers to Microsoft Teams

This article is for administrators and IT professionals porting their phone numbers from their current service provider into Microsoft Teams Calling Plans in the Teams Admin Center (TAC). Once completed, Microsoft becomes your Public Switched Telephone Network (PSTN) service provider.

Before you start, review prerequisite knowledge referenced in the following articles:

- [What's a port order](port-order-overview.md)
- [How many phone numbers can you get?](../how-many-phone-numbers-can-you-get.md)
- [Country or region specific articles](../manage-phone-numbers.md).

> [!NOTE]
> If you have more than 999 phone numbers that you need to transfer to Teams in one port request, don't use the port wizard. Navigate to the [Phone Number Service Center portal](https://pstnsd.powerappsportals.com/create-ticket/) and create/submit a new "Port in" case with the [Telephone Number Services (TNS) - Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

Microsoft's Telephone Number Service Center completes ports orders only on United States business days and not on public holidays or weekends.

## Create a port order and transfer your phone numbers to Teams

1. In the Teams admin center, launch the port wizard:
   - In the left navigation rail, go to **Voice** > **Phone numbers**.
   - Select the **Numbers** tab, and then from the table's header menu, select **Port**.

### Get started

On the **Get started** page, populate the fields as per your request.

- **Country or region**: Specify the country or region where you're porting numbers.
- **List your phone number**: Add your phone numbers manually or by uploading a list.

    - **To add phone numbers manually**: Enter numbers in E.164 format, separated by a comma or semicolon. Ranges are not supported. Optional dashes or hyphens are allowed.
    - **To upload a list of phone numbers**: Use a CSV file with one column labeled **PhoneNumber**. Each row should contain a single phone number in E.164 format.

### Manage numbers

The **Manage numbers** page checks that the number format is correct, matches the specified country or region, and is valid before proceeding.

If the number validation summary isn't successful, view the details to understand the reason.

- Select **View details** in the number validation summary pane, or select the phone number validation failure below **Validation status** to check the reasons for phone number failure.

- If failure isn't understood, you may create a case with the TNS-Service Desk team through the [Phone Number Service Center portal](https://pstnsd.powerappsportals.com/create-ticket/).
    - For the scenario where you don't understand the number validation result, select **Case Type = General Inquiry** and in the description, provide the number validation summary that you see in TAC along with the list of phone numbers that you're trying to port.

The number validation summary must indicate all numbers are valid before you can proceed. If there are no errors, continue.

### Add account information

On the **Add account information** page, complete the following, and then select **Next**.

> [!NOTE]
> The information displayed on this page is determined by the country or region and number type. Each country and region has different regulations on the information that's required to port numbers. What you see on this page may be different from what's described here.

1. **Order details**: Input required name for your port request. The order name you specify here becomes viewable by you in the Teams Admin Center during the porting process and after order completion for your records.

2. **Port details**: Enter the Billing Telephone Number (BTN) in E.164 format.

    - If you enter a BTN number that isn't in the list of numbers that you're porting, your request is automatically categorized as a **Partial port** and the BTN will remain with your current service provider after the port is complete.
    - If you enter a BTN number that matches a number in the list of numbers that you're porting, you have two options.

        - **Option 1**: Port **all numbers in my account**. If you choose this option, the account with your current service provider will be closed after the port is complete.
        - **Option 2**: Port **some numbers in my account, and I'm including my account's BTN**. If you choose this partial port option, you also have the option to enter a new BTN to designate for the account that is still open with your current service provider. Designating a replacement BTN is optional.

> [!NOTE]
> All information input for your organization and current service provider must match *exactly* with the current service provider's records.
>
> Some fields are optional, but some service providers require the optional fields.

3. **Organization details**: Enter your organization's name.

4. **Current service provider details**: Provide the current service provider's name, account number, and security PIN. The account PIN is required to port mobile numbers.

5. **Requester details**: Populate this information with the contact details of the person who Microsoft can contact with port order status updates.

6. **Authorized user details**: Populate this information with the contact details of the person who is the authorized user with your current service provider.

7. **How do you want to sign the Letter of Authorization?**: Select whether you want e-signature or manual upload for the Letter of Authorization.

8. **Service address**: Enter the service address exactly as it matches the current service provider's record. Emergency addresses can be assigned later, when assigning the number to a user.

9. **Default number usage**: Select the intended type of usage for the numbers. If you would like to change it, select *Yes, change usages* to go to the **Add number features** page. If you select *No*, the wizard skips you to the **Complete your order** page.

### Add number features

The add number features page is where you update the number usage. Usage is a category of service for the phone numbers.

- For numbers assigned to users, the default number type is geographic phone numbers and is listed as **User**.

- For numbers assigned to voice applications, such as Auto-Attendants and Call Queues, the number usage type should be set as **Voice app**.

- For numbers assigned to audio conferencing, the number usage type should be set to **Conference**.

Toll-free numbers default to **Voice app**, but you can make changes to the default number usages in this section of the wizard.

To update the number usage, check the desired number and select **Update number usage**. Then, from the right-hand side rail, use the drop-down and select your desired number usage to assign to the numbers.

### Complete your order

- If you selected **Paper signature** in the **Add account information** page, you can download a Letter of Authorization template.

    - The template is prepopulated with the information you input in the wizard.
    - Once signed, you upload a copy of the signed Letter of Authorization and then you can select **Submit** and the port request proceeds.

- If you selected **E-signature** in the **Add account information** page, the authorized user receives an email to sign the Letter of Authorization once you select **Complete and send e-signature request**.

    - Once they electronically sign, the port request proceeds.

## What happens next

When we receive your port order, you receive an automated email that confirms your request. All port order status changes generate automated email notifications to you about the order. If your port request is rejected by the carrier, if you need help with your port request, or if you have any questions about your port request, contact the [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) for assistance.

> [!NOTE]
> If you already have a case open with the TNS-Service Desk for your port request, update that existing ticket instead of creating a new case.

To view the status of your port order, in the left navigation of TAC, go to  **Voice** > **Port orders**, and then select **Order history**. Each port order status is listed in the **Status** column. To learn more, see [What's the status of your port orders?](port-order-status.md)

## Report phone number issues

If you notice any issues with the ported numbers within the first 24-48 hours after the port is completed, contact the [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md). For any issues beyond 48 hours, follow normal Microsoft Support process.

## Related articles

- [What's a port order?](port-order-overview.md)
- [Different kinds of phone numbers used for Calling Plans](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Emergency calling terms and conditions](../emergency-calling-terms-and-conditions.md)
- [Emergency Calling disclaimer label](https://download.microsoft.com/download/9/9/0/990e24c1-eb49-4b52-9306-dbd4c864ed91/emergency-calling-label-(en-us)-(v.1.0).zip)
