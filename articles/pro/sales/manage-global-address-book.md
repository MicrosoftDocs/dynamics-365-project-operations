---
title: Manage global address book for project operations
description: This article explains how to enable and use the global address book in project operations for resource-based or non-stocked scenarios. 
author: mukumarm
ms.date: 01/07/2025
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Enable global address book for project operations
The Dynamics 365 Global Address Book is a centralized repository that stores and manages address and contact information for various entities such as customers, vendors, employees, and other stakeholders. By consolidating this information, the global address book ensures data consistency, simplifies data management, and enables seamless communication across different modules and processes within Dynamics 365.

This feature enables the management of multiple physical and electronic addresses for customers, vendors, and contacts. It also supports the use of delivery addresses in project quotations, contracts, and invoices.

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use this feature for Microsoft **Dynamics 365 Project Operations non-stocked/resource-based scenarios**, below are the requirements:
1. **Project Operations Dataverse** version 4.124.0.x or later.
2. **Dynamics 365 Finance** version 10.0.43 or later.
3. Activate the feature **Enable global address book** in **Dataverse**.
  
Refer [Party and global address book](/Dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/party-gab.md) documentation for change of **Integration keys** and **Dual write maps** required for activation of **Enable global address book** feature. There is no need to install the **Dual-write Party and Global Address Book Solutions** as this solution is part of **Dynamics 365 project operations**.

> [!NOTE]
> Enabling the global address book feature will not impact existing address data. However, address-related fields will be disabled on the **project quotation**, **project contract** and **project invoice** form. Users can select a new address using the Address Name field, and fields such as Street, City, and Country will automatically populate with data from the address book.
> 
> If customers are using **Dynamics 365 Sales** or **Customer Service** and have already installed the **Global Address Book** solution, no additional setup is required.

## Customers, Vendors and Contacts

Once this feature is enabled, the system allows you to create and manage multiple **physical** and **electronic** addresses for **customers**, **vendors**, and **contacts**. It also enables linking customers and vendors to a Party ID managed by the global address book. 

In the forms for **customers**, **vendors**, and **contacts**, new tabs for managing physical and electronic addresses will become available. Users can create these addresses directly in **Dynamics 365 Finance** or **Dataverse**, with the information synchronized seamlessly through Dual Write.

## Project quotes
Users can add a **delivery address** to the **project quotation header** and **project quotation customer**. All address-related fields, such as Street 1, Street 2, City, and Country, will be disabled, allowing users to select from existing addresses for the customer. 

Similarly, **invoice address** and **delivery address** fields will be disabled on the project quotation customer form, enabling users to select one of the existing customer addresses.

Users can create a new address for the customer directly through the **address name** lookup field by clicking the **+New Postal Address** button on the **delivery address** or **invoice address** lookup and same address can be used for the project quoatation and project quotation customer form.

Once the quotation is **won**, the **delivery address** from the **project quotation** will be automatically carried over to the **project contract**. 
Additionally, the **delivery address** and **invoice addresses** of the project quotation customer will be defaulted to the **project contract customer**. 
## Project contracts
Users can add a **delivery address** to the **project contract** and **project contract customer** form. 
All address-related fields, such as Street 1, Street 2, City, and Country, will be disabled, allowing users to select from existing addresses for the customer. 

Similarly, **delivery address** and **invoice address** fields will be disabled on the project contract customer form, enabling users to select one of the existing customer addresses.

However, users can create a new address for the customer directly through the **address name** lookup field by clicking the **+New Postal Address** button on the delivery address and invoice address. 

When a new **project contract** is created **manually** and a customer is selected on the **project contract form**, the customer's **primary address** will automatically default in the **project contract customer** form. However, users can modify the invoice address if needed. 

## Project invoices
In **Dataverse**, A new section, **Delivery Address**, has been added to the project invoice. 

The **Invoice Address** and **Delivery Address** fields, such as Street, City, and Country, will be disabled and will automatically default based on the selected **Invoice Address Name** and **Delivery Address Name** field.

When a **project invoice** is generated for a **project contract**, the **invoice address** will default from the **project contract customer**. 

The **delivery address** will default from the **project contract** if specified; otherwise, it will default from the **project contract customer**. If no delivery address is provided on the project contract or the project contract customer, the delivery address field will remain blank. However, users can select a delivery address on the project invoice form from the customer's existing addresses.

Once the **project invoice** is **confirmed** in **Dataverse**, the **delivery address** and **invoice address** will be synchronized with the invoice proposal in **Dynamics 365 Finance**.

The **delivery address** and **invoice address** fields have been added to the Dynamics 365 Finance **project invoice proposal**. These fields are non-editable as the addresses will be synchronized from Dataverse. To enable the **synchronization** of the **delivery** and **invoice** addresses, activate the **Dual Write map** version specified below for the **project invoice proposal**.

**Project invoice proposal V2 (Invoices) : Version 1.0.0.4**
