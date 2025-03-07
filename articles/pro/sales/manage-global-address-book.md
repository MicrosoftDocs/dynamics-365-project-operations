---
title: Manage the global address book
description: Learn how to activate and use the global address book in project operations for resource based or nonstocked scenarios. 
author: mukumarm
ms.date: 01/27/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Enable global address book for project operations

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

The Microsoft Dynamics 365 global address book is a centralized repository that stores and manages contact information for customers, vendors, employees, and other stakeholders. Consolidating this information in the global address book ensures data consistency, simplifies data management, and allows seamless communication across different modules and processes within Microsoft Dynamics 365 Finance.

This feature allows the management of multiple physical and electronic addresses for customers, vendors, and contacts. It also supports the use of delivery addresses in project quotations, contracts, and invoices.

## Prerequisites

To use the functionality, in **Microsoft Dataverse**, activate the **Enable global address book** feature.

### Minimum versions required

To use the feature for Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios, you must have the following versions:

- **Project Operations Dataverse** version 4.140.0.x or later.
- **Dynamics 365 Finance** version 10.0.43 or later.

### Dual-write for Global address book 

Refer [Party and global address book](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/party-gab) documentation for change of **Integration keys** and **Dual-write maps** required for activation of **Enable global address book** feature. There isn't a need to install the **Dual-write Party and global address book solutions** as this solution is part of Project Operations.

> [!NOTE]
> Enabling the global address book feature doesn't impact existing address data. However, address-related fields are disabled on the **Project quotation**, **Project contract**, and **Project invoice** form. You can select a new address using the **Address Name** field, and fields such as **Street 1**, **Street 2**, **City**, and **Country** automatically populate with data from the address book.
> 
> If you use **Microsoft Dynamics 365 Sales** or **Microsoft Dynamics 365 Customer Service** and already installed the global address book solution, no other setup is required.

## Customers, Vendors, and Contacts

Once this feature is turned on, the system allows you to create and manage multiple physical and electronic addresses for customers, vendors, and contacts. It also permits linking customers and vendors to a **Party ID** that's managed by the global address book. 

In the **Customers**, **Vendors**, and **Contacts** forms, new tabs for managing physical and electronic addresses are available. You can create these addresses directly in **Dynamics 365 Finance** or **Dataverse**, with the information synchronized seamlessly using Dual-write.

## Project quotes

You can add a **Delivery address** to the **Project quotation header** and **Project quotation customer**. All address-related fields, such as **Street 1**, **Street 2**, **City**, and **Country** are disabled, allowing you to select from existing addresses for the customer. 

Similarly, the **Invoice address** and **Delivery address** fields are disabled on the project quotation customer form to allow you to select one of the existing customer addresses.

You can create a new address for the customer directly using the **Address name** lookup field by selecting the **+New Postal Address** button on the **Delivery address** or **Invoice address** lookup and the same address can be used for the **Project quotation** and **Project quotation customer** form.

Once the quotation is won, the **Delivery address** from the project quotation is automatically carried over to the project contract. 
Additionally, the **delivery address** and **invoice addresses** of the project quotation customer are defaulted to the **project contract customer**. 

## Project contracts

You can add a **Delivery address** to the **Project contract** and **Project contract customer** form. All address-related fields, such as  **Street 1**, **Street 2**, **City**, and **Country** are disabled, allowing you to select from existing addresses for the customer. 

Similarly, **Delivery address** and **Invoice address** fields are disabled on the project contract customer form, allowing you to select one of the existing customer addresses.

However, you can create a new address for the customer directly through the **Address name** lookup field by selecting the **+New Postal Address** button on the delivery address and invoice address. 

When a new project contract is created manually and a customer is selected on the **Project contract** form, the customer's primary address automatically default in the **Project contract customer** form. However, you can modify the invoice address if needed. 

## Project invoices

In **Dataverse**, the **Delivery Address** section is added to the project invoice. 

The **Invoice address** and **Delivery address** fields, such as **Street 1**, **Street 2**, **City**, and **Country** are disabled and automatically default based on the selected **Invoice Address Name** and **Delivery Address Name** field.

When a project invoice is generated for a project contract, the invoice address defaults from the **Project contract customer**. 

The **Delivery address** defaults from the **Project contract** if specified; otherwise, it defaults from the **Project contract customer**. If no delivery address is provided on the project contract or the project contract customer, the delivery address field remains blank. However, you can select a delivery address on the project invoice form from the customer's existing addresses.

Once the **project invoice** is **confirmed** in **Dataverse**, the **delivery address** and **invoice address** are synchronized with the invoice proposal in **Dynamics 365 Finance**.

The **Delivery address** and **Invoice address** fields are added to the Dynamics 365 Finance **Project invoice proposal**. These fields are noneditable as the addresses are synchronized from Dataverse. To enable the synchronization of the delivery and invoice addresses, activate the following Dual-write map version for the **Project invoice proposal**.

| Required Dual-write map | Required version |
|---|---|
| Project invoice proposal V2 (Invoices) | 1.0.0.4 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
