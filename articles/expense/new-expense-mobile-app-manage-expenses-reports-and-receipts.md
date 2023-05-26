---
title: Manage expenses, reports, and receipts using the Expense mobile app
description: This article provides information about managing expenses, reports, and receipts using the Expense mobile app.
author: ramagadu
ms.date: 05/26/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# Manage expenses, reports, and receipts using the Expense mobile app

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

> [!IMPORTANT]
>The functionality that's described in this article is available as part of a preview release. The functionality described and the content in this article are subject to change. For more information about preview releases, see [**One version service updates FAQ**](/dynamics365/unified-operations/fin-and-ops/get-started/one-version.md).

This article provides information about how you can manage expenses, reports, and receipts using the Expense mobile app.

## Prerequisites for using the Expense mobile app

To carry out tasks within the Expense mobile app, certain prerequisites must be in place. It is advised to collaborate with your **System Administrator** to ensure the following requirements are met.

* You must have access to the Microsoft Dynamics 365 Finance environment where you want to enter expenses.
* You must have the role **Employee** role assigned to your user account.
* You must have the **Company** value set for your user account.
* You must be linked to an **Employee** who has an active employment.

## Overview

The new **Expense mobile app** has three tabs in the application **Expenses** , **Reports** and **Receipts**.

The **Expense** tab allows users to see a list of unattached expenses (both manual and credit transactions) and manage them (create, update, delete).

The **Receipts** tab displays a list of all unattached receipts. Users could switch between a list and a tile view of their receipts and manage them (create, update, delete).

The **Reports** tab is divided into three sub tabs to group and show the expense reports based on their status.

## Manage expenses

### View expenses

When users launch the application, they will be taken to the **Expenses** screen, i.e., home screen, which displays a list of **unattached expenses**.

- Users can see all the unattached expenses that they have created manually or imported credit card transactions.
- Users can see key information about the expenses in the list screen such as **Transaction date, Merchant Name, Amount, Project Id.**
- Users can see the indication of **policy violations** against the expenses on the list screen if expenses have any policy violations against the policies configured by the organization. Whenever the policy indication is being shown, Project Id will be hidden.
- Users can navigate to Edit expense screen by tapping on the records in the list screen.
- Users can navigate to policy violations details from the Edit expense screen.

### Rapid expense entry using OCR

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select  **+** button
1. Camera will open to **Take a photo** of receipt or **Select existing** to selected already captured or **Select from device** to upload receipt from your mobile device. Select one of the options.
2. Preview the receipt and Select **Done**. You can select the **Retake** button if you would like to retake the picture.
3. In the New Expense screen, key information such as Date, Amount, Merchant name are populated using OCR.
4. Select the expense category, you see a list of expense categories, you can filter the categories by typing expense category name.
5. Enter the transaction date of the expense.
6. Optional: Enter the merchant for the expense if it's not populated by OCR or you would like to change the populated value.
7.  Enter the amount of the expense if it's not populated by OCR or you would like to change the amount.
8.  Select the currency of the expense.
9.  Select  **Done**.

> [!NOTE] 
> In New Expense screen, key information is populated using OCR only when the OCR is enabled for the environment.

> [!NOTE] 
> Per-diem and Mileage expenses are not supported as of now in the Preview version, they will be added before the application going to GA.

### Modify expense

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select an expense
4. Update the values for the fields that you would like to modify:
  1. By default, when the screen is loaded, limited number of fields are shown, to see more fields select **Add more details.**
  2. You see all the list of fields that are configured in Expense report field visibility the Dynamics 365 Finance
5. Add or Change the receipt
6. Click **Done**

#### Add receipt

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select an expense.
4. Select **Add receipt**
5. Camera will open to **Take a photo** of receipt or **Select existing** to selected already captured or **Select from device** to upload receipt from your mobile device. Select one of the options.
6. Preview the receipt and Select **Done**. You can select the **Retake** button if you would like to retake the picture.

#### Change receipt

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select an expense
4. Select **View receipt**.
5. Select **Change receipt** in View receipt screen
6. Camera will open to **Take a photo** of receipt or **Select existing** to selected already captured or **Select from device** to upload receipt from your mobile device. Select one of the options.
7. Preview the receipt and Select **Done**. You can select the **Retake** button if you would like to retake the picture.

