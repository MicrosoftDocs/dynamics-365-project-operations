---
title: Manage discounts and fees overview
description: Get an overview of discounts and fees in Microsoft Dynamics 365 Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 09/23/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---
# Manage discounts and fees overview

_**Applies To:** Lite deployment - deal to proforma invoicing._

This article provides an overview of the setup of the **Discount and Fee** feature in Microsoft Dynamics 365 Project Operations. In some cases, discounts might apply to the contracts that organizations enter into with customers. Alternatively, organizations might choose to charge extra fees, such as administrative fees. Project Operations lets you define discount percentages and fee percentages at the level of the project quotation or the contract line. When a transaction is generated and approved, the system applies the appropriate discount or fee, based on the contract line setup. It then updates the actuals accordingly. This feature is applicable to **Time and Material** business processes.

> [!NOTE]
> **Discount and fee** are applicable only to **Time & Material** billing types.
> Once the **Discount and fee** feature is enabled, it cannot be disabled because transactions may have been processed based on the applied discount or fee percentage.

## Prerequisites

To use discounts and fees in Project Operations, enable the **Discount and Fee** feature in the system.

## Project quotations

Project quotations can be created and shared with customers, and they can include one or more quotation lines that are tailored to business needs. For project quotation lines of the **Time and Material** type, **Discount percentage** and **Fee percentage** fields are available for editing. The discounts and fees are applied to all quotation line details of the selected quotation line. The extended amount on the project quotation line reflects the discounts and fees, based on the percentages that are entered. The discount amount is deducted from the total on the quotation line, whereas the fee amount is added to it.

To apply discounts and fees for project quotations, follow these steps.

1. Go to **Sales** \> **Sales** \> **Quotes**.
1. Select **New** to create a project quotation.
1. Set the **Name**, **Prospect or Customer**, and **Organization unit** fields, and provide other mandatory details.
1. On the **Quote lines** tab, select **Add New Quote line** to create a project quotation line.
1. Set the **Name** field.
1. In the **Billing method** field, select **Time and Material**.

    **Discount percentage** and **Fee percentage** fields appear on the page.

1. In the **Quoted amount** field, you can manually enter a value. Alternatively, create quotation line details on the **Quote Line Details** tab.
1. Set the **Discount percentage** field and/or the **Fee percentage** field.

    **Discount amount**, **Fee amount**, and **Extended amount** values are calculated based on the specified discount percentage and fee percentage.

1. Select **Save and Close** to close the quotation line page.

    The **Profitability Analysis** and **Total Revenue** fields are updated to reflect the discount and fee amounts.

Learn more about project quotations in [Manage project quotes](../pro/sales/manage-quotes-sales.md).

## Project contracts

Project contracts can be created manually or by using project quotations, based on the agreements with customers. They can include one or more contract lines that are tailored to business needs. For project contract lines of the **Time and Material** type, **Discount percentage** and **Fee percentage** fields are available for editing. The discounts and fees are applied to all contract line details of the selected contract line. The extended amount on the project contract line reflects the discounts and fees, based on the percentages that are entered. The discount amount is deducted from the total on the contract line, whereas the fee amount is added to it.

When a project contract is created through the project quotation process, the discount and fee percentage values from the project quotation lines are automatically applied to the project contract lines, if any are available.

To apply discounts and fees to project contracts, follow these steps.

1. Go to **Sales** \> **Sales** \> **Project Contracts**.
1. Select **New** to create a project contract.
1. Set the **Name**, **Customer**, and **Organization unit** fields, and provide other mandatory details.
1. On the **Contract lines** tab, select **Add New Contract line** to create a project contract line.
1. Set the **Name** and **Project** fields.
1. In the **Billing method** field, select **Time and Material**.

    **Discount percentage** and **Fee percentage** fields appear on the page.

1. In the **Contract amount** field, you can manually enter a value. Alternatively, create contract line details on the **Project Contract Line Details** tab.
1. Set the **Discount percentage** field and/or the **Fee percentage** field.

    **Discount amount**, **Fee amount**, and **Extended amount** values are calculated based on the specified discount percentage and fee percentage.
 
1. Select **Save and Close** to close the contract line page.

    The **Contract performance** and **Total Amount** fields are updated to reflect the discount and fee amounts.

Learn more about project contracts in [Manage project contracts](../pro/sales/manage-contracts-sales.md).

## Actuals

Actuals capture the results of all transactions that are performed or generated in Project Operations. They can be created or updated through timesheets, expenses, material usage, journals, or project invoice processes. When timesheets, expenses, or material usage is approved, or when journals are confirmed for a contract that has applicable discounts and/or fees associated with it, the system generates actuals of the **Unbilled Sales** type. It also updates the discount and fee amounts as appropriate. In addition, the extended amount is adjusted to account for the discounts and fees. The discount amount is deducted from the extended amount, whereas the fee amount is added to it.

Learn more about actuals in [Actuals impact in a time and materials engagement](../actuals/ActualsonTM.md).

## Project invoices

Project invoices are used to bill customers, and they can include one or more invoice lines. When you create an invoice for **Time and Material** transactions, if **Unbilled Sales** transactions that have discounts and fees are selected, the system generates an invoice where the lines reflect the discount and fee amounts. The invoice lines include separate fields for the discount and fee amounts. If the **Invoice line details** option is used to change the quantity, the discount and fee amounts are adjusted accordingly. After the project manager confirms the invoice, the **Unbilled Sales** actuals are reversed with negative discount and fee amounts. New **Billed Sales** actuals are then generated that reflect the updated discount and fee.

Learn more about project invoices in [Proforma project invoices](../pro/proforma-invoicing/create-manual-proforma-invoice-sales.md).
