---
title: Manage guests for expenses using the Expense management mobile app
description: This article explains how to add or manage guests for expenses by using the Microsoft Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 05/02/2024
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Manage guests for expenses using the Expense management mobile app

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked and Project Operations Integrated with ERP based scenarios._

In some cases, employees must cover expenses that involve guests. When these employees submit expenses, their organization requires that they include guest details together with the expense information. The guests might be colleagues (coworkers) within the organization or external individuals.

The Expense Management system enables guest users to be incorporated into expense records.

## Include guest details on expenses

To enter expenses by using the Microsoft Dynamics 365 expense management mobile app, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Expenses** tab, select the plus sign (**+**) button.
1. The camera app is opened, and you can perform any of the following actions:

    - Take a photo of a receipt to capture it.
    - Select an existing receipt that was previously captured.
    - Select a receipt to upload from your mobile device.

1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**. On the **New Expense** page, optical character recognition (OCR) should fill in information such as the date, amount, and merchant name.

    > [!IMPORTANT]
    > OCR can fill in the information on the **New Expense** page only if the OCR add-in is enabled for the environment.

1. In the list of expense categories, select the category that's marked for **Guests** for the expense. You can filter the list by entering the name of the expense category.
1. Enter the transaction date of the expense.
1. Enter the amount of the expense if OCR didn't fill it in, or if you want to change the amount that OCR filled in.
1. Select the currency of the expense.
1. Select **Add guest**. This button is available only if the expense category is marked for **Guests**. It opens another page where you can add the guest details for the expenses.
1. To add colleagues as guests, select the **Coworkers** option. Then select colleagues in the list of coworkers.
1. To include guests from the previously used list, select **Previous guests**.
1. To add a new guest, select the plus sign (**+**) button, and add the guest details. You can view all the selected guests for the expense in the upper section.
1. Select **Done** to save the guest details.

> [!NOTE]
> If the expense category is marked for both **Guests** and **Itemization**, both the **Add guest** and **Itemization** buttons are available so that you can provide the necessary details.
