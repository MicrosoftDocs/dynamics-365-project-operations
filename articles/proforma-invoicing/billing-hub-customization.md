---
title: Customize the Billing hub view for creating project-based proforma invoices
description: Learn how to customize Billing hub so that you can create project-based proforma invoices.
author: suvaidya
ms.date: 02/14/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Customize the Billing hub view for creating project-based proforma invoices

[!INCLUDE[banner](../includes/banner.md)]

The **Billing hub** view includes a nested grid that has contract and contract lines. We recommend that you don't customize the fields in the contract view. To customize the fields in the contract line view, create a copy of the out-of-box **Billing hub (Contracts)** view by following the steps in this article.

> [!NOTE]
> After the view is customized, you aren't notified about any updates that are made to the out-of-box view. Therefore, we recommend that you use the out-of-box view as a reference to understand the updates that Microsoft makes. In your custom view, you must manually update any fields that Microsoft adds or removes.

## Customize contract fields in the Billing hub view

> [!IMPORTANT]
> Although columns can be added to or removed from the out-of-box **Billing hub** view on the contract (parent) grid, any changes that are made in the **Components** section of the view currently cause the grid customizer to be removed from the view. This issue affects the ability to view the clickable backlog on the contracts or contract lines. The only way to reverse the changes is to remove all active customization from the view.
>
> Until this issue is fixed, we recommend that you don't update the out-of-box **Billing hub** view on the contract (parent) grid.

To customize the contract line fields, follow these steps.

1. From the admin portal, create a copy of the out-of-box **Billing hub (Contracts)** view by selecting **Save as**.
1. Update the custom view with the required fields on the contract line.
1. Save and publish the changes.
1. Set the custom view as the default view.
1. To revert to the out-of-box view at any point, remove active customizations from the custom view.

> [!IMPORTANT]
> Don't use **Edit Columns** to update the **Billing hub** view. Otherwise, the nested grid hierarchy is broken. Instead, use the Power Apps portal to customize the **Billing hub** and **Billing hub - All order lines** views.
>
> Don't remove the **Billing Method** column from the view. It's a required column.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
