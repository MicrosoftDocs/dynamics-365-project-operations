---
title: Manage itemization using the Expense management mobile app
description: Learn how to itemize expenses efficiently using the Expense management mobile app. Follow step-by-step instructions to create and manage detailed expense breakdowns.
author: mukumarm
ms.date: 02/05/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Expense itemization using the Expense management mobile app

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked and Project Operations Integrated with ERP based scenarios_

Many organizations require employees to provide a detailed breakdown of travel expenses. For example, a hotel bill typically lists various expenditures such as room charges, taxes, parking fees, and other miscellaneous costs incurred daily throughout the stay. To accommodate the specific requirements of each organization, you can configure **expense categories** to include **subcategories** or individual line items that make up an expense. The **Expense management mobile** application enables users to **itemize** expenses for any category that needs a detailed breakdown.   

To use the **Itemization** feature on the expenses mobile app, enable the **Ability to itemize recurring expenses quickly** feature.

## Create itemized expenses

To enter expenses by using the **expense management mobile** application, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. Navigate to the **Expenses** tab, and select the plus sign (**+**) button.
1. The camera app opens, and you can perform any of the following actions:
    * Take a photo of a receipt to capture it.
    * Select an existing receipt that's been captured.
    * Select a receipt to upload from your mobile device.
1. Preview the receipt, and then select **Done**. If you want to retake the photo, select **Retake**.
    On the **New Expense** page, OCR fills in information such as the date, amount, and merchant name.
    > [!IMPORTANT]
    > OCR fills in the information on the **New Expense** page only if the OCR add-in is enabled for the environment.
1. In the list of expense categories, select the **category** that is marked for **itemization** for the expense. You can filter the list by entering the name of the expense category.
1. Enter the transaction date of the expense.
1. Enter the amount of the expense if OCR didn't fill it in, or if you want to change the amount that OCR filled in.
1. Select the currency of the expense.
1. Select **Itemize expenses**. **Itemize expenses** is available only if the expense category is marked for **itemization**. It opens another page to create the itemization for the main expense.
    * Select **+Create new itemization**.
    * Select the **Start date**.
    * Select the **Subcategory**.
    * Enter **Daily rate** and the **Quantity**.
    * Select **Save** to save the **itemization** details.
    * Review the **Itemized amount** and **Remaining amount**. When you create the itemization detail, the itemized amount can be more than expense amount but 
      while validation is performed during the expense report submission.
1. Select **Done** to save the expense.

For more information about **expense reports**, see [Manage expense reports by using the Dynamics 365 expense management mobile app](mobile-app-manage-expense-reports.md).

## View itemized expenses

To view the itemized expenses by using **expense management mobile** application, follow these steps:

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. Go to the **Expenses** tab and select the **expense** that you want to validate its itemization details, or go to the **Reports** tab, select the **expense report**, and then select the expense. The expense screen opens.
1. Select **Itemize expenses**. **Itemize expenses** is available only if the expense category is marked for **itemization**. It opens another page to create or view or update the itemization for the main expense.
1. To view the itemized expenses created by using **+Create new itemization**, select **View all itemized expenses**.
1. Select the itemized expense to view the expense details of the itemized expense.
1. You can update **itemized** expenses with more details if needed. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
