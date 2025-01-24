---
title: Manage project production orders
description: Learn how to effectively manage production orders related to projects.
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

_**Applies To:** Project Operations for stocked based scenarios.

In Microsoft Dynamics 365 Finance, project production orders are used to manage and track the manufacturing activities associated with specific projects. These orders integrate production processes with project management to enable businesses to align manufacturing operations with project timelines, budgets, and deliverables.

## Key Features of Dynamics 365 Project Production Orders:

- **Integration with Projects** - Production orders are directly linked to projects to ensure materials, labor, and resources are allocated appropriately, and costs are tracked accurately.
- **Cost Tracking** - Costs incurred during the production process are recorded against the project. This recording helps with monitoring project budgets and ensuring profitability.
- **Material Planning** - Dynamics 365 enables detailed material requirements planning (MRP) for project-based production to ensure the necessary materials are procured or available on time.
- **Resource Allocation** - Resources, including machines and labor, are scheduled in line with project needs to avoid delays and optimize efficiency.
- **Real-Time Monitoring** - You can track the progress of production orders in real-time to ensure project deadlines and quality standards are met.
- **Integration with Other Modules** - Project production orders work seamlessly with other modules like Finance, Microsoft Dynamics 365 Supply Chain Management, and Project Operations to provide a holistic view of project performance.

## Set up project production parameters

To set up the default production parameters, follow these steps.

1. **Go to** **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.
1. Select **Production tab**.
1. Select **posting method** as **Finished item** or **Consumed**.
1. Set **Subproduction to consumed** to either **yes** or **no**. If subproduction orders are created for the main production orders, they can be designated as either consumed or not consumed. 

There are two methods for utilizing production orders in projects:

1. **Finished item**: In this method, a production order is created and executed. Once the production order is completed, the cost of the finished item is posted to the project, and the finished item can be invoiced to the customer.
1. **Consumed**: This method involves production orders where the time spent, and costs incurred during production are directly associated with the project. The individual time and item costs recorded during production can be invoiced to the customer.
       
## Project production orders linked with sales orders or item requirements

A project-related production order can be connected to a sales order or item requirement. If the production order is generated automatically to meet a sales order or item requirement, it's directly linked to that sales order or item requirement.

### Finished item

If you select the finished item posting method, you can link the project to a sales order or an item requirement. With this method, actual project costs are recorded either when the sales order is invoiced or when the packing slip is updated for the item requirement. The cost is posted as a finished item.

### Consumed item

If you select the **Consumed item** posting method, you can link the project to an item requirement. 
Using this method, you can view actual project costs when the production has a status of **Started** or is **reported as Finished**. 
The costs are posted as multiple project item transactions for raw materials and hours consumed for production. 
When the packing slip is updated for the item requirement, no project costs are posted. 
You can also define the level in the bill of materials (BOM) hierarchy at which projects in production are tracked. 
To create the hierarchy in the BOM line form, select **Pegged supply** in the **Line type** field and check the **Set subproduction to Consumed** option. This procedure creates subproductions for your hierarchy.

> [!NOTE]
> The consumed item/link to order method doesn't support indirect costs and standard costs.

## Direct project production orders

A project production order can be created independently of project sales orders or item requirements. 

### Finished item

If you select the finished item as **posting method** and **production order** is created without sales orders or item requirements,
then you can't **post project costs** until the production cycle for an item has a status of **Ended**. The cost for the finished item is posted as a single transaction.

### Consumed item

You can use the consumed item posting method without any linkage to the item requirement. By using this method, you can view actual project costs when the production has a status of **Started** or is **reported as Finished**. 

The costs are posted as multiple project item transactions for raw materials and hours consumed for production. 

You can also define the level in the BOM hierarchy at which projects in production are tracked. 

To create the hierarchy in the BOM line form, select **Pegged supply** in the **Line type** field and check the **Set subproduction to Consumed** option. This procedure creates subproductions for your hierarchy.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
