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

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

This article presents an overview of the **subcontracting** feature seamlessly integrated with **D365 Finance**. This functionality enables users to generate subcontracts, document timesheets, expenses, and other pertinent information provided by subcontractors within **Dataverse**. For every subcontract, the system automatically generates purchase orders in **D365 Finance**. Likewise, for each recorded timesheet or expense in **Dataverse**, the system generates corresponding product receipts in **D365 Finance**. When the subcontractor submits an invoice in **D365 Finance**, the accounts payable clerk gains access to all recorded timesheets and expenses associated with the subcontract. This facilitates the accounts payable clerk in conducting a three-way matching process and successfully booking the invoice in **D365 Finance**.

To utilize this functionality, it is necessary to activate the below **features**:
1. Enable subcontract actuals processing with Project Operations for resource based scenarios
2. Enable project purchase orders on Project Operations for resource based/non-stocked scenarios.
3. Enable subcontract purchase orders on Project Operations for resource based/non-stocked scenarios.

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
1. In **D365 Finance**, go to **Project management and accounting** > **Project management and accounting parameters**>.
2. Click on **Number sequence** tab.
3. Select the **Product receipt** reference and select the number sequence for subcontract **product receipt**. 

## Set Dual write maps
For the automatic generation of purchase orders and purchase order lines in D365 Finance for each subcontract, the Dual Write maps must be in the running stage. The following is a list of Dual Write maps that need to be in the running stage:

1. Project Operations integration actuals (msdyn_actuals) - 1.0.0.17
2. Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices)
3. Project subcontract purchase order header (msdyn_subcontracts)
4. Project subcontract purchase order line (msdyn_subcontractlines)



