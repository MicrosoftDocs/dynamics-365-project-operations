---
title: Subcontract purchase orders
description: This article explains how to manage or integrate Subcontract to Purchase order process and use 3 way matching process for subcontract vendor invoices.
author: mukumarm
ms.date: 01/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Dynamics 365 Subcontract purchase orders overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios.

This article presents an overview of the **subcontracting** feature seamlessly integrated with **D365 Finance**. This functionality enables users to generate subcontracts, document timesheets, expenses, and other pertinent information provided by subcontractors within **Dataverse**. For every subcontract, the system automatically generates purchase orders in **D365 Finance**. Likewise, for each recorded timesheet or expense in **Dataverse**, the system generates corresponding product receipts in **D365 Finance**. When the subcontractor submits an invoice in **D365 Finance**, the accounts payable clerk gains access to all recorded timesheets and expenses associated with the subcontract. This facilitates the accounts payable clerk in conducting a three-way matching process and successfully booking the invoice in **D365 Finance**.

To utilize this functionality, it is necessary to activate the below **features**:
1. Enable subcontract actuals processing with Project Operations for resource based scenarios
2. Enable project purchase orders on Project Operations for resource based/non-stocked scenarios.
3. Enable subcontract purchase orders on Project Operations for resource based/non-stocked scenarios.

## Minimum version required

To use this feature for Microsoft Dynamics 365 Project Operations non-stocked/resource-based scenarios, the following versions are required:

- **Project Operations Dataverse** version 4.91.0.0 or later.
- **Dynamics 365 Finance** version 10.0.39 or later.
  
## Set default procurement categories and project categories for subcontract lines
To generate purchase order lines in D365 Finance for each subcontract line created in Dataverse, it is essential to configure default procurement categories and project categories. This configuration should be based on the roles or expense details specified in the subcontract line. 

To set up the default procurement categories and project categories, follow these steps.
1. In **D365 Finance**, go to **Project management and accounting** > **Setup** > **Categories** > **Project subcontract categories**.
2. Click **New** to create a new record.
3. Select **Hour** for time or **Expense** for expenses in the **subcontract transaction type** field.
4. Select **Role id** for time or **Transaction category** for expenses. This step is optional and required only if setup is required for certain **transaction category** or **role id**.
5. Select the **Procurement category** for the mapping.
6. Select the **Project category** for the mapping.

## Set number sequence for product receipt
When a timesheet entry or expenses are logged in Dataverse, D365 Finance will automatically genearte and post the product receipt for the subcontract purchase order through the periodic processes: **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt**. To facilitate the automatic generation of product receipts, it is necessary to configure a number sequence. 

To set up the number sequence for subcontract product receipts, follow these steps:
1. In **D365 Finance**, go to **Project management and accounting** > **Project management and accounting parameters**.
2. Click on **Number sequence** tab.
3. Select the **Product receipt** reference and select the number sequence for subcontract **product receipt**. 

## Set Dual write maps
For the automatic generation of purchase orders and purchase order lines in **D365 Finance** for each subcontract in **Dataverse**, the Dual Write maps must be in the running stage. The following is a list of Dual Write maps and respective map versions that need to be in the running stage:

1. Project Operations integration actuals (msdyn_actuals) - 1.0.0.18
2. Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices) - 1.0.0.7
3. Project subcontract purchase order header (msdyn_subcontracts) - 1.0.0.0
4. Project subcontract purchase order line (msdyn_subcontractlines) - 1.0.0.0

## Create and manage subcontracts
Upon creating a **subcontract** in **Dataverse**, a corresponding purchase order is generated in **D365 Finance** for each subcontract. Additionally, for every **subcontract line** in **Dataverse**, a **purchase order line** is created. Leveraging the **Project Subcontract Category mapping** outlined earlier, the system identifies the **procurement category** and **project category** for each purchase order line. 

Purchase orders are automatically **confirmed** in **D365 Finance** upon confirmation of the subcontract in **Dataverse**. Any modifications made to the subcontract or its lines in Dataverse are seamlessly updated in **D365 Finance**, thereby reflecting changes in the **purchase order status** in the **D365 Finance**.

It is important to note that creating subcontract purchase orders directly in D365 Finance is restricted.

Refer **[Subcontract management in Project Operations](../../pro/subcontracting/key-concepts-subcontracting.md)** to create and manage the subcontracts in **Dataverse**.

To view the list of subcontract purchase orders in **D365 Finance**, follow below steps:

