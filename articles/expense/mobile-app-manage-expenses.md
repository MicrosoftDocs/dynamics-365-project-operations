---
title: Manage expenses by using the Dynamics 365 expense management mobile app
description: This article explains how to manage expenses by using the Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 11/06/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# Manage expenses by using the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for stocked/production-based scenarios_

This article explains how to manage expenses by using the Dynamics 365 expense management mobile app.

## Default Settings for Expense Creation and Updates

When an expense is either created or updated, specific values are automatically set based on predetermined settings or configurations:

* Defaulting the setting for **Include tax** to **Yes**. However, the user can override the default setting and set **Include tax** to **No** as well.
* Set the **item sales tax group** based on the **expense category** by default.
* Set the **sales tax group** based on the following **priority order**: **project, country, region, and vendor mapped with employee**.
* Display or conceal expense related fields in accordance with **expense configuration** settings.
* Automatically calculate the **tax amount** using both the **Sales tax group** and **Item sales tax group**, and allow the user to override the **tax amount** if necessary.
 
## View expenses

When you open the Dynamics 365 expense management mobile app, the **Expenses** tab is selected and shows a list of all unattached expenses.

* You can view all unattached expenses: both expenses that you manually created and your imported credit card transactions.
* You can view key information about the expenses in the list, such as the transaction date, merchant name, amount, and project ID.
* You can view an indication of any policy violations that the expenses have against the policies that are configured by your organization. When the policy violation indication is shown, the project ID is hidden.
* You can go to policy violation details from the **Edit expense** page.

### Quickly enter expenses by using OCR

To enter expenses by using optical character recognition (OCR), follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the plus sign (**+**) button.
1. The camera app is opened, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

    On the **New Expense** page, information such as the date, amount, and merchant name should be filled in by OCR.

    > [!IMPORTANT]
    > Information on the **New Expense** page is filled in by OCR only if the OCR add-in is enabled for the environment.

1. In the list of expense categories, select the category for the expense. You can filter the list by entering the name of the expense category.
1. Enter the transaction date of the expense.
1. Optional: Follow one or both of these steps:

    * Enter the merchant for the expense if it wasn't filled in by OCR, or if you want to change the value that was filled in.
    * Enter the amount of the expense if it wasn't filled in by OCR, or if you want to change the amount that was filled in.

1. Select the currency of the expense.
1. Select **Done**.

> [!NOTE]
> Per-diem and mileage expenses aren't supported in the preview version of the Dynamics 365 expense management mobile app. However, support will be added to the app when it becomes generally available.

### Modify an expense

To modify an expense, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Update the values of the fields that you want to modify.

    When the page is loaded, a limited number of fields are shown. To view more fields, select **Add more details**.

    The list of fields that display are configured in the Expense report field visibility section of Dynamics 365 Finance.

1. When you've finished, select **Add or Change the receipt**.
1. Select **Done**.

#### Add a receipt

To add a receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **Add receipt**.
1. The camera app is opened, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

#### Change a receipt

To change a receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **View receipt**.
1. On the **View receipt** page, select **Change receipt**.
1. The camera app is opened, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

#### Detach a receipt

To detach a receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense management mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **View receipt**.
1. Select **Detach**.
1. In the confirmation message box, select **Detach**.

### Delete expenses

To delete expenses, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

After an expense is deleted, the receipt that was attached to it moves to the list of unattached receipts and can be viewed on the **Receipts** tab.

### Attach expenses to an expense report

To attach expenses to an expense report, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Attach** button.
1. Select the expense report that you want to attach the selected expenses to.
1. In the confirmation message box, select **Yes**.

After expenses are attached to an expense report, they no longer appear on the **Expenses** tab. The **Expenses** tab shows only expenses that haven't been attached to a report.

