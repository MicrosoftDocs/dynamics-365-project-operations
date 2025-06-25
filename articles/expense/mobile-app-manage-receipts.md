---
title: Manage receipts by using the Dynamics 365 expense management mobile app
description: This article explains how to manage receipts by using the Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 11/06/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# Manage receipts by using the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for stocked/production-based scenarios_

This article explains how to manage receipts by using the Microsoft Dynamics 365 expense management mobile app.

Many organizations require that employees attach a copy of a receipt to a travel-related or business-related expense report that they submit for reimbursement. The Dynamics 365 expense management mobile app lets users seamlessly create and manage receipts.

## Expense Management Service add-in

To use these advanced expense capabilities, install the Expense Management Service add-in for Dynamics 365 Finance, and turn on the features in your instance. You can access the add-in from your project in Microsoft Dynamics Lifecycle Services. This add-in is required to use the optical character recognition (OCR) service for receipt scanning, and to enter the default merchant, transaction date, and amount from the receipt to the expense line.

1. Sign in to Lifecycle Services, and open the desired environment.
1. Go to **Full details**.
1. Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.
1. Select **Install a new add-in**.
1. Select **Expense Management Service**.
1. Follow the installation guide, and agree to the terms and conditions.
1. Select **Install**.

## View receipts

The **Receipts** tab of the Dynamics 365 expense management mobile app shows a list of all unattached receipts. By default, the list is shown in **Tiles** view. You can switch to **List** view by selecting the **List** button in the upper-right corner of the app.

Select a specific receipt in the list to preview the receipt and perform actions such as attaching the receipt to an expense or deleting the receipt.

## Create a receipt

The Dynamics 365 expense management mobile app lets you take a photo of a receipt to capture it. Alternatively, you can upload a receipt from your mobile device.

### Create a receipt by using your camera

To create a receipt by using your camera, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the plus sign (**+**) button.
1. Select the **Camera** button.
1. Select **Save receipt**.

### Upload a receipt from your mobile device

To upload a receipt from your mobile device, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the plus sign (**+**) button.
1. Select the **Select from device** button.
1. Select either **Photo Library** or **Choose File**.
1. Select a photo or a file.
1. Select **Done**.
1. Select **Save receipt**.

## Delete receipts

You can delete one or more receipts at a time.

To delete multiple receipts, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the **Multi select** button.
1. Select the receipts.
1. Select the **Delete** button.
1. In the confirmation message box, select **Delete**.

You can delete one receipt at a time from the receipt's preview page. To delete one receipt, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the receipt to open the preview page.
1. Select **Discard**.
1. In the confirmation dialog box, select **Delete**.

## Attach a receipt to an expense

You can attach a receipt to an expense either directly from the **Receipts** tab or from the receipt's preview page.

To attach a receipt to an expense directly from the **Receipts** tab, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the **Attach** button.
1. Select an expense in the list.

To attach a receipt to an expense from the receipt's preview page, follow these steps.

1. On your mobile device, open the Power Apps mobile app, and then open the Dynamics 365 expense management mobile app.
1. On the **Receipts** tab, select the receipt to open the preview page.
1. Select **Attach to an expense**.
1. Select an expense in the list.