1.  In **D365 Finance**, go to **Project management and accounting** > **Item tasks** > **Subcontract purchase orders**.
2.  Select the **purchase order** to view the purchase order details. All the fields on the purchase orders are non-editable.
3.  Click on the **Header** tab of the **purchase order**.
4.  On the **General** tab, **Subcontract** details like subcontract id, subcontract name, subcontract date and subcontract status is available.
5.  Click on the **Lines** tab of the **purchase order**.
6.  On the **Lines** tab, list of the purchase order lines created for each subcontract line.
7.  A **D365 Finance** purchase order line is generated for every **subcontract line** in Dataverse.
8.  Procurement categories are used for **expense** and **time** transaction line types, with these categories being derived from the **project subcontract mapping**. **Item sales tax** groups are defaulted from the **procurement categories** setup.
9.  **Material** type transactions utilize **released products**, with default settings assigning **site** and **warehouse** from the **default order settings**. Additionally, **project categories** and **item sales tax groups** are defaulted from the released products form.
10.  On the **Project** tab, Subcontract line details like subcontract line id, type and role id is available.
11.  Click on **Receipt** action pane on the purchase order form.
12.  On the **Journal** section, list of product receipts posted for the purchase order. **Product receipts** for subcontract purchase orders posted automatically based upon timesheet and expenses recorded in **Dataverse**. Manual product receipts are not allowed for subcontract purchase orders.

## Generate product receipt for subcontracts
When a timesheet entry or expenses are logged in Dataverse, D365 Finance will automatically produce and post the product receipt for the subcontract purchase order through the periodic processes: **Generate Subcontract Product Receipt** and **Post Subcontract Product Receipt**. 

To **generate product receipts** for timesheets and expenses recorded by subcontractor resources or shared by subcontractors in **Dataverse**, follow the steps outlined below:

1.  In **D365 Finance**, go to **Project management and accounting** > **Periodic** > **Subcontracts** > **Generate product receipt for subcontracts**.
2.  Click on **Generate product receipt for subcontracts** to generate the product receipt. This activity can be executed on periodic basis using batch process. It is recommened to run this process in batch mode on daily basis.
3.  **D365 Finance** will consider all the timesheet entries, expenses and materials approved in **Dataverse** for the subcontract using timesheet, expenses, Material usage or journal entries.
4.  After posting the **Project integration journal** for all entries, the system will proceed to **generate product receipts** for subcontract purchase orders. Each **accounting date** utilized for journals is taken into account during the product receipt generation process. If multiple entries have been posted through the **Project integration journal** with different accounting dates, **multiple product receipts** will be generated, each corresponding to its respective accounting date.
5.  In **D365 Finance**, go to **Project management and accounting** > **Sub contracts** > **Project subcontracts product receipts** to view the list of product receipts along with the posted status.

## Post product receipt for subcontracts
To post the **subcontract product receipts**, follow the steps outlined below:

1.  In **D365 Finance**, go to **Project management and accounting** > **Periodic** > **Subcontracts** > **Post product receipt for subcontracts**.
2.  Click on **Post product receipt for subcontracts** to post the product receipt. This activity can be executed on periodic basis using batch process. It is recommened to run this process in batch mode on daily basis.
3.  On alternate basis, In **D365 Finance**, go to **Project management and accounting** > **Sub contracts** > **Project subcontracts product receipts** to view the list of product receipts along with the posted status. Select the **product receipt** and click **Post** to post the product receipt.
4.  System will generate the Product receipt financial voucher if as per **Purchasing policy**, Product receipt accrual is configured for **procurement categories**.

## Create and post subcontract vendor invoices

When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in **D365 Finance**.

1. In Finance, go to **Accounts payables** > **Purchase orders** > **All purchase orders**.
2. On the **Invoice** Action Pane, click **invoice** to create a vendor invoice for subcontract purchase order.
3. On the **Default from** Action pane, Select **Product receipt quantity** as an option. It will display the purchase order lines with the product receipt quantity.
4. Enter the **Invoice number** and **invoice date**.
5. Select **Post** to post the vendor invoice.

Upon posting the vendor invoice, **synchronization** with **Dataverse** occurs, and an automatic **confirmation** is executed for the vendor invoices in **Dataverse**. Within **Dataverse**, the system initiates an **automatic matching** process for **vendor invoice lines** and the **original timesheet or expense entries** associated with subcontracts. This process involves generating a **reversal** entry for the original record and subsequently creating a new entry for the vendor invoice line in the **Actual** entity.
   


