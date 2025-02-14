---
title: Customize the Billing hub view
description: Learn about how to customize Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 02/14/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Customize the Billing hub for creating project based proforma invoices

[!INCLUDE[banner](../includes/banner.md)]

The Billing hub view includes a nested grid with contract and contract lines. We recommend you don't customize the fields on the contract view. To customize the fields on the contract line view, create a copy of the out-of-the-box (OOB) Billing hub (Contracts) view using the steps listed in this article.

> [!NOTE]
> Once the view is customized, you aren't notified of any updates made to the OOB view. Therefore, we recommend using the OOB view as a reference to understand the updates made by Microsoft. Fields added or removed by Microsoft need to be manually updated by you on your custom view.

## Customize contract fields on Billing hub view

Updating the OOB Billing hub view on the contract (parent) grid is currently not recommended until the following issue is resolved. 
Columns can be added or removed from the view, however any changes within the "Components" section of the view will remove the grid customizer from the view, impacting the ability to view the clickable backlog on the contracts or contract lines. This change can only be reverted by removing all active customizations from the view. 

To customize the contract line fields, follow these steps.

1. From the admin portal, create a copy of the OOB Billing hub (Contracts) view using **Save as**. 
1. Update the custom view with the required fields on the contract line. 
1. Save and publish the changes.
1. Set the custom view as the default view.
1. At any point in time, to revert to the OOB view, remove active customizations on the custom view. 

> [!IMPORTANT]
> Don't use **Edit Columns** to update the Billing hub view. Using **Edit Columns** to update the Billing hub view breaks the nested grid hierarchy. Instead, use the Power Apps portal to customize the Billing hub, and Billing hub - All order lines views.
>
> Do not remove the **Billing Method** column from the view, it's a required field.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
