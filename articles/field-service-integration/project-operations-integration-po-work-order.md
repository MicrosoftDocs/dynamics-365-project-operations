---
title: Create a work order in Project Operations
description: As a project manager, learn how to create a work order from a project in Dynamics 365 Project Operations.
ms.date: 06/30/2026
ms.topic: how-to
author: vhorvathms
ms.author: vhorvath
---

# Create a work order from a project in Project Operations

Project managers can initiate field work directly by creating a work order from the project level in Project Operations. A project can have multiple work orders across different tasks.

Project managers can also associate existing work orders with projects to align previously created or in-progress work with the project structure.

To create a work order from a project task, go to [Create a work order from a project task](project-operations-integration-po-work-order-task.md).

## Prerequisites

- The [Field Service and Project Operations integration is installed](/dynamics365/field-service/project-operations-integration-setup).
- You have a Project Operations license and [permission to manage projects](../environment/security-model.md).

## Create a work order from a project

1. In Project Operations, open the project.

1. Select the **Related** tab and then **Work Orders**.

1. Select **New Work Order**. A quick create pane appears.

   :::image type="content" source="../field-service-integration/media/project-operations-integration-quick-create-work-order.png" alt-text="Screenshot of Project Operations work order creation screen.":::

1. Select the **Work Order Type** and add any other relevant information.

   Project context automatically populates key values, such as the account, project, and price list.

1. Save and close.

The work order is available in Field Service for scheduling and execution.

## Associate an existing work order to a project

1. In Project Operations, open the project.

1. Select the **Related** tab and then **Work Orders**.

1. Select **Add Existing Work Order**. Search for and select the work order from the list.

## Next steps

- [Schedule a work order linked to a project](/dynamics365/field-service/project-operations-integration-work-order-schedule#schedule-a-work-order-linked-to-a-project)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
