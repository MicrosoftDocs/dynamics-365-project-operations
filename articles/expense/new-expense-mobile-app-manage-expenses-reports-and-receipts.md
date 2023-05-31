---
title: Manage expenses, expense reports, and receipts using the Expense mobile app
description: This article explains how to manage expenses, expense reports, and receipts by using the Expense mobile app.
author: ramagadu
ms.date: 05/26/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ramagadu
ms.custom: bap-template
---

# Manage expenses, expense reports, and receipts using the Expense mobile app

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

> [!IMPORTANT]
> The functionality that's described in this article is available as part of a preview release. The functionality and the content of this article are subject to change. For more information about preview releases, see [One version service updates FAQ](/dynamics365/unified-operations/fin-and-ops/get-started/one-version.md).

This article explains how to manage expenses, expense reports, and receipts by using the Expense mobile app.

## Prerequisites for using the Expense mobile app

Before you can perform tasks in the Expense mobile app, you must work with your system administrator to ensure that the following requirements are in place:

* You must have access to the Microsoft Dynamics 365 Finance environment where you want to enter expenses.
* The **Employee** role must be assigned to your user account.
* The **Company** value must be set for your user account.
* You must be linked to an employee who has an active employment status.

## Overview of the Expense mobile app UI

The user interface (UI) of the Expense mobile app has three tabs:

