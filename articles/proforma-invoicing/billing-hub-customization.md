---
title: Billing hub view customization
description: This article provides information about how to customize Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 02/12/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Customizing Billing Hub for creating project based proforma invoices

> [!NOTE]
> Once the view is customized, customers will not get notified of any updates made to the OOB view.
> Hence we recommend using the OOB view as a reference to understand the updates made by Microsoft.
> Fields added/removed by Microsoft need to be manually updated by the customer on their custom view.

Billing Hub View includes a nested grid with contract and contract lines.
We recommend not customizing the fields on the contract view . To customize the contract line fields, follow the steps below.

## Customizing contract fields on Billing hub view

Updating the OOB billing hub view on the contract (parent) grid is currently not recommended unti the below issue is resolved. 
Columns can be added or removed from the view, however any changes within the "Components" section of the view will remove the grid customizer from the view , impacting the ability to view the clickable backlog on the contract(s) or contract line(s). This change can only be reverted by removing all active customizations from the view. 

## Customizing contract line fields on Billing hub view

To customize the contract line fields, follow the steps below.
1. Create a copy of the OOB billing hub (Contracts) view using "Save as" from the admin portal 
2. Update the custom view with the required fields on the contract line. 
3. Save and Publish
4. Set the custom view as the default view.
5. At any point in time , to revert to the OOB view, remove active customizations on the custom view. 

> [!IMPORTANT]
> Do not use "Edit Columns" to update Billing hub view. Doing so will break the nested grid hierarchy. Instead always use the Power Apps portal to customize the Billing hub and Billing hub - All order lines views.
> The "Billing Method" column should not be removed from the view as it is a required field.


   

