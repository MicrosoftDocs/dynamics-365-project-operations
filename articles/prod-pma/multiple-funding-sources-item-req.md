---
title: Item requirements for project contracts with multiple funding sources
description: Learn how to configure item requirements for project contracts with multiple funding sources in Dynamics 365. Follow step-by-step instructions to streamline your setup.
author: mukumarm
ms.author: mukumarm
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Item requirements for project contracts with multiple funding sources

_**Applies To:** Project Operations for manufacturing based scenarios_

Some contractual agreements for project-based deliverables require multiple funding sources. This article explains how to select and configure the desired funding sources when multiple sources are required for a project or project contract.

## Terminology

- **Funding source** – The entity that funds the project contract work. This entity can be an internal organization or an external invoice account (customer or grant).
- **Project customer** – The entity that the project work is delivered to.
- **Invoice account** – The external entity that pays for the project work.

## Example

Contoso wins an equipment renewal contract with two of its customers: Adatum US and Adatum Corporate. The contract includes hardware and installation services that it delivers to Adatum US (the project customer). Adatum Corporate (invoice account 1) finances the hardware, and Adatum US (invoice account 2) finances the installation work.

## Set up invoice account defaulting rules for item requirements

### Prerequisites

- To use item requirements that have multiple invoice accounts, you need Microsoft Dynamics 365 Finance **version 10.0.27 or later**.
- Your system administrator must enable the **Allow Item requirements with multiple funding sources for Project Operations for manufacturing** feature in the **Feature management** workspace.

### Set up the invoice account defaulting rules

To set up the default rules for the invoice account, follow these steps:

1. Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **General** tab, in the **Sales orders and Item requirements** section, set the **Allow for projects with multiple funding sources** option to **Yes**.
1. In the **Default customer** field, specify where the project delivery customer on the item requirement comes from by default:

    - **From funding source** – The default project delivery customer comes from the funding source. If multiple funding sources are associated with the project contract, the first funding source in the list is used.
    - **From project** – The default project delivery customer comes from the customer that you select in the **Project record account** field.

1. Optional: Set or change the default invoice account on project records:

    1. Go to **Project management and accounting** \> **Projects** \> **All projects**, and open the project record details.
    1. On the **General** tab, set or update the **Default invoice account** field. The account that you specify is the default invoice account for new item requirements that you create for the project. If you leave the field blank, the invoice account of the first project contract funding source is used by default. However, users can change the account when they save the record.

### Select the invoice account to use when you create an item requirement

To select the invoice account to use when you create an item requirement, follow these steps:

1. Go to **Project management and accounting** \> **Projects** \> **All projects**, and select the project record.
1. On the **Plan** tab, select **Item requirements**.
1. Create a new item requirement record.

    - By default, the **Invoice account** field in the record is set to the invoice account that is set for the project. Change the value of the **Invoice account** field if needed, and then save the record. After you save the record, you can't update the **Invoice account** value. If you must update the **Invoice account** value for the item requirement, delete the existing item requirement, and then create a new one that has the desired value.
    - By default, the **Customer** field for the item requirement is set based on the **Default customer** value that is set on the **Project management and accounting parameters** page.

    When you save the item requirement record, the system associates it with the **Item requirement sales order** header record. If no open sales order header has the selected invoice account, the system creates one and associates the item requirement line with it.

> [!NOTE]
> Item requirements are always fully invoiced to the invoice account that you set in the record. The system doesn't currently support funding allocation rules that have item requirements, and it won't split the posting based on the setup of funding allocation rules.

### Create an item requirement from an item forecast record

To create an item requirement from an item forecast record, follow these steps:

1. Go to **Project management and accounting** \> **Projects** \> **All projects** and select the project record.
1. On the **Plan** tab, select **Item forecasts**.
1. Create a new item forecast record.
1. Optional: On the **Project** tab, in the **Funding source** field, select the desired invoice account.
1. Select **Create item requirement**, and confirm the message that you receive.

    > [!NOTE]
    > The system copies the **Funding source** value from the item forecast record to the newly created item requirement record.

### Default invoice account when the system automatically creates an item requirement from a purchase order line

If you set the **Create item requirement** option to **Yes** on the **Project management and accounting parameters** page, the system automatically creates an item requirement when you save a new project purchase order line. By default, the **Invoice account** and **Item requirement** fields use the value from the **Default invoice account** field in the project record. The system doesn't currently support updating or changing the invoice account for records of this type.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
