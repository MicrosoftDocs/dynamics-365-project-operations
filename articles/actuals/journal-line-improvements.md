---
title: Journal line improvements
description: Learn about the Journal line improvements feature in Microsoft Dynamics 365 Project Operations. This feature implements new business rules and validation to ensure accurate journal entries. It also adjusts field visibility in the Quick create journal line dialog box, based on the transaction class and type.
author: mukumarm
ms.author: mukumarm
ms.date: 09/24/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---
# Journal line improvements

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The **Journal line improvements** feature enforces *business rules* to help prevent you from entering incorrect journal line entries. It also introduces new *validations* and automatically fills in dependent values, based on the transaction class and transaction type. The purpose of this feature is to enhance the **Quick create** dialog box for journal lines by adding validations and default logic for fields, and by improving the display of fields. In this way, it helps ensure that users enter data correctly.

Learn more about journals in [Create and confirm Entry journals](create-confirm-entry-journals.md).

## Prerequisites

To use the **Journal line improvements** feature in Microsoft Dynamics 365 Project Operations, enable the **Enable journal line improvements** feature in the system.

## Business rule validation

As part of the feature, business rules are implemented on journal lines to ensure data accuracy and integrity. These business rules are applied when journal lines are created or updated through the **Quick create journal line** dialog box, Excel import, or another method for journal line insertion or update. The following table shows the business rules.

| Billing method on the contract line | Transaction type | Transaction classes that are allowed | Transaction classes that aren't allowed |
| --- | --- | --- | --- |
| Fixed Price | Cost | **Time**, **Expense**, and **Material** | **Fee**, **Retainer**, and **Milestone** |
| | Unbilled sales | **Retainer** | **Time**, **Expense**, **Material**, **Fee**, and **Milestone** |
| | Billed sales | **Retainer** and **Milestone** | **Time**, **Expense**, **Material**, and **Fee** |
| | Inter Org Sales | **Time** and **Expense** | **Material**, **Fee**, **Retainer**, and **Milestone** |
| | Resource unit cost | **Time** and **Expense** | **Material**, **Fee**, **Retainer**, and **Milestone** |
| Time & Material | Cost | **Time**, **Expense**, and **Material** | **Fee**, **Retainer**, and **Milestone** |
| | Unbilled sales | **Time**, **Expense**, **Material**, **Fee**, and **Retainer** | **Milestone** |
| | Billed sales | **Time**, **Expense**, **Material**, **Fee**, and **Retainer** | **Milestone** |
| | Inter Org Sales | **Time** and **Expense** | **Material**, **Fee**, **Retainer**, and **Milestone** |
| | Resource unit cost | **Time** and **Expense** | **Material**, **Fee**, **Retainer**, and **Milestone** |

## Defaulting and field visibility settings for the Quick create journal line dialog box

The **Quick create journal line** dialog box is optimized so that it shows only fields that are relevant to the user, based on the transaction class and transaction type. Additionally, defaulting logic is applied to fields to ensure that journal lines can be created efficiently. All fields can be modified on the details page, as required.

| Journal line field | Visibility in the Quick create dialog box | Default value |
| --- | --- | --- |
| Product | This field is visible only when the transaction class is **Material**. | |
| External description | No | The default value is the value of the **Description** field. |
| Document date | No | The default value is the value of the **Transaction date** field. |
| Start date | No | The default value is the value of the **Transaction date** field. |
| End date | No | The default value is the value of the **Transaction date** field. |
| Accounting date | No | The default value is the value of the **Transaction date** field. |
| Contract line customer | Yes | The default value is based on the contract line that is associated with the project, and on the task. |
| Role | This field is visible only when the transaction class is **Time**. | |
| Unit schedule | No | The default value is based on the value of the **Unit** field. |
| Bookable resource | This field is visible only when the transaction class is **Time** or **Expense**. | |