* **Expenses** – This tab shows a list of all unattached expenses (that is, expenses that haven't been attached to an expense report.) The expenses on this tab include both manually created expenses and imported credit card transactions. You can manage the expenses (that is, create, update, or delete them).
* **Receipts** – This tab shows a list of all unattached receipts. You can switch between a **List** view and a **Tiles** view of the receipts, and manage them (that is, create, update, or delete them).
* **Reports** – This tab shows all expense reports for the employee for the selected company. It's subdivided into three tabs that group the expense reports based on their status.

## Manage expenses

This section explains how to manage your expenses by using the Expense mobile app.

### View expenses

When you open the Expense mobile app, the **Expenses** tab is selected and shows a list of all unattached expenses.

* You can view all unattached expenses: both expenses that you manually created and your imported credit card transactions.
* You can view key information about the expenses in the list, such as the transaction date, merchant name, amount, and project ID.
* You can view an indication of any policy violations that the expenses have against the policies that are configured by your organization. When the policy violation indication is shown, the project ID is hidden.
* You can go to policy violation details from the **Edit expense** page.

### Quickly enter expenses by using OCR

To enter expenses by using optical character recognition (OCR), follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select the plus sign (**+**) button.
1. The camera app is opened, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

    On the **New Expense** page, information such as the date, amount, and merchant name should be filled in by OCR.

    > [!IMPORTANT]
    > Information on the **New Expense** page is filled in by OCR only if the OCR option is enabled for the environment.

1. In the list of expense categories, select the category for the expense. You can filter the list by entering the name of the expense category.
1. Enter the transaction date of the expense.
1. Optional: Follow one or both of these steps:

    * Enter the merchant for the expense if it wasn't filled in by OCR, or if you want to change the value that was filled in.
    * Enter the amount of the expense if it wasn't filled in by OCR, or if you want to change the amount that was filled in.

1. Select the currency of the expense.
1. Select **Done**.

> [!NOTE]
> Per-diem and mileage expenses aren't supported in the preview version of the Expense mobile app. However, support will be added to the app when it becomes generally available.

### Modify an expense

To modify an expense, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select an expense.
1. Update the values of the fields that you want to modify.

    When the page is loaded, a limited number of fields are shown. To view more fields, select **Add more details**.

    The list of fields that are configured in Expense report field visibility the Dynamics 365 Finance display.

1. When you've finished, select **Add or Change the receipt**.
1. Select **Done**.

#### Add a receipt

To add a receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **Add receipt**.
1. The camera app is opened, and you can perform any of the following actions:

    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.

#### Change a receipt

To change a receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
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

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select an expense.
1. Select **View receipt**.
1. Select **Detach**.
1. In the confirmation message box, select **Detach**.

### Delete expenses

To delete expenses, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

After an expense is deleted, the receipt that was attached to it moves to the list of unattached receipts and can be viewed on the **Receipts** tab.

### Attach expenses to an expense report

To attach expenses to an expense report, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Expenses** tab, select the **Multi select** button in the upper-right corner.
1. Select the expenses.
1. Select the **Attach** button.
1. Select the expense report that you want to attach the selected expenses to.
1. In the confirmation message box, select **Yes**.

After expenses are attached to an expense report, they no longer appear on the **Expenses** tab. The **Expenses** tab shows only expenses that haven't been attached to a report.

## Manage expense reports

The **Reports** tab of the Expense mobile app shows all expense reports for the employee for the selected company. It's subdivided into three tabs that group the expense reports based on their status:

* **Draft** – This tab shows all the expense reports that are in **Draft** or **Rejected** status. Rejected expense reports are highlighted in red to indicate that they've been rejected against a report.
* **In review** – This tab shows all the expense reports that are in **In review** status.
* **Approved** – This tab shows all the expense reports that are in **Approved** or **Processed for payment** status.

### Create an expense report

To create an expense report, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Reports** tab, on the **Draft** tab, select the plus sign (**+**) button.
1. Optional: Enter a name for the expense report.
1. Optional: Enter a description.
1. Optional: Enter the location.
1. Select **Attach expenses**.
1. In the list of expenses, select one or more expenses.
1. Select **Done**.
1. Select **Save Draft** to save the report as a draft. Alternatively, select **Submit** to save the report and submit it for review.

### Delete expense reports

To delete expense reports, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Reports** tab, on the **Draft** tab, select the **Multi select** button.
1. Select one or more expense reports.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

After an expense report is deleted, all the expenses that were attached to it move to the list of unattached expenses and can be viewed on the **Expenses** tab.

### Submit an expense report for review

To submit an expense report for review, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Reports** tab, on the **Draft** tab, open the expense report that you want to submit for review.
1. Select **Submit**.

After an expense report is submitted, it moves to **In review** status and is available on the **In review** tab.

### Recall an expense report

To recall an expense report, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Reports** tab, on the **In review** tab, open the expense report that you want to recall.
1. Select **Withdraw**.

## Manage receipts

Many organizations require that employees attach a copy of a receipt to a travel-related or business-related expense report that they submit for reimbursement. The Expense mobile app lets users seamlessly create and manage receipts.

### View receipts

The **Receipts** tab of the Expense mobile app shows a list of all unattached receipts. By default, the list is shown in **Tiles** view. You can switch to **List** view by selecting the **List** button in the upper-right corner of the app.

Select a specific receipt in the list to preview the receipt and perform actions such as attaching the receipt to an expense or deleting the receipt.

### Create a receipt

The Expense mobile app lets you take a photo of a receipt to capture it. Alternatively, you can upload a receipt from your mobile device.

#### Create a receipt by using your camera

To create a receipt by using your camera, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the plus sign (**+**) button.
1. Select the **Camera** button.
1. Select **Save receipt**.

#### Upload a receipt from your mobile device

To upload a receipt from your mobile device, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the plus sign (**+**) button.
1. Select the **Select from device** button.
1. Select either **Photo Library** or **Choose File**.
1. Select a photo or a file.
1. Select **Done**.
1. Select **Save receipt**.

### Delete receipts

You can delete one or more receipts at a time.

To delete multiple receipts, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the **Multi select** button.
1. Select the receipts.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

You can delete one receipt at a time from the receipt's preview page. To delete one receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the receipt to open the preview page.
1. Select **Discard**.
1. In the confirmation dialog box, select **Delete**.

### Attach a receipt to an expense

You can attach a receipt to an expense either directly from the **Receipts** tab or from the receipt's preview page.

To attach a receipt to an expense directly from the **Receipts** tab, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the **Attach** button.
1. Select an expense in the list.

To attach a receipt to an expense from the receipt's preview page, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Expense mobile app.
1. On the **Receipts** tab, select the receipt to open the preview page.
1. Select **Attach to an expense**.
1. Select an expense in the list.
