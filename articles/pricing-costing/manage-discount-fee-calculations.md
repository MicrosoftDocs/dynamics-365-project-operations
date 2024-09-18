---
title: Manage Discount and Fee
description: This article provides information about discount and fee overview in Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 09/17/2024
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---
# Discount and Fee overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

This article provides an overview of **Discount and Fee** setup in **Dynamics 365 Project Operations**. In some cases, organizations may enter into contracts with customers where discounts apply, or they may choose to charge additional fees, such as administrative fees. Project Operations allows you to define discount percentages and fee percentages at the project quotation or contract line level. When a transaction is generated and approved, the system applies the appropriate discount or fee based on the contract line setup and updates the actuals accordingly. This feature is applicable to **Time and Material** business processes.

> [!NOTE]
>Discount and fee are applicable only to Time & Material billing types. 

## Prerequisites
To use the discount and fee feature in Dynamics 365 Project Operations, enable the feature **Discount and Fee** feature within the system.

## Project quotations

Project quotations can be created and shared with customers, and can include one or more quotation lines tailored to business needs. For project quotation lines of the **Time and Material** type, **discount** and **fee** percentage fields are available for editing. These discounts and fees are applied to all the quotation line details details of the selected quotation line. The extended amount on the project quotation line will reflect the discount and fee, based on the entered percentages. The discount amount is deducted, while the fee amount is added to the total on the quotation line. To apply discounts and fees to project quotations, follow the steps below.

1. Go to **Sales** > **Sales** > **Quotes**.
2. Click **+ New** to create a project quotation.
3. Provide **Name**, **Prospect  or Customer**, **Organization unit** and other mandatory details.
4. Go to **quote lines** tab and Click **+ Add New Quote line** to create a new project quotation line.
5. Provide **Name** and select **Billing method** as **Time and Material**. **Discount percentage** and **fee percentage** fields will be displayed on the form.
6. Enter the **Quoted amount** manually or create quotation line details using **Quote Line Detalis** tab.
7. Enter the **Discount percentage** or/and **Fee percentage**. **Discount amount**, **Fee amount** and **Extended amount** will be calculated based upon the discount percentage and fee percentage. Click **Save and Close** to close the quotation line form.
8. The **Profitability Analysis** and **Total Revenue** fields are updated to reflect the discount and fee amounts.

For more information about **Project quotation**, refer (../articles/pro/sales/manage-quotes-sales.md)

## Project contract

Project contracts can be created manually or using project quotations based upon agreement with customers, and can include one or more contract lines tailored to business needs. For project contract lines of the **Time and Material** type, **discount** and **fee** percentage fields are available for editing. These discounts and fees are applied to all contract line details of the selected contract line. The extended amount on the project contract line will reflect the discount and fee, based on the entered percentages. The discount amount is deducted, while the fee amount is added to the total on the contract line. 

When a project contract is created through the project quotation process, the discount and fee percentage values from the project quotation lines will automatically be applied to the project contract lines, if available.

To apply discounts and fees to project contracts, follow the steps below.

1. Go to **Sales** > **Sales** > **Project Contracts**.
2. Click **+ New** to create a **Project Contract**.
3. Provide **Name**, **Customer**, **Organization unit** and other mandatory details.
4. Go to **Contract lines** tab and Click **+ Add New Contract line** to create a new project contract line.
5. Provide **Name**, select **Project**, **Billing method** as **Time and Material**. **Discount percentage** and **fee percentage** fields will be displayed on the form.
6. Enter the **Contract amount** manually or create contract line details using **Project Contract Line Details** tab.
7. Enter the **Discount percentage** or/and **Fee percentage**. **Discount amount**, **Fee amount** and **Extended amount** will be calculated based upon the discount percentage and fee percentage. Click **Save and Close** to close the contract line form.
8. The **Contract performance** and **Total Amount** fields are updated to reflect the discount and fee amounts.

For more information about **Project contract**, refer (../articles/pro/sales/manage-contracts-sales.md) for more details.

## Actuals

**Actuals** capture the results of all transactions performed or generated in **Dynamics 365 Project Operations**. They can be created or updated through **Timesheets**, **Expenses**, **Material usage**, **Journals**, or **Project invoice** processes. When **Timesheets**, **Expenses**, or **Material usage** are approved, or **Journals** are confirmed for a contract with applicable discounts and/or fees associated, the system generates **Actuals** of the type **Unbilled Sales** and updates the **Discount** and **Fee** amounts accordingly. The **Extended amount** is also adjusted to account for the **Discount** and **Fee**.  The discount amount is deducted, while the fee amount is added to the extended amount.

For more information about **Actuals**, refer (../articles/actuals/ActualsonTM.md) for more details.

## Project invoice

A **Project invoice** is used to bill the customer and may include one or more invoice lines. When creating an invoice for **Time & Material** transactions, and **Unbilled sales transactions** with discounts and fees are selected, the system generates an invoice with lines that reflect the discount and fee amounts. The invoice lines include **separate fields** for the discount and fee amounts. If there are changes to the quantity using the **Invoice line details** option, the discount and fee amounts are adjusted accordingly. Once the invoice is **confirmed** by the project manager, the **Unbilled sales** actuals are **reversed** with **negative discount and fee amounts**, and new **Billed sales** actuals are generated, reflecting the updated discount and fee.

For more information about **Project invoice**, refer (../articles/pro/proforma-invoicing/create-manual-proforma-invoice-sales.md) for more details.
