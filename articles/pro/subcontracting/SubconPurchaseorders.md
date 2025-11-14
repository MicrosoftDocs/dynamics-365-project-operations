---
title: Subcontract purchase orders overview
description: This article explains how to manage or integrate the Subcontract to Purchase order process and use a three-way matching process for subcontract vendor invoices.
author: mukumarm
ms.date: 02/02/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Subcontract purchase orders overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP._

This article presents an overview of the subcontracting feature in Microsoft Dynamics 365 Project Operations that's seamlessly integrated with Dynamics 365 Finance. This feature lets users generate subcontracts, document timesheets, and expenses, and other relevant information that subcontractors provide, in Dataverse. For every subcontract in Dataverse, the system automatically generates purchase orders in Finance. Likewise, for every recorded timesheet or expense in Dataverse, the system generates corresponding product receipts in Finance. When a subcontractor submits an invoice in Finance, the Accounts payable (AP) clerk gains access to all recorded timesheets and expenses that are associated with the subcontract. The AP clerk can then perform a three-way matching process and book the invoice in Finance.

## Prerequisites

To use the functionality, activate the following features:

- **Enable Subcontract actuals processing with Project Operations for resource based/non-stocked scenarios**
- **Enable Project purchase orders on Project Operations for resource based/non-stocked scenarios**
- **Enable Subcontract purchase orders on Project Operations for resource based/non-stocked scenarios**

### Minimum versions required

To use the feature for Project Operations Integrated with ERP, you must have the following versions:

- **Project Operations Dataverse** version 4.91.0.0 or later
- **Dynamics 365 Finance** version 10.0.39 or later

## Set up default procurement categories and project categories for subcontract lines

To generate purchase order lines in Finance for each subcontract line that's created in Dataverse, you must configure default procurement categories and project categories. This configuration should be based on the roles or expense details that are specified on the subcontract line.

To set up the default procurement categories and project categories, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Setup** \> **Categories** \> **Project subcontract categories**.
1. Select **New** to create a record.
1. In the **Subcontract transaction type** field, select **Hour** for time or **Expense** for expenses.
1. Optional: Select **Role ID** for time or **Transaction category** for expenses.

    > [!NOTE]
    > This step is required only if setup is required for a specific transaction category or role ID.

1. Select the procurement category for the mapping.
1. Select the project category for the mapping.

## Set up a number sequence for product receipts

When timesheet entries or expenses are logged in Dataverse, Finance automatically generates and posts the product receipt for the subcontract purchase order through the **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt** periodic processes. To facilitate the automatic generation of product receipts, you must configure a number sequence.

To set up the number sequence for subcontract product receipts, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Project management and accounting parameters**.
1. On the **Number sequence** tab, select the **Product receipt** reference, and then select the number sequence for subcontract product receipts.

## Set up dual-write maps

Before purchase orders and purchase order lines in Finance can be automatically generated for each subcontract in Dataverse, the following dual-write maps must be in the running stage.

| Required dual-write map | Required version |
|---|---|
| Project Operations integration actuals (msdyn\_actuals) | 1.0.0.18 |
| Project Operations integration project vendor invoice export entity V2 (msdyn\_projectvendorinvoices) | 1.0.0.0 |
| Project Operations integration project vendor invoice line export entity (msdyn\_projectvendorinvoicelines) | 1.0.0.7 |
| Project subcontract purchase order header (msdyn\_subcontracts) | 1.0.0.0 |
| Project subcontract purchase order line (msdyn\_subcontractlines) | 1.0.0.0 |

> [!Note]
> The **Language** field in the Purchase Order header is **mandatory** in Finance and Operations but does **not exist** in Dataverse.  
>  
> This field is automatically populated from the Vendor’s **Language** setting in Finance and Operations. 
>  - Ensure the **Language** field for vendor is set to a valid value.  
>  - Navigate to **Finance and Operations** > **Procurement and sourcing** > **Vendors** > **All vendors**.  
 

## Create and manage subcontracts

After you create a subcontract in Dataverse, a corresponding purchase order is generated for it in Finance. Additionally, for every subcontract line in Dataverse, a purchase order line is created. The system uses the project subcontract category mapping that was outlined earlier to identify the procurement category and project category for each purchase order line.

After the subcontract is confirmed in Dataverse, purchase orders are automatically confirmed in Finance. If the subcontract or its lines are changed in Dataverse, the purchase orders are seamlessly updated in Finance. Therefore, the purchase order status in Finance reflects any changes.

