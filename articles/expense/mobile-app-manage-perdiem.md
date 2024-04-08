---
title: Manage Per diem using the Expense management mobile app
description: This article explains how to manage Perdiem expenses using Expense management mobile app.
author: mukumarm
ms.date: 04/01/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Perdiem using the Expense management mobile app

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked and resource/non-stocked based scenarios_

Per diem expenses refer to daily allowances provided to cover expenses incurred while traveling for business purposes. These expenses typically include meals, lodging, and incidental expenses such as transportation and tips.
Per diem rates can vary depending on factors such as the destination, the length of stay, and the employer's policies. 

Using per diem allowances simplifies the reimbursement process for both employees and employers, as it eliminates the need for individuals to track and submit receipts for each expense incurred during travel. Instead, employees receive a fixed daily allowance based on the location and duration of their trip.

## Prerequisites
To use the Per diem feature on Dynamics 365 expense management mobile app, you must use the following versions of Microsoft Dynamics 365 Finance with the latest quality update (QU) or later.
* 10.0.38 - 10.0.1777.165 or later
* 10.0.39 - 10.0.1860.84 or later
  
Activate the following features:
* Expense reports re-imagined
* Per-diem for expense report re-imagined interface

> [!NOTE]
> **Per diem** expense entries will adhere to the **Per-diem for expense report re-imagined interface** feature. Users will be restricted from editing or modifying per diem expenses generated using alternative user interface **Expense management** > **My expenses** > **Expense report**. For more information, see [Manage per diem using reimagined interface](per-diem-expenses.md).

## Create Per diem expenses - Meal type per day

To enter expenses by using **expense management mobile** application, follow these steps.

1. Goto **Expense management parameters** > **Per diem** tab. Set **Calculate meal reduction by** to **Meal type per day**.
2. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
3. Navigation to the **Expenses** tab, select the plus sign (**+**) button.
4. The camera app opens, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that's been captured.
    * Select a receipt to upload from your mobile device.
5. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
6. In the list of expense categories, select the **category** that is marked for **Per diem** for the expense. You can filter the list by entering the name of the expense category.
7. Enter the **Per diem from date** and **Per diem to date** of the expense.
8. Enter the **travel location**. Based on the travel destination, the **currency** will be automatically set as default.
9. Click **Edit meal exclusion** button. It will enable to exclude the meals.
10. Click **Show all** to view the meals per day for inclusion or exclusion.
11. Click **Calculate means and incidentals** to calculate meals & incidentals amount and total amount.
12. Click **Save** to save the details.
13. Select **Done** to save the expense.

## Create Per diem expenses - Meal type per trip

To enter expenses by using **expense management mobile** application, follow these steps.

1. Goto **Expense management parameters** > **Per diem** tab. Set **Calculate meal reduction by** to **Meal type per trip**.
2. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
3. Navigation to the **Expenses** tab, select the plus sign (**+**) button.
4. The camera app opens, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that's been captured.
    * Select a receipt to upload from your mobile device.
5. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
6. In the list of expense categories, select the **category** that is marked for **Per diem** for the expense. You can filter the list by entering the name of the expense category.
7. Enter the **Per diem from date** and **Per diem to date** of the expense.
8. Enter the **travel location**. Based on the travel destination, the **currency** will be automatically set as default.
9. Enter number of **breakfast, lunch and dinner** excluded from the allowance.
11. Click **Refresh** to calculate meals & incidentals amount and total amount.
12. Select **Done** to save the expense.

## Create Per diem expenses - Number of meals per day

To enter expenses by using **expense management mobile** application, follow these steps.

1. Goto **Expense management parameters** > **Per diem** tab. Set **Calculate meal reduction by** to **Number of meals per day**.
2. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
3. Navigation to the **Expenses** tab, select the plus sign (**+**) button.
4. The camera app opens, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that's been captured.
    * Select a receipt to upload from your mobile device.
5. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
6. In the list of expense categories, select the **category** that is marked for **Per diem** for the expense. You can filter the list by entering the name of the expense category.
7. Enter the **Per diem from date** and **Per diem to date** of the expense.
8. Enter the **travel location**. Based on the travel destination, the **currency** will be automatically set as default.
9. Enter number of **breakfast, lunch and dinner** excluded from the allowance.
11. Click **Refresh** to calculate meals & incidentals amount and total amount.
12. Select **Done** to save the expense.

For more information about **expense reports**, see [Manage expense reports by using the Dynamics 365 expense management mobile app](mobile-app-manage-expense-reports.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
