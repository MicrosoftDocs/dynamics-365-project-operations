---
title: Capture a receipt using OCR
description: This article provides information about optical character recognition (OCR) processing for receipts.
author: mukumarm
ms.author: mukumarm
ms.date: 03/13/2025
ms.topic: how-to
ms.custom: 
  - bap-template

---

# Capture a receipt using OCR

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Expense entry was enhanced through the introduction of optical character recognition (OCR) processing for receipts. This functionality is designed to improve the user experience when creating expense reports.

## Key features

- The system extracts the merchant name, date, and total amount from receipts.
- The system tries to match unattached receipts to unattached expense transactions.
- You can create manually entered expense transactions from receipts.

## Attach receipts to an expense report

To automatically attach receipts that include credit card transactions when an expense report is created, complete the following steps.

  1. Open the **Expense management** workspace.
  2. On the **Receipts** tab, verify that unattached receipts exist. You can also upload receipts on the **Receipts** tab.
  3. On the **Expenses** tab, verify that unattached expenses exist. Typically, the expense administrator imports these expenses from the credit card provider.
  4. Select **New expense report**. Notice that you can include expenses, and receipts, now as well, when you create an expense report. If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.

## Create or match receipts to an expense report
To create an expense, or match an expense from a receipt, complete the following steps.

  1. On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.
  2. Under the uploaded image of the receipt, notice the **Create** and **Match** options.

      - Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.
      - If you select **Match**, the system tries to match an existing expense to the receipt.

## Installation

**Option 1:** To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance. You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).

1. Sign in to LCS, and open the desired environment.
2. Go to **Full details**.
3. Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.
4. Select **Install a new add-in**.
5. Select **Expense Management Service**.
6. Follow the installation guide, and agree to the terms and conditions.
7. Select **Install**.

**Option 2:** You can also enable the service by installing the **Dynamics 365 Project Operations expense receipt capture** application from the Power Platform Admin Center. 

To install the **Dynamics 365 Project Operations expense receipt capture** application, follow these steps.

1. Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/applications) and select the required environment.  
3. Select **Dynamics 365 Apps**.  
4. Select **Install App**.  
5. Search for the **Dynamics 365 Project Operations expense receipt capture** application, agree to the terms of service, and install it.
   
After completing either of the two installation options previously mentioned, go to the **Feature management** workspace and turn on the following features: 

- Expense reports reimagined
- Automatch and create expense from receipt

When you turn on these features, the following actions occur:

- The existing **Expense management** workspace is replaced with the new workspace.
- A new menu item for expense field visibility is added.
- You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.
- Workflows and any approvals still take you to the existing expense reports page.
- Receipts are processed through Microsoft Azure Cognitive Services, and metadata is extracted and added.
- An option is added that lets you create an expense report that includes matched unattached receipts.
- An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.

## Frequently asked questions

**Does Microsoft use my data for its models?**

No, Microsoft built a general machine learning model for its receipt processing service. This model isn't based on the receipts that you upload.

**Where is this feature available and processed?**

The availability of this feature in different regions is listed in the following table. If your region isn't currently supported, submit a request to prioritize the availability of the OCR service in your region. 

| Region | Supported                         |
|--------|-----------------------------------|
| USA    | Yes                               |
| CAN    | Yes                               |
| UK     | Yes                               |
| AUS    | Yes                               |
| EU     | Partially. English receipts only. |
| Asia   | No                                |
| Japan  | No                                |
| Africa | No                                |

**Where do my receipts go?**

Finance contacts Cognitive Services to extract the field data. Cognitive Services retains a copy of your receipt for up to 24 hours while processing occurs. After processing is completed, Cognitive Services removes the receipt. Receipts are still stored in Finance.

For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
