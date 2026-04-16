---
title: Use financial dimensions in Expense Mobile
description: Learn how to add and manage financial dimensions while creating and submitting expenses using the Expense Mobile app.
author: ajitchandran
ms.author: ajitchandran
ms.topic: how-to
ms.date: 04/16/2026
ms.service: dynamics-365-project-operations
ms.subservice: expense-management
ms.custom: mobile
ms.reviewer: johnmichalak
---

# Use financial dimensions in Expense Mobile

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for manufacturing-based scenarios_

Financial dimensions help your organization track expenses using business-specific attributes such as **Department**, **Cost center**, **Project**, or **Location** etc.
In Expense Mobile, you can enter financial dimensions directly while creating or editing expense reports and expense lines—without switching to the web app.
This article explains how to configure, view, add, and manage financial dimensions using the Expense Mobile app.

---

## Before you begin

To use financial dimensions in Expense Mobile:
- Financial dimensions must be enabled by your organization.
- At least one financial dimension must be configured for expenses.
- The Financial Dimensions section must be visible in the mobile app.

> [!NOTE]
> If you don’t see financial dimensions in the app, contact your finance or system administrator and configure the Financial Dimensions using the below steps,
> 1. On finance and operations environment, Go to **Expense Management** > **Setup** > **General** >  **Expense Management Parameters** > **Expense mobile** > **Enable financial dimensions**
> 1. You can configure the needed Financial Dimensions that are needed to be displayed in the Expense mobile app. A minimum of 1 and maximum of 4 values can be defined.

---

## Financial dimension visibility in Expense Mobile

The **Financial dimensions** section appears in Expense Mobile only when:

- Financial dimensions are enabled for Expense Mobile, and
- Field visibility for dimensions is enabled under **Expense Management** > **Setup** > **General** >  **Expense Field visibility (Expense reports re-imagined)** > **Dimension** under Expense report and Expense have to enabled.
- If re-imagined UI is disabled, then **Expense Management** > **Setup** > **General** >  **Expense report fields** > **Dimensions** under Report heading fields and Expense line fields) will be considered.

If financial dimensions are enabled but not visible, contact your system administrator to configure the visibility of the dimension field.

---

## Add financial dimensions

You can add financial dimensions at two levels in Expense Mobile:

- **Expense report level** – Applies to the entire expense report.
- **Expense line level** – Applies only to a specific expense line.
  
---

## Add financial dimensions to an expense report

1. Open the **Expense Mobile** app.
1. Create a new expense report or open an existing one.
1. Click the vertical ellipsis (⋮) on the top right corner of the expense report and select  **Financial Dimensions**.
1. Select a value for each required dimension, such as **Department** or **Cost center** etc.
1. Each financial dimension is shown as a separate field, displaying up to 50 values by default, with the option to search for additional values by entering two or more characters.
1. Save the expense report.

---

## Add financial dimensions to an expense line

1. Open an expense report.
1. Select an existing expense line or add a new one.
1. Click the vertical ellipsis (⋮) on the top right corner of the expense line screen and select **Financial Dimensions**.
1. Select values for the available financial dimensions.
1. Each financial dimension is shown as a separate field, displaying up to 50 values by default, with the option to search for additional values by entering two or more characters.
1. Save the expense line.
  
> [!TIP]
> Use the search button by typing two or more characters to find additional financial dimension values configured but not appearing in the drop down by default.

---

## Edit financial dimensions

You can edit financial dimensions at any time **before submitting** the expense report:

- Edit report-level dimensions from **Report details**.
- Edit line-level dimensions from **Expense details**.

---

## Troubleshooting

### I don’t see financial dimensions in the app
- Financial dimensions might not be enabled for mobile use. 
- Field visibility for financial dimensions might be turned off.

Contact your system administrator for help.

---
[!INCLUDE[footer-include](../includes/footer-banner.md)]
