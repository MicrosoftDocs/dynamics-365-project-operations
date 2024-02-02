---
title: Subcontract purchase orders
description: This article explains how to manage or integrate the Subcontract to Purchase order process, and use a three-way matching process for subcontract vendor invoices.
author: mukumarm
ms.date: 02/02/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Dynamics 365 Subcontract purchase orders overview

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios.

This article presents an overview of the subcontracting feature in Project Operations that is seamlessly integrated with Dynamics 365 Finance. This functionality enables users to generate subcontracts, document timesheets, expenses, and other pertinent information provided by subcontractors within Dataverse. For every subcontract, the system automatically generates purchase orders in Dynamics 365 Finance. Likewise, for each recorded timesheet or expense in Dataverse, the system generates corresponding product receipts in Dynamics 365 Finance. When a subcontractor submits an invoice in Dynamics 365 Finance, the accounts payable clerk gains access to all recorded timesheets and expenses associated with the subcontract. This facilitates the accounts payable clerk in conducting a three-way matching process and successfully booking the invoice in Dynamics 365 Finance.

## Prerequisites

To utilize this functionality, activate the following features.
- Enable **Subcontract actuals processing** with Project Operations for resource based/non-stocked scenarios.
- Enable **Project purchase orders** on Project Operations for resource based/non-stocked scenarios.
- Enable **Subcontract purchase orders** on Project Operations for resource based/non-stocked scenarios.

### Minimum version required

To use this feature for Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios, the following versions are required:

- **Project Operations Dataverse** version 4.91.0.0 or later.
- **Dynamics 365 Finance** version 10.0.39 or later.
  
## Set default procurement categories and project categories for subcontract lines

To generate purchase order lines in Dynamics 365 Finance for each subcontract line that is created in Dataverse, it's essential to configure default procurement categories and project categories. This configuration should be based on the roles or expense details specified in the subcontract line. 

To set up the default procurement categories and project categories, follow these steps.

1. In **Dynamics 365 Finance**, go to **Project management and accounting** > **Setup** > **Categories** > **Project subcontract categories**.
1. Select **New** to create a new record.
1. Select **Hour** for time, or **Expense** for expenses in the **subcontract transaction type** field.
1. Select **Role ID** for time, or **Transaction category** for expenses. This step is optional and required only if setup is required for certain **transaction category** or **Role ID**.
1. Select the **Procurement category** for the mapping.
1. Select the **Project category** for the mapping.

## Set number sequence for product receipt

When timesheet entries or expenses are logged in Dataverse, Dynamics 365 Finance automatically generates and posts the product receipt for the subcontract purchase order through the periodic processes **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt**. To facilitate the automatic generation of product receipts, it's necessary to configure a number sequence. 

To set up the number sequence for subcontract product receipts, follow these steps.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Project management and accounting parameters**.
1. Select the **Number sequence** tab.
1. Select the **Product receipt** reference and select the number sequence for subcontract **product receipt**. 

## Set Dual-write maps

For the automatic generation of purchase orders and purchase order lines in **Dynamics 365 Finance** for each subcontract in **Dataverse**, the Dual-write maps must be in the running stage. The following is a list of Dual-write maps and respective map versions that need to be in the running stage:

1. Project Operations integration actuals (msdyn_actuals) - 1.0.0.18
1. Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices) - 1.0.0.7
1. Project subcontract purchase order header (msdyn_subcontracts) - 1.0.0.0
1. Project subcontract purchase order line (msdyn_subcontractlines) - 1.0.0.0

## Create and manage subcontracts

After you create a subcontract in Dataverse, a corresponding purchase order is generated in Dynamics 365 Finance for each subcontract. Additionally, for every subcontract line in Dataverse, a purchase order line is created. Using the **Project Subcontract Category mapping** outlined earlier, the system identifies the **procurement category** and **project category** for each purchase order line. 

Purchase orders are automatically confirmed in Dynamics 365 Finance after confirmation of the subcontract in Dataverse. Any modifications made to the subcontract or its lines in Dataverse are seamlessly updated in Dynamics 365 Finance, thereby reflecting changes in the **purchase order status** in Dynamics 365 Finance.

It's important to note that creating subcontract purchase orders directly in Dynamics 365 Finance is restricted.

To create and manage the subcontracts in Dataverse, see [Subcontract management in Project Operations](../../pro/subcontracting/key-concepts-subcontracting.md).

