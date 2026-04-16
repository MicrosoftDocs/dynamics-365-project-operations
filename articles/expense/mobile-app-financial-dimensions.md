---
title: Use financial dimensions in Microsoft Dynamics 365 Expense Mobile
description: Learn how to add and manage financial dimensions while creating and submitting expenses using Microsoft Dynamics 365 Expense Mobile.
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

Financial dimensions help your organization track expenses by using business-specific attributes such as **Department**, **Cost center**, **Project**, or **Location**.

In Dynamics 365 Expense Mobile, you can enter financial dimensions directly while creating or editing expense reports and expense lines - without switching to the web app.

This article explains how to configure, view, add, and manage financial dimensions by using Expense Mobile.

## Before you begin

To use financial dimensions in Expense Mobile:

- Your organization must enable financial dimensions.
- You must configure at least one financial dimension for expenses.
- The mobile app must display the Financial Dimensions section.

> [!NOTE]
> If you don't see financial dimensions in Expense Mobile, contact your finance or system administrator and configure the Financial Dimensions by using the following steps:
>
> 1. On finance and operations environment, go to **Expense Management** > **Setup** > **General** >  **Expense Management Parameters** > **Expense mobile** > **Enable financial dimensions**.
> 1. Configure the financial dimensions that you want to display in the Expense mobile app. Define a minimum of one and maximum of four values.

## Financial dimension visibility in Expense Mobile

The **Financial dimensions** section appears in Expense Mobile only when all of the following conditions are true:

- You enable financial dimensions for Expense Mobile.
- You enable field visibility for dimensions under **Expense Management** > **Setup** > **General** > **Expense Field visibility (Expense reports re-imagined)** > **Dimension** under Expense report and Expense.
- If the reimagined UI is disabled, **Expense Management** > **Setup** > **General** > **Expense report fields** > **Dimensions** under Report heading fields and Expense line fields is considered.

If you enable financial dimensions but don't see them, contact your system administrator to configure the visibility of the dimension field.

## Add financial dimensions

You can add financial dimensions at two levels in Expense Mobile:

- **Expense report level** – Applies to the entire expense report.
- **Expense line level** – Applies only to a specific expense line.

## Add financial dimensions to an expense report

1. Open **Expense Mobile**.
1. Create a new expense report or open an existing one.
1. Select the vertical ellipsis (⋮) on the top right corner of the expense report and select **Financial Dimensions**.
1. Select a value for each required dimension, such as **Department** or **Cost center**.
1. Each financial dimension appears as a separate field. Each field displays up to 50 values by default, but you can search for more by entering two or more characters.
1. Save the expense report.

## Add financial dimensions to an expense line

1. Open an expense report.
1. Select an existing expense line or add a new one.
1. Select the vertical ellipsis (⋮) on the top right corner of the expense line screen and select **Financial Dimensions**.
1. Select values for the available financial dimensions.
1. Each financial dimension appears as a separate field. Each field displays up to 50 values by default, but you can search for more by entering two or more characters.
1. Save the expense line.
  
> [!TIP]
> Use the search button by typing two or more characters to find other financial dimension values that are configured but don't appear in the drop-down by default.

## Edit financial dimensions

You can edit financial dimensions at any time **before submitting** the expense report:

- Edit report-level dimensions from **Report details**.
- Edit line-level dimensions from **Expense details**.

## I don’t see financial dimensions in Expense Mobile

- The system administrator might not enable financial dimensions for mobile use.
- The system administrator might turn off field visibility for financial dimensions.

Contact your system administrator for help.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
