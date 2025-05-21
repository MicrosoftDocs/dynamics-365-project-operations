---
title: Manage multiple account addresses and apply them to project invoices.
description: Learn how to manage multiple addresses for accounts and apply them to project invoices in Project Operations integrated with ERP scenarios.
author: mukumarm
ms.date: 05/15/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage multiple addresses for accounts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations integrated with ERP scenarios_

The Microsoft Dynamics 365 global address book is a centralized repository that stores and manages contact information for customers, vendors, employees, and other stakeholders. Consolidating this information in the global address book ensures data consistency, simplifies data management, and allows seamless communication across different modules and processes within Microsoft Dynamics 365 Finance.

This feature allows the management of multiple physical addresses for customers, vendors, and contacts. It also supports the use of delivery addresses in project quotations, contracts, and invoices.

## Prerequisites

To use the functionality, in **Microsoft Dataverse**, activate the **Enable mulitple addresses for accounts** feature.

### Minimum versions required

To use the feature for **Microsoft Dynamics 365 Project Operations** integrated with ERP scenarios, you must have the following versions:

- **Project Operations Dataverse** version 4.142.0.x or later.
- **Dynamics 365 Finance** version 10.0.43 or later.

### Dual-write maps

| Required Dual-write map | Required version |Initial sync|
|---|---|---|
| Project invoice proposal V2 (Invoices) | 1.0.0.4 |Not applicable|
|Customers V3 (accounts)|1.0.0.3|Not applicable|
|CDS Party postal address locations (msdyn_locationparties)|1.0.0.0|Dynamics 365 Finance to Dataverse|
|CDS Postal address history V2 (msdyn_registeredaddresses|1.0.0.0|Dynamics 365 Finance to Dataverse|

> [!NOTE]
> Enabling feature doesn't impact existing address data. However, address-related fields are disabled on the **Project quotation**, **Project contract**, and **Project invoice** form. You can select a new address using the **Address Name** field, and fields such as **Street 1**, **Street 2**, **City**, and **Country** automatically populate with data from the address book.

## Customers, Vendors, and Contacts

Once this feature is turned on, the system allows you to create and manage multiple physical addresses for customers, vendors, and contacts. 

In the **Customers**, **Vendors**, and **Contacts** forms, new tabs for managing physical ddresses are available. You can create these addresses directly in **Dynamics 365 Finance** or **Dataverse**, with the information synchronized seamlessly using Dual-write.

## City, State and Country
This feature provides an option to select the city, state, and country during address creation. The lookups for these fields are fetched from the **Dynamics 365 Finance address setup**. Once the city, state, or country is selected, the name is defaulted to the respective field in **Dataverse**. City, state and country name fields are disabled and defaulted based upon the lookup values.

## Project quotes

You can add a **Delivery address** to the **Project quotation header** and **Project quotation customer**. All address-related fields, such as **Street 1**, **Street 2**, **City**, and **Country** are disabled, allowing you to select from existing addresses for the customer. 

Similarly, the **Invoice address** and **Delivery address** fields are disabled on the project quotation customer form to allow you to select one of the existing customer addresses.

You can create a new address for the customer directly using the **Address name** lookup field by selecting the **+New Address** button on the **Delivery address** or **Invoice address** lookup and the same address can be used for the **Project quotation** and **Project quotation customer** form.

Once the quotation is won, the **Delivery address** from the project quotation is automatically carried over to the project contract. 
Additionally, the **delivery address** and **invoice addresses** of the project quotation customer are defaulted to the **project contract customer**. 

## Project contracts

You can add a **Delivery address** to the **Project contract** and **Project contract customer** form. All address-related fields, such as  **Street 1**, **Street 2**, **City**, and **Country** are disabled, allowing you to select from existing addresses for the customer. 

Similarly, **Delivery address** and **Invoice address** fields are disabled on the project contract customer form, allowing you to select one of the existing customer addresses.

However, you can create a new address for the customer directly through the **Address name** lookup field by selecting the **+New Address** button on the delivery address and invoice address. 

When a new project contract is created manually and a customer is selected on the **Project contract** form, the customer's primary address automatically default in the **Project contract customer** form. However, you can modify the invoice address if needed. 

## Project invoices

In **Dataverse**, the **Delivery Address** section is added to the project invoice. 

The **Invoice address** and **Delivery address** fields, such as **Street 1**, **Street 2**, **City**, and **Country** are disabled and automatically default based on the selected **Invoice Address Name** and **Delivery Address Name** field.

When a project invoice is generated for a project contract, the invoice address defaults from the **Project contract customer**. 

The **Delivery address** defaults from the **Project contract** if specified; otherwise, it defaults from the **Project contract customer**. If no delivery address is provided on the project contract or the project contract customer, the delivery address field remains blank. However, you can select a delivery address on the project invoice form from the customer's existing addresses.

Once the **project invoice** is **confirmed** in **Dataverse**, the **delivery address** and **invoice address** are synchronized with the invoice proposal in **Dynamics 365 Finance**.

The **Delivery address** and **Invoice address** fields are added to the Dynamics 365 Finance **Project invoice proposal**. These fields are noneditable as the addresses are synchronized from Dataverse.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
