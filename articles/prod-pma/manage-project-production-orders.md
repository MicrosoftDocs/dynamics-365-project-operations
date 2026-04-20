---
title: Manage project production orders
description: Learn how to effectively manage production orders that are related to projects.
author: mukumarm
ms.author: mukumarm
ms.reviewer: johnmichalak
ms.topic: how-to
ms.custom: 
  - bap-template
ms.date: 01/24/2025
---

# Manage project production orders

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for stocked based scenarios._

In Microsoft Dynamics 365 Finance, project production orders are used to manage and track the manufacturing activities that are associated with specific projects. By integrating production processes with project management, project production orders enable businesses to align manufacturing operations with project timelines, budgets, and deliverables.

## Key features of project production orders

- **Integration with projects** – Production orders are linked directly to projects to ensure that materials, labor, and resources are allocated appropriately, and that costs are tracked accurately.
- **Cost tracking** – Costs that are incurred during the production process are recorded against the project. This recording helps monitor project budgets and ensure profitability.
- **Material planning** – Dynamics 365 enables detailed material requirements planning (MRP) for project-based production. MRP ensures that the required materials are procured or available on time.
- **Resource allocation** – Scheduling of resources, including machines and labor, is aligned with project needs to help prevent delays and optimize efficiency.
- **Real-time monitoring** – You can track the progress of production orders in real time to ensure that project deadlines and quality standards are met.
- **Integration with other apps** – Project production orders work seamlessly with other apps, such as Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Project Operations. Therefore, you get a holistic view of project performance.

## Set up project production parameters

To set up the default production parameters, follow these steps:

1. Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. On the **Production** tab, in the **Posting method** field, select one of the following values to specify how productions are used in projects:

    - **Finished item** – In this posting method, a production order is created and run. After the production order is completed, the cost of the finished item is posted to the project, and the finished item can be invoiced to the customer.
    - **Consumed item** – This posting method involves production orders where the time that is spent and the costs that are incurred during production are directly associated with the project. The individual times and item costs that are recorded during production can be invoiced to the customer.

1. Set the **Subproduction to consumed** option to either **Yes** or **No**. If subproduction orders are created for the main production orders, they can be designated as either consumed or not consumed.

## Project production orders linked to sales orders or item requirements

A project-related production order can be linked to a sales order or an item requirement. If the production order is automatically generated to meet a sales order or item requirement, it's linked directly to that sales order or item requirement.

### Finished item

If you select **Finished item** as the posting method, you can link the project to a sales order or an item requirement. In this method, actual project costs are recorded either when the sales order is invoiced or when the packing slip is updated for the item requirement. The cost is posted as a finished item.

### Consumed item

If you select **Consumed item** as the posting method, you can link the project to an item requirement. In this method, you can view actual project costs when the production has a status of **Started**, or when it's reported as finished. The costs are posted as multiple project item transactions for raw materials and hours consumed for production. No project costs are posted when the packing slip is updated for the item requirement.

You can also define the level at which projects in production are tracked in the bill of materials (BOM) hierarchy. To create the hierarchy on the BOM line page, select **Pegged supply** in the **Line type** field, and select the **Set subproduction to Consumed** option. This procedure creates subproductions for your hierarchy.

> [!NOTE]
> The **Consumed item**/link to order method doesn't support indirect costs and standard costs.

## Direct project production orders

A project-related production order can also be created independently of project sales orders and item requirements.

### Finished item

If you select **Finished item** as the posting method, and a production order is created without sales orders or item requirements, you can't post project costs until the production cycle for an item has a status of **Ended**. The cost for the finished item is posted as a single transaction.

### Consumed item

You can use the **Consumed item** posting method without linking to an item requirement. In this method, you can view actual project costs when the production has a status of **Started**, or when it's reported as finished. The costs are posted as multiple project item transactions for raw materials and hours consumed for production.

You can also define the level at which projects in production are tracked in the BOM hierarchy. To create the hierarchy on the BOM line page, select **Pegged supply** in the **Line type** field, and select the **Set subproduction to Consumed** option. This procedure creates subproductions for your hierarchy.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
