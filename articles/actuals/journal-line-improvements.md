---
title: Journal line improvements
description: This article provides information about journal lines improvement feature in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 09/19/2024
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---
# Journal line improvements

_**Applies To:** Lite deployment - deal to proforma invoicing_

This feature helps prevent you from entering incorrect **journal line** entries by enforcing **business rules**. It introduces new **validations** and automatically fills in dependent values based on the **transaction class** and **type**. This feature aims to enhance the **Quick create form** on the journal lines by adding validations and default logic for fields, as well as improving the display of fields, ensuring users enter data correctly.

## Prerequisites
To use the journal line improvements feature in Dynamics 365 Project Operations, enable the feature **Enable journal line improvements** feature within the system.

## Business rules
Business rules have been implemented on the journal lines as part of this feature to ensure data accuracy and integrity. The following are the business rules:

| Billing method on contract line | Transaction type | Transaction classes allowed |Transaction classes not allowed |
 | --- | --- | --- | --- |
 | Fixed Price | Cost | Time, Expense, Material | Fee, Retainer and Milestone |
 |  | Unbilled sales | Retainer | Time, Expense, Material, Fee and Milestone |
 |  | Billed sales | Retainer and Milestone | Time, Expense, Material, Fee |
 |  | Inter Org Sales | Time, Expense | Material, Fee, Retainer and Milestone |
 |  | Resource unit cost | Time, Expense | Material, Fee, Retainer and Milestone |
 | Time & Material | Cost | Time, Expense, Material | Fee, Retainer and Milestone |
 |  | Unbilled sales | Time, Expense, Material, Fee, Retainer | Milestone |
 |  | Billed sales | Time, Expense, Material, Fee, Retainer | Milestone |
 |  | Inter Org Sales | Time, Expense | Material, Fee, Retainer and Milestone |
 |  | Resource unit cost | Time, Expense | Material, Fee, Retainer and Milestone |

## Defaulting and field visibility setting for quick create journal line
The **Quick Create journal line** entry form is optimized to display fields that are relevant to the user, based on the transaction class and type. Additionally, defaulting logic has been applied to fields to ensure that journal lines can be created efficiently. All fields are available for modification on the detail page if necessary.

| Journal line field | Display on quick create |Default value|
| --- | --- | --- |
| Product |This field will be visible only for **Transaction class** is **Material** | |
| External description | No |This field will defaulted from the **Description** field. |
| Document date | No | This field will be defaulted from the **Transaction date field** |
| Start date | No | This field will be defaulted from the **Transaction date field** |
| End date | No | This field will be defaulted from the **Transaction date field** |
| Accoutning date | No | This field will be defaulted from the **Transaction date field** |
| Contract line customer | Yes  | This field will be defualted based upon **Contract line** associated with project and **Task**.  |
| Role | Role will be visible only for  **Transaction class** is **Time**  |  |
| Unit schedule | No | This field will be defualted based upon **Unit** |
| Bookable resource | This field will be displayed only for **Transaction class** **Time** and **Expense**  |  |
| Amount method | No  |  |