> [!IMPORTANT]
> The creation of subcontract purchase orders directly in Finance is restricted.

For information about how to create and manage subcontracts in Dataverse, see [Subcontract management in Project Operations](../../pro/subcontracting/key-concepts-subcontracting.md).

To view the list of subcontract purchase orders in Finance, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Item tasks** \> **Subcontract purchase orders**.
1. Select the purchase order to view its details. None of the fields are editable.
1. Select the **Header** tab of the purchase order.

    The **General** tab shows the details of the subcontract, such as the subcontract ID, name, date, and status.

1. Select the **Lines** tab of the purchase order.

    The **Lines** tab lists the purchase order lines that were created for each subcontract line. A purchase order line is generated in Finance for every subcontract line in Dataverse.

    - Transaction lines of the **Expense** and **Time** types use procurement categories. These categories are derived from the project subcontract mapping. Default item sales tax groups are taken from the procurement categories setup.
    - Transaction lines of the **Material** type use released products. A site and a warehouse are assigned from the default order settings. Additionally, default project categories and item sales tax groups are taken from the released products page.

    The **Project** tab shows the details of the subcontract line, such as the subcontract line ID, type, and role ID.

1. On the Action Pane, select **Receipt**.

    The **Journal** section lists the product receipts that were posted for the purchase order. Product receipts for subcontract purchase orders are automatically posted based on timesheets and expenses that are recorded in Dataverse. Manual product receipts aren't allowed for subcontract purchase orders.

## Generate product receipts for subcontracts

When timesheet entries or expenses are logged in Dataverse, Finance automatically generates and posts the product receipt for the subcontract purchase order through the **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt** periodic processes.

To generate product receipts for timesheets and expenses that subcontractor resources record or subcontractors share in Dataverse, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Periodic** \> **Subcontracts** \> **Generate product receipt for subcontracts**.
1. Select **Generate product receipt for subcontracts** to generate the product receipt. You can use a batch process to perform this activity on a periodic basis. We recommend that you run this process in batch mode every day.

    Finance uses the timesheet, expenses, material usage, or journal entries to consider all the timesheet entries, expenses, and materials that were approved in Dataverse for the subcontract.

    After the Project integration journal for all entries is posted, the system generates product receipts for subcontract purchase orders. During the product receipt generation process, the system considers each accounting date that's used for journals. If multiple entries were posted through the Project integration journal, but they have different accounting dates, multiple product receipts are generated. Each product receipt corresponds to the appropriate accounting date.

1. In Finance, go to **Project management and accounting** \> **Sub contracts** \> **Project subcontracts product receipts** to view the list of product receipts together with the posted status.

## Post product receipts for subcontracts

To post the subcontract product receipts, follow one of these steps in Finance.

- Go to **Project management and accounting** \> **Periodic** \> **Subcontracts** \> **Post product receipt for subcontracts**, and select **Post product receipt for subcontracts** to post the product receipt. You can use a batch process to perform this activity on a periodic basis. We recommend that you run this process in batch mode every day.
- Go to **Project management and accounting** \> **Sub contracts** \> **Project subcontracts product receipts** to view the list of product receipts together with the posted status. Select the product receipt, and then select **Post** to post it.

In both cases, the system generates the Product receipt financial voucher if product receipt accrual is configured for procurement categories, in accordance with the purchasing policy.

## Create and post subcontract vendor invoices

When an AP clerk receives an invoice from the subcontractor, a new invoice is created in Finance.

To create and post subcontract vendor invoices, follow these steps.

1. In Finance, go to **Accounts payables** \> **Purchase orders** \> **All purchase orders**.
1. On the Action Pane, on the **Invoice** tab, select **Invoice** to create a vendor invoice for the subcontract purchase order.
1. On the Action Pane, on the **Default from** tab, select **Product receipt quantity** as an option. The purchase order lines are shown together with the product receipt quantity.
1. Enter the invoice number and invoice date.
1. Select **Post** to post the vendor invoice.

When the vendor invoice is posted, synchronization with Dataverse occurs, and an automatic confirmation is done for the vendor invoices in Dataverse. In Dataverse, the system initiates an automatic matching process for vendor invoice lines and the original timesheet or expense entries that are associated with subcontracts. This matching process involves generating a reversal entry for the original record and then creating a new entry for the vendor invoice line in the **Actual** entity.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
