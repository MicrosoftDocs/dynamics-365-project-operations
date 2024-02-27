---
title: Manage itemization using Expense management mobile app
description: This article explains how to itemize expenses using the Expense management mobile app.
author: mukumarm
ms.date: 02/27/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Expense itemization using Expense management mobile app

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked and resource/non-stocked based scenarios_

Many organizations mandate that employees furnish a comprehensive breakdown of travel expenses. Take, for instance, a hotel bill, which typically lists various expenditures such as room charges, taxes, parking fees, and additional miscellaneous costs incurred daily throughout the stay. To accommodate the specific requirements of each organization, **expense categories** can be configured to encompass **subcategories** or individual line items constituting an expense. An **Expense management mobile** application empowers users to **itemize** expenses for any designated category that necessitates such detailed breakdowns.   

## Create itemized expenses

To enter expenses by using **expense managemement mobile** appplication, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
2. Navigation to the **Expenses** tab, select the plus sign (**+**) button.
3. The camera app is opened, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that has already been captured.
    * Select a receipt to upload from your mobile device.
4. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
    On the **New Expense** page, information such as the date, amount, and merchant name should be filled in by OCR.
    > [!IMPORTANT]
    > Information on the **New Expense** page is filled in by OCR only if the OCR add-in is enabled for the environment.
5. In the list of expense categories, select the **category** which is marked for **itemization** for the expense. You can filter the list by entering the name of the expense category.
6. Enter the transaction date of the expense.
7. Enter the amount of the expense if it wasn't filled in by OCR, or if you want to change the amount that was filled in.
8. Select the currency of the expense.
9. Select **Itemize expenses**. This button will be available only if the expense category is marked for **itemization**. It will open another page to create the itemization for the main expense.
    * Select **+Create new itemization**.
    * Select the **Start date**.
    * Select the **Subcategory**.
    * Enter **Daily rate** and the **Quantity**.
    * Click **Save** to save the **itemization** details.
    * Review the **Itemized amount** and **Remaining amount**. While creating the itemization detali, Itemized amount can be more than expense amount but 
      while validation will be performed during the expense report submission
10. Select **Done** to save the expense.

For more information about **expense reports**, see [Manage expense reports by using the Dynamics 365 expense management mobile app](mobile-app-manage-expense-reports.md).

## View itemized expenses

To view the itemized expenses by using **expense managemement mobile** appplication, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
2. Navigate to the **Expenses** tab and choose the **expense** that requires validation of its itemization details or navigate to **Reports** tab, select the **expense report** and select the expense . It will open the expense screen.
4. Select **Itemize expenses**. This button will be available only if the expense category is marked for **itemization**. It will open another page to create or view or update the itemization for the main expense.
5. Select **View all itemizaed expenses** to view the itemized expenses created using **+Create new itemization**.
6. Select the itemized expense to view the expense details of the itemized expense.
