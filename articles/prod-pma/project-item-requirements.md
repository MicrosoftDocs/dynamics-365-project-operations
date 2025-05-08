---
title: Project item requirements
description: This article explains how to create project-based item requirements.
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project item requirements

[!include[banner](../includes/banner.md)]

An *item requirement* is a sales order document that has project-specific integrations and enhancements that non-project sales orders lack. An item requirement is unique and provides flexibility during planning for item consumption throughout the lifecycle of a project. You can record item requirements earlier than sales orders.

Like sales orders, item requirements can represent a stocked item, a non-stocked item, or a service item. Because item requirements are integrated throughout the project module, organizations have the flexibility to start with planned requirements. They can then execute against the project, either by using item requirements from stock or by acquiring them through production or procurement, and then consume them against the project at the correct time. Item requirements provide great visibility into the financial implications of a transaction throughout the item's lifecycle.

To have item requirements automatically created, enable the **Create item requirement** parameter in the **Project purchase orders** section of the **Project management and accounting parameters** page.

> [!NOTE]
> To distinguish between a sales order and an item requirement, review whether the **Order type** field of the sales order is set to **Sales order** or **Item requirements**.

Item requirements can be used in several project types. They can be used even in several project types where sales orders aren't available. The following table shows the types of projects where item requirements and sales orders can be used.

| Project type      | Item requirement | Sales order |
| ----------------- | ---------------- | ----------- |
| Time and Material | X                | X           |
| Fixed Price       | X                |             |
| Investment        | X                |             |
| Cost              |                  |             |
| Time              |                  |             |
| Internal          |                  |             |

## Create item requirements

You create item requirements from the **Plan** tab in a project, or by going to **Project management and accounting** \> **Item tasks** \> **Item requirements**.

The **Item requirements** page is a streamlined version of the **Sales order** page. Required functions are available on the Action Pane.

Previously, item requirements were always managed through a single sales order header. In general, most item requirements will continue to add lines to a single header, even if all previous lines were invoiced. However, in some situations, multiple headers will be created. For example, if there are multiple funding sources, a unique header is created for each funding source.

## Post the packing slip for item requirements

When an item requirement's packing slip is posted, accounting entries are created to post the cost of the item, and inventory is called to update the inventory state.

### Item requirement cancellation feature

In the 10.0.33 release, you can cancel a packing slip for item requirements. To enable the cancellation of item requirements, use the **Enable packing slip cancellation for item requirements** feature. 

The packing slip cancellation feature provides the following functionality:

- Packing slips can be canceled for item requirements that aren't connected to a production order or purchase order that a packing slip was posted for while the feature was enabled. Connected item requirements and packing slips that were previously posted continue to behave as if the feature isn't enabled.
- Newly posted packing slips for item requirements that aren't connected to a production or purchase order use the new behavior. Eventually, a product receipt cancellation feature will modify the posting behavior of item requirements that are connected to purchase orders.
- The way that financial posting is done for stocked item requirements now closely resembles sales order posting. For more information, see [table 1](#table1).
- The way that inventory is posted for stocked items is changed. For more information, see [table 2](#table2).
- The line status of stocked item requirements that have a posted packing slip is now **Delivered** instead of **Invoiced**.
- The packing slip journal can now be accessed from the item requirement page on the **Inquiries** navigation menu, so that you can view and cancel the packing slip.
- A new packing slip ID field is added, and the packing slip ID is visible on the **Posted project transactions** page. Therefore, you can filter the transactions and view the original transaction and reversal from the cancellation together.
- Other entries for project cost appear in posted project transactions and the general ledger. The project cost is initially posted during packing slip posting. However, it's then reversed and posted again during invoicing. These amounts might be the same, or they might change if inventory determines that project cost has changed. 

The following functionality was added in the 10.0.35 release:

- Support is added for packing slip cancellation in committed costs.
- Support is added for packing slip cancellation in funding limits.
- Support is added for packing slip cancellation in budget.
- Support is added for adjusting transactions that are posted while the feature is on.
- The adjustment behavior is changed, so that stocked items can financially post inventory to complete posting, reverse the entry, and then post it again with adjustments. 

**<a id="table1"></a>Table 1: Accounting generated from a Time and Material project without work in process (WIP)**

| Step | Account name | Posting type |
| --- | --- | --- |
| Create an item requirement | Not applicable | Not applicable |
| Post a packing slip | <ul><li>COGS - Finished Goods</li><li>Finished Goods Inventory</li></ul> | <ul><li>Project cost</li><li>Cost of units, delivered</li></ul> |
| Create and post an invoice proposal | <ul><li>Accounts Receivable - Domestic</li><li>Product Sales</li><li>Finished goods inventory</li></li>Finished goods inventory</li><li>COGS - Finished Goods</li><li>COGS - Finished Goods</li></ul> | <ul><li>Customer balance</li><li>Project - invoiced revenue</li><li>Cost of units, delivered</li><li>Cost of units, invoiced</li><li>Project cost</li><li>Project cost</li></ul> |

**<a id="table2"></a>Table 2: Inventory behavior for stocked items when the feature is off versus on**

| Step | Inventory issue when the feature is off | Inventory issue when the feature is on | Sales order line when the feature is off | Sales order line when the feature is on |
| --- | --- | --- | --- | --- |
| Create an item requirement line | New entry where **Issue** = **On order** | New entry where **Issue** = **On order** | Open order | Open order |
| Post a packing slip | **Issue** = **Sold** | **Issue** = **Deducted** | Invoiced | Delivered |
| Post a project invoice proposal | **Issue** = **Sold** | **Issue** = **Sold** | Invoiced | Invoiced |

#### Limitations of item requirement cancellation

- If the feature is used with nonchargeable lines for stocked items or fixed price projects, transactions and amounts are left in the **Cost of units, delivered** posting type and the associated account. Because these transactions can't be invoiced, the amounts aren't moved to the **Cost of units, invoiced** posting type.
- Packing slips can't be canceled if the transaction was previously invoiced, or if it was invoiced and then returned through a credit note.

#### Demo data issues to consider

In the **USSI** legal entity, the **Sale\_367** number sequence is in an inconsistent state. Cancellation of an item requirement causes the following error:

> Voucher 000001 is already used as of date 1/9/2017. Posting has been cancelled.

To fix the issue, go to **Number sequences**, filter for number sequence code **Sale\_367**, and open the item. On the **Performance** FastTab, change the value of the **Preallocation** option from **Yes** to **No**, and save the change. Then, change the value back to **Yes**.
