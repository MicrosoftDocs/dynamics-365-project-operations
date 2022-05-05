---
title: Item requirements for project contracts with multiple funding sources
description: This topic provides information about how to configure and use item requirements with multiple funding sources.
author: sigitac
ms.date: 05/04/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Item requirements for project contracts with multiple funding sources

_**Applies To:** Project Operations for stocked/production based scenarios_

# Item requirements for project contracts with multiple funding sources

Some contractual agreements for project-based deliverables may require multiple funding sources. This topic describes how to select and configure the desired funding source when required for a project or project contract.

## Terminology

**Funding source** – entity funding project contract work. This entity can be an internal organization, or an external invoice account (customer or grant).

**Project customer** – entity to which project work is being delivered.

**Invoice account** – external entity paying for the project work.

## Example

Contoso has won an equipment renewal contract with their customers Adatum US and Adatum Corporate. The contract includes hardware and installation services that will be delivered to Adatum US (project customer). The hardware will be financed by Adatum Corporate (invoice account 1) and installation work will be financed by Adatum US (invoice account 2).

## Set up invoice account defaulting rules for item requirements

### Prerequisites

- Using **Item requirements with multiple invoice accounts** requires **10.0.27 or higher Dynamics 365 Finance and Operations version**.
- Your System administrator must enable **Allow item requirements with multiple funding sources for Project Operations stocked/production-based scenarios** in **Feature management** workspace.

### Set up the invoice account defaulting rules

To set up the default rules for the invoice account, complete the following setup:
1. Go to  **Project management and accounting**  \&gt;  **Setup**  \&gt;  **Project management and accounting parameters** and select the **General** tab.
1. In the **Sales orders and Item requirements** group:
  - Set the parameter **Allow for projects with multiple funding sources** to **Yes**.
  - Select the appropriate option in the **Default customer** field:
    - **From funding source** – selecting this option defaults the project delivery customer on the item requirement from the funding source. If project contract has multiple funding sources associated, it will use the first funding source from the list.
    - **From project** – selecting this option defaults the project delivery customer on the item requirement from the customer selected in Project record Account field.

1. Optionally set or change **Default invoice account** on the **Project** records. Go to **Project management and accounting** \&gt; **Projects** \&gt; **All projects** and open the project record details. In the **General** tab, set or update the value for the **Default invoice account** field. This value is used as a default value for the invoice account for the new item requirements created for this project. If the value in this field is empty, the system will default to **Invoice account** for the first project contract funding source, and the user will be able to change it when saving the record.

### Pick the invoice account to use when creating an item requirement

To pick the invoice account to use when creating an item requirement, complete the following setup:
1. Go to **Project management and accounting** \&gt; **Projects** \&gt; **All projects**, and then pick the project record. In the **Plan** tab, select **Item requirements** menu.
1. Create a new **item requirement** record:
  1. The system defaults to the **Invoice account** field on the record as per Default **Invoice account** setup for the project. If desired, change **Invoice account** to a different value, and then save the record. The system will not allow you to update the value after the record is saved. If you need to update **Invoice account** value on the **Item requirement**, delete the existing **Item requirement** and create a new a new one with the desired value.
  1. **Customer** field value on the **Item requirement** is defaulted based on **Project management and accounting parameters** setting Default customer.
1. When the **Item requirement** record is saved, the system associates it with the **Item requirement Sales Order** header record. If the open sales order header with selected **Invoice account** does not exists, the system will automatically create one and will associate the **Item requirement** line to it.

Note:

**Item requirement** is always fully invoiced to the **Invoice account** that is set on the record. The system currently does not support funding allocation rules with **Item requirements** and will not split the posting based on the funding allocation rules setup.

### Create an Item requirement from the Item forecast record

To create Item Requirement from the Item forecast record, complete the following setup:
1. Go to **Project management and accounting** \&gt; **Projects** \&gt; **All projects** and pick the project record. In the **Plan** tab, select **Item forecasts**.
1. Create a new **Item forecast** record. Optionally select the desired **Invoice account** in the **Funding source** field in the **Project** tab.
1. Select **Create item requirement** and confirm the dialog window. Note the system copies project the **Funding source** from the **Item forecast** record to newly created **Item requirement** record.

###

### Default invoice account when system automatically creates an item requirement from Purchase order line

When the **Create item requirement** parameter is set to **Yes** in the **Project Management and accounting parameters** form, the system automatically creates an **Item requirement** when the new project purchase order line is saved. The **Invoice account** for such and **Item requirement** is defaulted based on the **Default invoice account** setting in the **Project** record. Currently the system does not support updating/changing the **Invoice account** for such record.