#### Detach receipt

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select an expense.
4. Select **View receipt**.
5. Select **Detach**
6. Select **Detach** in Confirmation Dialog

### Delete expenses

1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select **Multi select icon**
4. Select the expenses
5. Select **Delete** icon
6. Select **Delete** in confirmation dialog box

When an expense is deleted the receipt attached that expense will move to unattached receipts and receipt can be seen in Receipts.

### Attach expenses to reports


1. On your mobile device, open the  **Power Apps mobile** application and open the **Expense mobile app.**
2. Select **Expenses** tab
3. Select **Multi select icon** at the top right corner of the app
4. Select the expenses
5. Select **Attach** icon
6. Select a Report to which you would like to attach selected expense
7. Select **Yes** in the confirmation dialog box

When the expenses are attached a report, those expenses will not be shown in the Expenses as Expenses list will only show the unattached expenses.

## Manage expense reports

The **Reports** tab displays all expense reports for the employee for the selected company. Report tab is sub-divided into three sub tabs to group and show the expense reports based on their status.

**Draft:** This tab displays all the expense reports that are in **Draft** or **Rejected** status. Rejected expense reports are highlighted as Rejected against a report in Red.

**In review:** This tab displays all the expense reports that are in In review status.

**Approved:** This tab displays all the expense reports that are in Approved or Processed for payment status.

### Create a new report

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Reports** tab
3. Select **Draft** tab
4. Select **+** icon
5. Optional: Enter the Report name
6. Optional: Enter the Description
7. Optional: Enter location
8. Select **+Attach expenses**
9. Select one or more expense from the list of expense
10. Select **Done**
11. Select **Save Draft** to save the report as draft or select the **Submit** button to save the report and submit it for review.

### Delete report(s)

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Reports** tab
3. Select **Draft** tab
4. Select **Multi select icon**
5. Select one or more reports
6. Select **Delete icon**
7. Select **Delete** in confirmation dialog box

When the report is deleted successfully, all the expenses that were attached a report will move to unattached expenses list.

### Submit a report for review

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Reports** tab
3. Select **Draft** tab
4. Open the report that you would like to Submit for review
5. Select **Submit**

When the report is successfully submitted, the Report will move to In review status and it will be available under In review tab.

### Recall a report


1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Reports** tab
3. Select **In review** tab
4. Open the report that you would like to Recall
5. Select **Withdraw**

When the report is successfully recalled, the Report will move to Draft status and it will be available under Draft tab.

## Manage receipts

Many organizations require that a copy of a receipt be attached to a travel-related or business-related expense report that an employee submits for reimbursement. The  **Expense mobile app** allows users to create and manage receipts seamlessly.

### View receipts

You can view the list of receipts from the Receipt tab of the mobile app. By default, the list of reciepts is shown in **Tiles** view. You could switch to **List** view by selecting List icon at the right top corner of the app.

Select the specific reciept from the list to preview the reciept and perform action such as **Attach to expense** or **Delete** the reciept.

### Create a new receipt

Expense mobile app allows you to capture a photo of a new receipt or upload a reciept from your device.

**Create a new reciept using camera:**

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts** tab
3. Select **+** icon
4. Select **Camera** Icon
5. Select **Save receipt**

**Upload a new receipt from the device:**

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts** tab
3. Select **+** icon
4. Select **Select from device** Icon
5. Select either Photo Library or Choose File
6. Select file or photo
7. Select **Done**
8. Select **Save receipt**

### Delete reciept(s)

You can delete one receipt or multiple receipts at a time.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts** tab
3. Select **Multi select icon**
4. Select one or more receipts
5. Select **Delete icon**
6. Select **Delete** in confirmation dialog box

You can also delete a single receipt from the preview screen as well.

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts**
3. Open a receipt
4. Select **Discard**
5. Select **Delete** in confirmation dialog box

### Attach receipt to an expense

You can attach the receipt to an expense either from the receipt list screen or from the preview screen.

**Attach receipt to an expense from reciept list screen:**

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts**
3. Select **Attach** Icon
4. Select an expense from the list

**Attach receipt to an expense from receipt preview screen:**

1. On your mobile device, open the **Power Apps mobile** application and open the **Expense mobile app**
2. Select **Receipts**
3. Open a receipt
4. Select **Attach to an expense**
5. Select an expense from the list
