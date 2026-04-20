---
title: Use discounts and fees in Microsoft Dynamics 365 Project Operations integrated with ERP
description: Gain a concise understanding of how discounts and fees are applied and managed in Microsoft Dynamics 365 Project Operations when integrated with ERP systems.
author: mukumarm
ms.author: mukumarm
ms.date: 12/18/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---
# Integrate Discount and Fee with ERP (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operation integrated with ERP_

This article provides an overview of the setup of the **Discount and Fee** feature in Microsoft Dynamics 365 Project Operations integrated with ERP. Discount and fee posting in **Dynamics 365 Finance** requires updates to the Project integration journal and Project invoices. Fees and discounts impact work in progress (WIP) and accrual transactions generated through the project integration journal and reverse during the project invoice posting process.

> [!NOTE]
> **Discount and fee** are applicable only to **Time and Material** billing types.

## Activate Features

To integrate Discount and Fee with ERP, activate the following features:

- **Enable line discounts and additional fee for non-stocked/resource based scenarios** in Dynamics 365 Finance
- **Enable Discount and Fee** in Dynamics 365 Project Operations

### Minimum version requirement

To use the feature for Project Operations integrated deployments, you must have the following versions:

- **Project Operations Dataverse version** 4.145.0.x or later
- **Dynamics 365 Finance version** 10.0.45 (10.0.2345.41) or later

### Run dual-write maps

This section provides information about the specific maps that are required for this feature.

| Dual-write map                                   | Version   |
|--------------------------------------------------|-----------|
| Project operations integration actuals (msdyn_actuals) | 1.0.0.21  |

## Fee

For **fee**, the system creates a new integration journal line of the **Fee** type, linked to the source record—such as **time, expense, or material** actuals. During posting, the system uses the default fee category configured in the **Project management and accounting parameters**.

During the **Project integration journal** posting process, WIP and accrual transactions are generated based on the configured **cost and revenue profiles**.

Once the **project invoice** is generated, fee transactions linked to the source documents—such as time, expense, or material actuals automatically become part of the main invoice proposal lines. Tax amounts are also posted financially, based on the sales tax group and item sales tax group configurations.

> [!NOTE]
> During the invoice line generation process using **Import from staging**, if fee transactions are expected on the invoice proposal lines but aren't successfully posted through the Project integration journal, the system doesn't generate the corresponding project invoice proposal lines. Instead, it logs an error message indicating the issue.

## Discount

For **discounts**, depending on the organization's policy, the discount either reduces the revenue during financial posting or is posted separately, allowing the full revenue to be recognized for the project.

### Project management and accounting parameters

According to the organization's policy, if discounts must be posted separately and aren't deducted from project revenue accounts/ The **Discount category** field is available in the **Project management and accounting parameters**. This field helps identify the appropriate ledger account for posting discount amounts independently.

1. Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. Go to **Project Operations on Dynamics 365 customer engagement** tab.
1. In the **Project category defaults** group, select fee type category in the **Line discount** field.

### Project integration journal

During the project integration journal posting process, if the **Line discount** field is enabled in the **Project management and accounting parameters**, the system posts the sales amount without considering the discount. WIP and accrual financial transactions are then generated accordingly.

If the **Line discount** field isn't enabled in the **Project management and accounting parameters**, the system posts the sales amount after deducting the discount amount. WIP and accrual financial transactions are then generated accordingly.

### Project invoice

On the project invoice proposal lines, a new field **Line discount** displays the applicable discount amount. Based on the configuration for discount posting, the system generates project invoice financials accordingly. If the discount is to be posted separately without impacting project revenue, the discount ledger account is derived from the **Invoice revenue** type account defined in the project ledger posting setup.

The sales tax amount is calculated after deducting the discount from the sales amount.

Learn more about project discount and fee in [Manage discount and fee in Project operations](manage-discount-fee-calculations.md).

Learn more about project invoices in [Proforma project invoices](../pro/proforma-invoicing/create-manual-proforma-invoice-sales.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
