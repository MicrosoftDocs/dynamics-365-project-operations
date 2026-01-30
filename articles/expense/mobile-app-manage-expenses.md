---
title: Manage expenses by using the Dynamics 365 expense management mobile app
description: Learn how to manage expenses efficiently using the Dynamics 365 expense management mobile app. Discover features like OCR for receipts and policy violation tracking.
author: mukumarm
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# Manage expenses by using the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

This article explains how to manage expenses by using the Dynamics 365 expense management mobile app.

## Default settings for expense creation and updates

When you create or update an expense, the app automatically sets specific values based on predetermined settings or configurations:

* The app defaults the setting for **Include tax** to **Yes**. However, you can override the default setting and set **Include tax** to **No**.
* The app sets the **item sales tax group** based on the **expense category**.
* The app sets the **sales tax group** based on the following **priority order**: **project, country/region, and vendor mapped with employee**.
* The app displays or conceals expense related fields in accordance with **expense configuration** settings.
* The app automatically calculates the **tax amount** by using both the **Sales tax group** and **Item sales tax group**, and you can override the **tax amount** if necessary.
 
## View expenses

When you open the Dynamics 365 expense management mobile app, the **Expenses** tab is selected and shows a list of all unattached expenses.

* You can view all unattached expenses, including both expenses that you manually created and your imported credit card transactions.
* You can view key information about the expenses in the list, such as the transaction date, merchant name, amount, and project ID.
* You can view an indication of any policy violations that the expenses have against the policies that your organization configures. When the policy violation indication is shown, the project ID is hidden.
* You can go to policy violation details from the **Edit expense** page.

### Quickly enter expenses by using OCR

To enter expenses by using optical character recognition (OCR), follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the plus sign (**+**) button.
1. The camera app opens, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that you already captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

    On the **New Expense** page, OCR fills in information such as the date, amount, and merchant name.

    > [!IMPORTANT]
    > OCR fills in information on the **New Expense** page only if the OCR add-in is enabled for the environment.

1. In the list of expense categories, select the category for the expense. You can filter the list by entering the name of the expense category.
1. Enter the transaction date of the expense.
1. Optional: Follow one or both of these steps:

    * Enter the merchant for the expense if OCR didn't fill it in, or if you want to change the value that was filled in.
    * Enter the amount of the expense if OCR didn't fill it in, or if you want to change the amount that was filled in.

1. Select the currency of the expense.
1. Select **Done**.

> [!NOTE]
> Per-diem and mileage expenses aren't supported in the preview version of the Dynamics 365 expense management mobile app. However, support is coming to the app when it becomes generally available.

### Modify an expense

To modify an expense, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Update the values of the fields that you want to modify.

    When the page loads, you see a limited number of fields. To view more fields, select **Add more details**.

    The list of fields that display are configured in the Expense report field visibility section of Dynamics 365 Finance.

1. When you're done, select **Add or Change the receipt**.
1. Select **Done**.

#### Add a receipt

To add a receipt, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **Add receipt**.
1. The camera app opens, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that you already captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

#### Change a receipt

To change a receipt, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **View receipt**.
1. On the **View receipt** page, select **Change receipt**.
1. The camera app opens, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that you already captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

#### Detach a receipt

To detach a receipt, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **View receipt**.
1. Select **Detach**.
1. In the confirmation message box, select **Detach**.

### Delete expenses

To delete expenses, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

After you delete an expense, the receipt that you attached to it moves to the list of unattached receipts and you can view it on the **Receipts** tab.

### Attach expenses to an expense report

To attach expenses to an expense report, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Attach** button.
1. Select the expense report that you want to attach the selected expenses to.
1. In the confirmation message box, select **Yes**.

After you attach expenses to an expense report, they no longer appear on the **Expenses** tab. The **Expenses** tab shows only expenses that aren't attached to a report.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
