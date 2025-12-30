---
title: Create vendor invoices
description: This article describes the concept of vendor invoices and explains how to create them in Microsoft Dynamics 365 Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create vendor invoices

_**Applies To:** Project Operations Integrated with ERP_

To use the functionality that's described in this article, you must enable the **Enable subcontract actuals processing with Project Operations for resource based scenarios** feature in the **Feature management** workspace.

Vendor invoicing in Microsoft Dynamics 365 Project Operations can be used to record costs from deliveries of services and/or materials on a project that's completed by vendors.

When services and/or materials are subcontracted to a vendor, a subcontract represents the contractual agreement with that vendor. As the vendor delivers the services, or as the materials are received and used on project tasks, costs are recorded on the project. The vendor then periodically sends invoices. Those invoices are verified and matched with costs that are recorded on the project. After the verification process is completed, the vendor invoice is confirmed and released for payment.

## Scenarios for use

Vendor invoices in Project Operations can be used to support two distinct scenarios:

- Customers use the full subcontracting experience.
- Customers don't use the full subcontracting experience but want to have a unified view of costs on projects in Project Operations.

### Customers use the full subcontracting experience

The vendor invoice experience provides a way to verify time entries, material usage, and expense entries that reference subcontracted components, and match them with vendor invoice lines. This process can be used to verify the accuracy of the vendor invoice lines. After the verification process is completed and the vendor invoice is confirmed, the system reverses the actuals that were recorded by approved time, expense, and material usage logs. It then creates new cost actuals by using the vendor invoice lines.

### Customers don't use the full subcontracting experience but want to have a unified view of costs on projects in Project Operations

If you're tracking the subcontract process in a third-party system, you can record costs from that third-party system to Project Operations by creating vendor invoices that don't reference subcontracts. In this way, your project managers can have a single, unified view of all costs on a given project.

## Create vendor invoices in Project Operations

Vendor invoices are created in Dynamics 365 Finance, by using the **Accounts payable** module. You can't create vendor invoices directly in Dataverse.

### Set up vendor invoice verification

If a vendor invoice is intended for a subcontract in Dataverse, you must enable the **Manual verification by PM is required** parameter. The header of project vendor invoices includes an option of the same name. By default, the option on the header of every vendor invoice is set to the value that you set on the **Project management and accounting parameters** page. However, you can update the value as required on the header of individual vendor invoices.

The setting of the option determines whether the vendor invoice should be automatically confirmed in Dataverse, or whether it requires manual confirmation.

- If the option is set to **Yes**, the vendor invoice that's created in Finance and synced to Dataverse has **Draft** status. The invoice must then be validated and verified by the project manager, and confirmed, before it's processed and posted to the specific project and ledger accounts in Finance.
- If the option is set to **No**, the vendor invoice is automatically confirmed. No further action is required.

To set up vendor invoice verification, follow these steps:

1. In Finance, go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **Financial** tab, set the **Manual verification by PM is required** option to **Yes** if company policy requires verification of subcontractor vendor invoices. If verification by the project manager isn't required in Dataverse, leave the option set to **No**. By default, the setting will be used on the **Pending vendor invoice** page.

> [!NOTE]
> Vendor invoices that are created for subcontracts in Dataverse can be processed correctly only if the **Manual verification by PM is required** option is set to **Yes**. Time, material, and expense cost actuals that subcontractors create can be manually matched with vendor invoice lines by the project manager only if this option is set to **Yes**.

### Set up a procurement integration account for vendor invoices

When a vendor invoice is posted in Finance for Project Operations – Integrated environment (non-stock), financials are posted to the Procurement integration account. The system generates the actuals in Dataverse for the posted invoice. Those actuals are posted in Finance by using the Project integration journal. Posting of the Project integration journal posts the actual cost and reverses the Procurement integration account.

To set up a Procurement integration account for vendor invoices, follow these steps:

1. In Finance, go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **Project operations on Dynamics 365 customer engagement** tab, select **Materials** \> **Procurement integration account**.

### Create and post subcontract vendor invoices

When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in Finance.

1. In Finance, go to **Accounts payables** \> **Invoices** \> **Pending vendor invoices**.
1. On the Action Pane, select **New** to create a vendor invoice.
1. On the invoice header, in the **Invoice account** field, select **Subcontractor**.
1. Select the invoice date.
1. On the **Header** tab, set the **Manual verification by PM is required** option to **Yes**. The default setting of this option comes from the **Project management and accounting parameters** page. However, it can be changed at vendor invoice level.
1. On the **Invoice line** FastTab, select **Add line** to create a vendor invoice line.
1. Select the procurement category that was created for subcontract lines, and enter the unit price, unit of measurement, and quantity.
1. In the vendor invoice lines section, on the **Project** tab, select the project that the subcontractor shares the subcontract invoice against.
1. Select the project category. It can be of any type (**Item**, **Expense**, **Materials**, or **Hours**).
1. If the selected project category is of the **Hour** type, select the role.
1. Select **Post** to post the vendor invoice.

Alternatively, you can create a vendor invoice by going to **Accounts payable** \> **Invoices** \> **Open vendor invoices** and selecting **New**.

When the vendor invoice is posted, it becomes available in Dataverse for project manager verification and processing.

## Vendor invoice processing in Dataverse

In the vendor invoice that's created in Dataverse, some field values come from the vendor invoice that's recorded in Finance. Other values are default values that come from the subcontract.

The following fields and related records will be copied from the subcontract to the header of the vendor invoice:

- Currency
- Contracting unit
- Payment terms

On the vendor invoice lines, Project Operations uses the following field values to enter the default subcontract and subcontract line reference:

- Transaction class
- Role
- Transaction category
- Product fields
- Project
- Task

> [!NOTE]
> Fixed-price subcontract lines aren't supported in Project Operations.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
