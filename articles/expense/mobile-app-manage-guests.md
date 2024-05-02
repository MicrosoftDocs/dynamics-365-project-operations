---
title: Manage guests using the Expense management mobile app
description: This article explains how to add or manage guests for expenses using the Expense management mobile app.
author: mukumarm
ms.date: 05/02/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Manage guest functionality for expenses using the Expense management mobile app

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked and resource/non-stocked based scenarios_

The Expense Management system offers the capability to incorporate guest users into expense records. In certain instances, employees may need to cover expenses involving guests. When submitting expenses, organizations require employees to include guest details along with the expense information. Guests can either be colleagues within the organization or external individuals.

## Include guest details on the expenses

To enter expenses by using **expense management mobile** application, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
2. Navigation to the **Expenses** tab, select the plus sign (**+**) button.
3. The camera app opens, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that's been captured.
    * Select a receipt to upload from your mobile device.
4. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
    On the **New Expense** page, information such as the date, amount, and merchant name should be filled in by OCR.
    > [!IMPORTANT]
    > The information on the **New Expense** page is filled in by OCR only if the OCR add-in is enabled for the environment.
5. In the list of expense categories, select the **category** that is marked for **Guests** for the expense. You can filter the list by entering the name of the expense category.
6. Enter the transaction date of the expense.
7. Enter the amount of the expense if it wasn't filled in by OCR, or if you want to change the amount that was filled in.
8. Select the currency of the expense.
9. Select **Add guest**.  **Add guest** is available only if the expense category is marked for **Guests**. It opens another page to add the guest details for the expenses.
10. Select **Coworkers** option to add the coworker as a guest. Choose colleagues from the coworkers list.
11. Select **Previous guests** to include guests from the previously used list.
12. To add a new guest, Select **+** icon and add the guest details. You can see all the selected guests for the expense in the top section. 
13. Select **Done** to save the guest details.

>Note When the expense category is designated for guests and itemization, both the **Itemization** and **Add Guest** buttons will be accessible to provide the necessary details.
