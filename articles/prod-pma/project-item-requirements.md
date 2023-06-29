---
# required metadata

title: Project item requirements
description: This article explains how to create project-based item requirements.
author: ryansandness
ms.date: 06/23/2023
ms.topic: conceptual
ms.custom: bap-template

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak

# ms.search.industry: 
ms.author: ryansandness
ms.search.validFrom: 2023-06-23
ms.dyn365.ops.version: AX 10.0.33

---

# Project item requirements

[!include[banner](../includes/banner.md)]

An item requirement is a sales order (SO) document with project-specific integrations and enhancements over nonproject SOs. An item requirement is unique and provides flexibility in planning for item consumption throughout the lifecycle of a project. You can record item requirements earlier than sales orders.

Just like sales orders, an item requirement can represent a stocked item, a non-stocked item, or a service item. Because item requirements are integrated throughout the project module, organizations have flexibility to start with planned requirements. Then they can execute against the project with using item requirements from stock or by acquiring through production or procurement, and then they can consume against the project at the right time. Item requirements provide great visibility into the financial implications of the transaction throughout the item's lifecycle.

Item requirements can be created automatically from **Project management and accounting parameters** form     using the **Create item requirement** parameter in the **Project purchase orders** section.

> [!NOTE]
> You can differentiate between a sales order and an item requirement by reviewing the **Order type** of the **Sales order** with values **Sales order** or **Item requirements**.

Item requirements can be used in several project types, and can be used in several project types where sales orders aren't available.

The following table shows the types of projects where item requirements and sales orders can be used.

| Project Type     | Item Requirement | Sales Order |
| ---------------- | ----------------- | ----------- |
| Time and Material| x                 | x           |
| Fixed Price      | x                 |             |
| Investment       | x                 |             |
| Cost             |                   |             |
| Time             |                   |             |
| Internal         |                   |             |

## Create item requirements

You create item requirements from within a Project, on the **Plan** tab, or on the **Item requirements** menu item under **Item tasks** within the **Project management and accounting** module.

The **Item requirements** form is a streamlined version of the **Sales order** form. Required functions are available on the ribbon.

Previously, item requirements were always managed through a single sales order header. It is still generally the case where most item requirements will continue adding lines to a single header, even if all previous lines were invoiced. In certain situations, such as with multiple funding sources, multiple headers are created to have a unique header per funding source.

## Post the packing slip for item requirements

When an item requirement's packing slip is posted, accounting entries are created to post the cost of the item and inventory is called to update the inventory state.

### Item requirement cancellation feature

With the 10.0.33 release, you can cancel a packing slip for item requirements. To enable the cancellation for item requirements, use **Enable packing slip cancellation for item requirements**. 

The packing slip cancellation feature:

- Enables packing slip cancellation for item requirements that aren't connected to a production order or purchase order that had a packing slip posted while the feature was enabled. Connected item requirements and packing slips that were previously posted continue to behave as if the feature wasn't enabled.
- Newly posted packing slips for item requirements not connected to a production or purchase order exhibit the new behavior. Item requirements connected to purchase orders will modify their posting behavior in a future feature enabling product receipt cancellation.
- Changes how financial posting is done for stocked item requirements to closely resemble sales order postings. For more information, see table 1.
- Changes how inventory is posted for stocked items. For more information, see table 2.
- Changes the behavior to have the line status of stocked item requirements with a posted packing slip as **delivered** instead of **invoiced**.
- The **packing slip journal** can be now accessed from the item requirement form under the **Inquiries** menu for navigation to view and cancel the packing slip.
- A new packing slip ID field has been added and the packing slip ID is visible in **Posted project transactions**  to filter the transactions and see the original transaction and reversal from the cancellation together
- Other entries for project cost appear in posted project transactions and in general ledger. The project cost is posted initially during the packing slip posting, but then is reversed and posted again during invoicing. These amounts may be the same, or it can change if inventory has determined that project cost has changed. 

The following functionality was added in the 10.0.35 release:

- Adds support for packing slip cancellation in committed costs.
- Add support for packing slip cancellation in funding limits.
- Adds support for packing slip cancellation in budget.
- Adds support for adjusting transactions that have been posted with the feature on. Adjustment behavior has changed for stocked items to post inventory financially to complete posting, reverse the entry and then post it again with adjustments. 

Table 1 - Accounting generated from a Time and Material project without WIP.

| Step | **Account name**                            | **Posting type**                                 |
| -------- | ------------------------------------- | ---------------------------------------- |
| Create Item Requirement    | - | -    |
| Post Packing Slip  |  - COGS - Finished Goods</br> - Finished Goods Inventory |- Project cost</br>- Cost of units, delivered |
| Create and Post Invoice Proposal   | - Accounts Receivable - Domestic</br>- Product Sales</br>- Finished goods inventory </br>- Finished goods inventory</br>- COGS - Finished Goods </br>- COGS - Finished Goods | - Customer balance</br>- Project - invoiced revenue<br>- Cost of units, delivered <br>- Cost of units, invoiced  <br>- Project cost <br>- Project cost

Table 2 - Inventory behavior for stocked items with feature off vs on.


| Step                          | Inventory Issue - feature off | Inventory Issue - feature on | SO Line - feature off | SO Line - feature on |
|-------------------------------|----------------------|----------------------|----------------|----------------|
| Create item requirement line        |New entry with Issue = on order                      | New entry with Issue = on order                     | Open order               | Open order               |
| Post Packing Slip             |  Issue = sold                    | Issue = deducted                     | Invoiced                | Delivered               |
| Post Project Invoice Proposal| Issue = sold                     | Issue = sold                     | Invoiced               | Invoiced               |


#### Item requirements cancellation limitations

- Using the feature with nonchargeable lines for stocked items or fixed price projects leaves transactions and amounts in the cost of units delivered posting type and associated account. Since these transactions can't be invoiced, the amounts won't move to the cost of units invoiced posting type.
- Packing slips can't be canceled if the transaction was previously invoiced, or invoiced and then returned through a credit note.

#### Demo data issues to consider

In USSI, the Sale_367 number sequence is in an inconsistent state. Canceling an item requirement results in the following error.

``` console
: "Voucher 000001 is already used as of date 1/9/2017. Posting has been cancelled."
```
To fix the issue, navigate to **number sequences**, filter number sequence code to Sale_367 and open the item. Under the **Performance** FastTab, set preallocation to **No** from **Yes** and save. Then, move back to **Yes**.
