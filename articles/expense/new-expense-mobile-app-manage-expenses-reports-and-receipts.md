---
title: Manage expenses, expense reports, and receipts using the Expense mobile app
description: This article provides information about managing expenses, expense reports, and receipts using the Expense mobile app.
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
> This article provides information about how you can manage expenses, expense reports, and receipts using the Expense mobile app.

## Prerequisites for using the Expense mobile app

To carry out tasks within the Expense mobile app, certain prerequisites must be in place. Collaborate with your **System Administrator** to ensure the following requirements are met.

* You must have access to the Microsoft Dynamics 365 Finance environment where you want to enter expenses.
* You must have the **Employee** role assigned to your user account.
* You must have the **Company** value set for your user account.
* You must be linked to an **Employee** who has an active employment status.

## Overview

The new Expense mobile app has three tabs.

* The **Expense** tab allows you to see a list of unattached expenses (both manual and credit transactions) and manage them (create, update, delete).
* The **Receipts** tab displays a list of all unattached receipts. You can switch between a list view and a tile view of receipts and manage them (create, update, delete).
* The **Reports** tab is subdivided into three tabs to group and show the expense reports based on their status.

## Manage expenses

The following sections explain how to manage your expenses using the Expense mobile app.

### View expenses

When you launch the Expense mobile app, the **Expenses** page displays a list of **unattached expenses**.

* You can see all the unattached expenses that you have created manually or your imported credit card transactions.
* You can see key information about the expenses in the list page, such as **Transaction date, Merchant Name, Amount**, and **Project ID.**
* You can see the indication of **policy violations** if any of the expenses have policy violations against the policies that are configured by your organization. When the policy indication is shown, the Project ID is hidden.
* You can navigate to policy violations details from the Edit expense page.

### Rapid expense entry using OCR

To enter expenses using optical character recognition (OCR), follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application, and then open the **Expense mobile app.**
1. Select the **Expenses** tab.
1. Select the **+** button.
1. The camera app opens so you can:
   * **Take a photo** of a receipt to capture it.
   * **Select existing** receipt that's already captured.
   * **Select from device** to upload a receipt from your mobile device. 
1. Preview the receipt and select **Done**. You can select the **Retake** button if you would like to retake the picture.
1. On the **New Expense** page, information such as **Date**, **Amount**, **Merchant name** are populated using OCR.
1. From the list of expense categories, select the expense category. You can filter the categories by typing expense category name.
1. Enter the transaction date of the expense.
1. Optional: 
   * Enter the merchant for the expense if it isn't populated by OCR or if you would like to change the populated value.
   * Enter the amount of the expense if it isn't populated by OCR or if you would like to change the amount.
1. Select the currency of the expense.
1. Select  **Done**.

> [!IMPORTANT] 
> In New Expense page, key information is populated using OCR only when the OCR option is enabled for the environment.

> [!NOTE] 
> Per-diem and Mileage expenses are not supported in the Preview version, but will be added to the application becoming Generally Available.

### Modify an expense

To modify an expense, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Expenses** tab.
1. Select an expense.
1. Update the values for the fields that you want to modify:
   1. When the page is loaded, a limited number of fields are shown. To see more fields, select **Add more details.**
   1. The list of fields that are configured in Expense report field visibility the Microsoft Dynamics 365 Finance display.
1. Select **Add or Change the receipt**.
1. Select **Done**

#### Add a receipt

To add a receipt, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Expenses** tab.
1. Select an expense.
1. Select **Add receipt**.
1. The camera app opens so you can:
   * **Take a photo** of a receipt to capture it.
   * **Select existing** receipt that's already captured.
   * **Select from device** to upload a receipt from your mobile device. 
1. Preview the receipt and select **Done**. You can select the **Retake** button if you would like to retake the picture.

#### Change a receipt

To change a receipt, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Expenses** tab
1. Select an expense.
1. Select **View receipt**.
1. Select **Change receipt** in View receipt page.
1. The camera app opens so you can:
   * **Take a photo** of a receipt to capture it.
   * **Select existing** receipt that's already captured.
   * **Select from device** to upload a receipt from your mobile device. 
1. Preview the receipt and Select **Done**. You can select the **Retake** button if you would like to retake the picture.

#### Detach a receipt

To detach a receipt, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Expenses** tab.
1. Select an expense.
1. Select **View receipt**.
1. Select **Detach**.
1. Select **Detach** in the **Confirmation** dialog box.

### Delete expenses

