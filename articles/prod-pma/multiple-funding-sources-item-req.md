---
title: Item requirements for project contracts with multiple funding sources
description: This topic provides information about how to configure and use Item requirements with multiple funding sources.
author: sigitac
ms.date: 05/04/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Item requirements for project contracts with multiple funding sources

_**Applies To:** Project Operations for stocked/production based scenarios_

Some contractual agreements for project-based deliverables may require multiple funding sources. This topic describes how to select and configure the desired funding source when multiple sources are required for a project or project contract.

## Terminology

**Funding source** – entity funding project contract work. This entity can be an internal organization, or an external invoice account (customer or grant).

**Project customer** – entity to which project work is being delivered.

**Invoice account** – external entity paying for the project work.

## Example

Contoso has won an equipment renewal contract with their customers Adatum US and Adatum Corporate. The contract includes hardware and installation services that will be delivered to Adatum US (project customer). The hardware will be financed by Adatum Corporate (invoice account 1) and installation work will be financed by Adatum US (invoice account 2).

## Set up Invoice account defaulting rules for Item requirements

### Prerequisites

- Using **Item requirements with multiple Invoice accounts** requires **10.0.27 or higher Dynamics 365 Finance and Operations version**.
- Your System administrator must enable **Allow Item requirements with multiple funding sources for Project Operations stocked/production-based scenarios** in **Feature management** workspace.

### Set up the invoice account defaulting rules

To set up the default rules for the **Invoice account**, complete the following setup:
1. Go to  **Project management and accounting** \> **Setup** \> **Project management and accounting parameters** and select the **General** tab.
1. In the **Sales orders and Item requirements** group:
   - Set the parameter **Allow for projects with multiple funding sources** to **Yes**.
   - Select the appropriate option in the **Default customer** field:
     - **From funding source** – select this option to set the default for the **Project delivery customer** on the **Item requirement** to come from the funding source. If the project contract has multiple funding sources associated, it will use the first funding source from the list.
     - **From project** – select this option to set the default for the **Project delivery customer** on the **Item requirement** to come from the customer selected in the **Project record account** field.
1. Optionally, you can set or change the **Default invoice account** on the **Project records**. Go to **Project management and accounting** \> **Projects**  \> **All projects** and open the project record details. In the **General** tab, set or update the value for the **Default invoice account** field. This value is used as a default value for the invoice account for the new item requirements created for this project. If the value in this field is empty, the system will default to **Invoice account** for the first project contract funding source, and the user will be able to change it when saving the record.

### Pick the invoice account to use when creating an Item requirement

To pick the invoice account to use when creating an **Item requirement**, complete the following setup:
1. Go to **Project management and accounting** \>  **Projects** \> **All projects**, and then pick the **Project record**. From the **Plan** tab, select the **Item requirements** menu.
1. Create a new **Item requirement** record:
  1. The system defaults to the **Invoice account** field on the record as per the default **Invoice account** setup for the project. If desired, change **Invoice account** to a different value, and then save the record. The system will not let you update the value after the record is saved. If you need to update **Invoice account** value on the **Item requirement**, delete the existing **Item requirement** and create a new a new one with the desired value.
  1. The **Customer** field value on the **Item requirement** is defaulted based on the **Project management and accounting parameters** setting for the **Default customer**.
1. When the **Item requirement** record is saved, the system associates it with the **Item requirement sales order** header record. If the open sales order header with the selected **Invoice account** does not exists, the system will create one and will associate the **Item requirement** line to it.

> [!NOTE]
> **Item requirement** is always fully invoiced to the **Invoice account** that is set on the record. The system currently does not support funding allocation rules with **Item requirements** and will not split the posting based on the funding allocation rules setup.

### Create an Item requirement from the Item forecast record

To create an **Item Requirement** from the **Item forecast** record, complete the following setup:
1. Go to **Project management and accounting** \> **Projects** \> **All projects** and then select the project record. From the **Plan** tab, select **Item forecasts**.
1. Create a new **Item forecast** record. Optionally, you can select the desired **Invoice account** in the **Funding source** field in the **Project** tab.
1. Select **Create item requirement** and confirm the dialog window. 
   > [!NOTE]
   > The system copies project the **Funding source** from the **Item forecast** record to newly created **Item requirement** record.

### Default Invoice account when system automatically creates an item requirement from Purchase order line

When the **Create item requirement** parameter is set to **Yes** in the **Project Management and accounting parameters** form, the system automatically creates an **Item requirement** when the new project purchase order line is saved. The **Invoice account** and **Item requirement** is defaulted to the **Default invoice account** setting in the **Project record**. Currently the system does not support updating or changing the **Invoice account** for such record.