To view the list of subcontract purchase orders in **Dynamics 365 Finance**, follow these steps.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Item tasks** > **Subcontract purchase orders**.
1. Select the **purchase order** to view the purchase order details. All the fields on the purchase orders are noneditable.
1. Select the **Header** tab of the **purchase order**.
1. On the **General** tab, the **Subcontract** details like **Subcontract ID**, **Subcontract name**, **Subcontract date**, and **Subcontract status** is available.
1. Select the **Lines** tab of the **purchase order**.
1. The **Lines** tab shows the list of the purchase order lines created for each subcontract line.
1. A **Dynamics 365 Finance** purchase order line is generated for every **subcontract line** in Dataverse.
1. Procurement categories are used for **expense** and **time** transaction line types, with these categories being derived from the **project subcontract mapping**. **Item sales tax** groups are defaulted from the **procurement categories** setup.
1. **Material** type transactions utilize **released products**, with default settings assigning **site** and **warehouse** from the **default order settings**. Additionally, **project categories** and **item sales tax groups** are defaulted from the released products form.
1. On the **Project** tab, Subcontract line details like subcontract line ID, type and role ID is available.
1. Select the **Receipt** action pane on the purchase order form.
1. On the **Journal** section, list of product receipts posted for the purchase order. **Product receipts** for subcontract purchase orders posted automatically based upon timesheet and expenses recorded in **Dataverse**. Manual product receipts aren't allowed for subcontract purchase orders.

## Generate product receipt for subcontracts

When a timesheet entry or expenses are logged in Dataverse, Dynamics 365 Finance will automatically produce and post the product receipt for the subcontract purchase order through the periodic processes: **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt**. 

To **generate product receipts** for timesheets and expenses recorded by subcontractor resources or shared by subcontractors in **Dataverse**, follow these steps.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Periodic** > **Subcontracts** > **Generate product receipt for subcontracts**.
1. Select **Generate product receipt for subcontracts** to generate the product receipt. This activity can be executed on periodic basis using batch process. It's recommended to run this process in batch mode on daily basis.
1. Dynamics 365 Finance considers all the timesheet entries, expenses and materials approved in **Dataverse** for the subcontract using timesheet, expenses, Material usage or journal entries.
1. After posting the **Project integration journal** for all entries, the system will proceed to **generate product receipts** for subcontract purchase orders. Each **accounting date** utilized for journals is taken into account during the product receipt generation process. If multiple entries have been posted through the **Project integration journal** with different accounting dates, **multiple product receipts** will be generated, each corresponding to its respective accounting date.
1. In Dynamics 365 Finance, go to **Project management and accounting** > **Sub contracts** > **Project subcontracts product receipts** to view the list of product receipts along with the posted status.

## Post product receipt for subcontracts

To post the **subcontract product receipts**, follow these steps.

1. In **Dynamics 365 Finance**, go to **Project management and accounting** > **Periodic** > **Subcontracts** > **Post product receipt for subcontracts**.
1. Select **Post product receipt for subcontracts** to post the product receipt. This activity can be executed on periodic basis using batch process. It's recommended to run this process in batch mode on daily basis.
1. On alternate basis, In **Dynamics 365 Finance**, go to **Project management and accounting** > **Sub contracts** > **Project subcontracts product receipts** to view the list of product receipts along with the posted status. Select the **product receipt** and select **Post** to post the product receipt.
1. System will generate the Product receipt financial voucher if as per **Purchasing policy**, Product receipt accrual is configured for **procurement categories**.

## Create and post subcontract vendor invoices

When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in **Dynamics 365 Finance**.

To create and post subcontract vendor invoices, follow these steps.

1. In Finance, go to **Accounts payables** > **Purchase orders** > **All purchase orders**.
1. On the **Invoice** Action Pane, select **invoice** to create a vendor invoice for subcontract purchase order.
1. On the **Default from** Action pane, Select **Product receipt quantity** as an option. It will display the purchase order lines with the product receipt quantity.
1. Enter the **Invoice number** and **invoice date**.
1. Select **Post** to post the vendor invoice.

Upon posting the vendor invoice, **synchronization** with **Dataverse** occurs, and an automatic **confirmation** is executed for the vendor invoices in **Dataverse**. Within **Dataverse**, the system initiates an **automatic matching** process for **vendor invoice lines** and the **original timesheet or expense entries** associated with subcontracts. This process involves generating a **reversal** entry for the original record and subsequently creating a new entry for the vendor invoice line in the **Actual** entity.
   
[!INCLUDE[footer-include](../../includes/footer-banner.md)]