To delete expenses, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Expenses** tab.
1. Select **Multi select icon**.
1. Select the expenses.
1. Select the **Delete** icon.
1. Select **Delete** in the **Confirmation** dialog box.

When an expense is deleted the receipt attached that expense moves to unattached receipts and receipt can be seen in Receipts.

### Attach expenses to reports

To attach expenses to reports, follow these steps.

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select the **Expenses** tab.
3. Select the **Multi select** icon at the top right corner of the app.
4. Select the expenses.
5. Select the **Attach** icon.
6. Select the report to which you would like to attach selected expense.
7. Select **Yes** in the **Confirmation** dialog box.

After expenses are attached a report, those expenses no longer show on the **Expenses** list. The **Expenses** list only shows expenses that have not been attached to a report.

## Manage expense reports

The **Reports** tab displays all expense reports for the employee for the selected company. The **Reports** tab is subdivided into three tabs to group and show the expense reports based on their status.

* The **Draft** tab displays all of the expense reports that are in **Draft** or **Rejected** status. Rejected expense reports are highlighted in red to indicate they are rejected against a report.
* The **In review** tab displays all of the expense reports that are in the **In review** status.
* The **Approved** tab displays all of the expense reports that are in the **Approved** or **Processed for payment** status.

### Create a new expense report

To create a new expense report, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Reports** tab.
1. Select the **Draft** tab.
1. Select the **+** icon.
1. Optional: Enter the Report name.
1. Optional: Enter the Description.
1. Optional: Enter location.
1. Select **+Attach expenses**.
1. Select one or more expense from the list of expense.
1. Select **Done**.
1. Select **Save Draft** to save the report as draft, or select the **Submit** button to save the report and submit it for review.

### Delete expense reports

To delete expense reports, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Reports** tab.
1. Select the **Draft** tab.
1. Select the **Multi select icon**.
1. Select one or more reports.
1. Select the **Delete icon**.
1. Select **Delete** in the **Confirmation** dialog box.

When the report is deleted successfully, all the expenses that were attached the report move to the **Expenses list**.

### Submit an expense report for review

To submit an expense report for review, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Reports** tab.
1. Select the **Draft** tab.
1. Open the report that you would like to submit for review.
1. Select **Submit**.

When the report is successfully submitted, the Report moves to the **In review** status and it's available under In review tab.

### Recall an expense report

To recall an expense report, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Reports** tab.
1. Select the **In review** tab.
1. Open the report that you would like to recall.
1. Select **Withdraw**.


## Manage receipts

Many organizations require you to attach a copy of a receipt to a travel-related or business-related expense reports that an employee submits for reimbursement. The Expense mobile app allows users to create and manage receipts seamlessly.

### View receipts

You can view the list of receipts from the **Receipt** tab of the Expense mobile app. By default, the list of receipts is shown in **Tiles** view. You can switch to **List** view by selecting **List** icon at the right top corner of the app.

Select the specific receipt from the list to preview the receipt and perform action such as **Attach to expense** or **Delete** the receipt.

### Create a new receipt

The Expense mobile app allows you to capture a photo of a new receipt or upload a receipt from your device.

**Create a new receipt using camera:**

To create a new receipt using your camera, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Receipts** tab.
1. Select the **+** icon.
1. Select the **Camera** icon.
1. Select **Save receipt**.

**Upload a new receipt from your mobile device:**

To upload a new receipt from your mobile device, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Receipts** tab.
1. Select the **+** icon.
1. Select **Select from device** Icon
1. Select either **Photo Library** or **Choose File**.
1. Select a file or photo.
1. Select **Done**.
1. Select **Save receipt**.

### Delete receipts

You can delete one or more receipts at a time.

To delete multiple receipts, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Receipts** tab.
1. Select the **Multi select icon**.
1. Select one or more receipts.
1. Select the **Delete icon**.
1. Select **Delete** in the **Confirmation** dialog box.

You can delete one receipt at a time from the **Preview** page. 

To delete one receipt from the preview page, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
1. Select the **Receipts** tab.
1. Open a receipt.
1. Select **Discard**.
1. Select **Delete** in the **Confirmation** dialog box.

### Attach a receipt to an expense

You can attach a receipt to an expense either from the **Receipt list** page or from the **Preview** page.

To attach a receipt to an expense from the **Receipt list** page, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app.**
2. Select the **Receipts** tab.
3. Select the **Attach** icon.
4. Select an expense from the list.

To attach a receipt to an expense from the receipt **Preview** page, follow these steps.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select the **Receipts** tab.
3. Open a receipt.
4. Select **Attach to an expense**.
5. Select an expense from the list.
