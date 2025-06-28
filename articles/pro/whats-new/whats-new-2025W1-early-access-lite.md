---
title: What's new 2025 wave 1 early access - Project Operations Core deployment
description: Learn about the features available in the 2025 Wave 1 early access release of Project Operations Core deployment.
author: mohitmenon
ms.custom:
  - evergreen
ms.date: 03/11/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# What's new 2025 wave 1 early access - Project Operations Core deployment

_**Applies To:** Core deployment - deal to proforma invoicing_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.131.0.74

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Estimates | **Project estimate updates** <br><br> This feature includes label changes at the project level where the original Estimates tab shows Time-phased estimates, and the newly labeled Estimates tab is a consolidated view of expense and material estimates. The new grid for expense and material estimates allows easy creation and editing of those estimates. You can view cost and sales amounts in one line. | [Financial Estimates on projects](../../project-management/create-expense-estimates.md) |

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Sales |**Modern Quote Update** <br><br> This feature enhances the quote management experience with a unified grid interface, allowing users to seamlessly add or edit quote line details with fewer clicks. Key information such as cost details, customer schedules, margins, role price override, and budgets are now accessible within each quote line.| [New Quote Form Experience](../../sales/quotes-new-form.md) |
| Invoicing |**Customizing Billing hub** <br><br> This feature lets you customize billing hub for invoicing.| [Customize billing hub](../../proforma-invoicing/billing-hub-customization.md) |

## Critical updates in this release

| **Feature area** | **Issue Name** | **Issue Description** | **Fix implemented** |
| --- | --- | --- | --- | 
| Actuals | Updates to creation of actuals | Creating or updating actuals manually or by unsupported methods can affect the financial integrity of the system. | The newly added validation prevents creating or updating actuals using unsupported methods. Learn more in [Create or update actuals](../../actuals/create-update-actuals.md). |
