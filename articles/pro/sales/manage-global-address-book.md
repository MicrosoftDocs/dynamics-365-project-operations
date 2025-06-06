---
title: Manage multiple account addresses and apply them to project invoices.
description: Learn how to manage multiple addresses for accounts and apply them to project invoices in Project Operations integrated with ERP scenarios.
author: mukumarm
ms.date: 05/21/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage multiple addresses for accounts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations integrated with ERP scenarios_

The Microsoft Dynamics 365 global address book is a centralized repository that stores and manages contact information for customers, vendors, employees, and other stakeholders. Consolidation of this information into the global address book ensures data consistency, simplifies data management, and allows for seamless communication across modules and processes in Dynamics 365 Finance.

This feature enables the management of multiple physical addresses for customers, vendors, and contacts. It also supports the use of delivery addresses in project quotations, contracts, and invoices.

## Prerequisites

To use the functionality, in Dataverse, activate the **Enable multiple addresses for accounts** feature.

### Minimum versions required

To use the feature for Dynamics 365 Project Operations integrated with enterprise resource planning (ERP) scenarios, you must have the following versions:

- **Project Operations Dataverse** version 4.142.0.x or later
- **Dynamics 365 Finance** version 10.0.43 or later

### Dual-write maps

| Required dual-write map | Required version | Initial synchronization |
|---|---|---|
| Project invoice proposal V2 (Invoices) | 1.0.0.4 | Not applicable |
| Customers V3 (accounts) | 1.0.0.3 | Not applicable |
| CDS Party postal address locations (msdyn_locationparties) | 1.0.0.0 | Dynamics 365 Finance to Dataverse |
| CDS Postal address history V2 (msdyn_registeredaddresses) | 1.0.0.0 | Dynamics 365 Finance to Dataverse |

> [!NOTE]
> Enabling this feature doesn't affect existing address data. However, address-related fields are disabled on the **Project quotation**, **Project contract**, and **Project invoice** pages. You can select a new address by using the **Address Name** field. Fields such as **Street 1**, **Street 2**, **City**, and **Country/Region** are then automatically filled with data from the address book.

## Customers, vendors, and contacts

After this feature is turned on, you can create and manage multiple physical addresses for each customer, vendor, and contact. 

New tabs for managing physical addresses are available on the **Customers**, **Vendors**, and **Contacts** pages. You can create the addresses directly in either Dynamics 365 Finance or Dataverse. The information is then seamlessly synchronized through dual-write.

## City, state/province, and country/region

This feature provides an option that lets you select the city, state/province, and country/region during address creation. The lookups for these fields are fetched from the address setup in Dynamics 365 Finance. After you select the city, state/province, or country/region, the name is automatically set to the appropriate field in Dataverse. City, state/province, and country/region name fields are disabled and automatically set based on the lookup values.

## Project quotes

You can add a delivery address to the **Project quotation header** and **Project quotation customer** pages. All address-related fields, such as **Street 1**, **Street 2**, **City**, and **Country/region**, are disabled. Instead, you can select among the existing addresses for the customer. 

In a similar way, the **Invoice address** and **Delivery address** fields are disabled on the **Project quotation customer** page. Instead, you can select one of the existing customer addresses.

However, you can create a new address for the customer directly through the **Address name** lookup field by selecting **New Address** on the **Delivery address** or **Invoice address** lookup. The same address can be used on the **Project quotation** and **Project quotation customer** pages.

After the quotation is won, the delivery address from the project quotation is automatically carried over to the project contract. Additionally, the delivery address and invoice addresses of the project quotation customer are automatically entered for the project contract customer. 

## Project contracts

You can add a delivery address to the **Project contract** and **Project contract customer** pages. All address-related fields, such as **Street 1**, **Street 2**, **City**, and **Country**, are disabled. Instead, you can select among the existing addresses for the customer. 

In a similar way, the **Delivery address** and **Invoice address** fields are disabled on the **Project contract customer** page. Instead, you can select one of the existing customer addresses.

However, you can create a new address for the customer directly through the **Address name** lookup field by selecting **New Address** on the **Delivery address** or **Invoice address** lookup. 

When a new project contract is manually created, and a customer is selected on the **Project contract** page, the customer's primary address is automatically entered on the **Project contract customer** page. However, you can modify the invoice address if needed. 

## Project invoices

In Dataverse, the **Delivery Address** section is added to the project invoice. 

The **Invoice address** and **Delivery address** fields, such as **Street 1**, **Street 2**, **City**, and **Country/region**, are disabled and automatically set based on the selected **Invoice Address Name** and **Delivery Address Name** values.

When a project invoice is generated for a project contract, the invoice address is automatically taken from the project contract customer. 

The delivery address is automatically taken from the project contract, if it's specified there. Otherwise, it's taken from the project contract customer. If no delivery address is specified for the project contract or the project contract customer, the **Delivery address** field remains blank. However, on the **Project invoice** page, you can select a delivery address among the customer's existing addresses.

After the project invoice is confirmed in Dataverse, the delivery address and invoice address are synchronized with the invoice proposal in Dynamics 365 Finance.

The **Delivery address** and **Invoice address** fields are added to the **Project invoice proposal** page in Dynamics 365 Finance. These fields can't be edited, because the addresses are synchronized from Dataverse.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
