---
title: Project task and work order integration
ms.reviewer: v-wendysmith
description: Learn how project tasks in Project Operations associate with work orders in the integration between Dynamics 365 Field Service and Project Operations.
ms.date: 07/07/2026
ms.topic: overview
author: vhorvathms
ms.author: vhorvath
---

# Project task and work order integration

The Project Operations app manages project task planning, task management, and task-level association experiences. The Field Service app manages scheduling and execution of field work. In the Field Service and Project Operations integration, you can create work orders from these project tasks directly in Project Operations to facilitate field work execution.

When you associate a work order with both a project and project task, the system maintains the relationship throughout execution to preserve project and financial alignment. Project managers can continue to manage and refine project plans in Project Operations, while the work order maintains a consistent link to the assigned project task for execution and traceability.

To create work orders from a project task in Project Operations, projects must meet the following criteria:

- The project must meet the [project requirements](/dynamics365/field-service/project-operations-integration-projects#project-requirements).
- The project tasks are created at the leaf task level in the [work breakdown structure (WBS)](../project-management/create-wbs.md).

## Project-driven scheduling behavior

Project Operations task dates synchronize to the work order as **Time Promised Start** and **Time Promised End** values, but this synchronization is one-directional. Changes made during scheduling in Field Service don't update project task dates, preserving the integrity of the project plan.

If project task dates change, the time promised values on the work order update automatically for unscheduled and scheduled work orders. Existing bookings aren't modified, which preserves dispatcher control over execution while still reflecting updated project expectations.

As work for project tasks progresses and [time entries are approved](/dynamics365/field-service/project-operations-integration-time), the system updates the task execution progress on the WBS.

## Assignments and bookings

In the integrated experience, resource assignments and bookings serve different purposes. Assignments represent planned resource allocation in the project work breakdown structure. Bookings represent confirmed scheduling commitments managed through Field Service or Project Operations. When a work order is linked to a project task, resource requirements are generated against the work order, and dispatchers book resources through Field Service. The project task view in Project Operations can display both assigned and booked resources. Learn more in [Bookings vs assignments](../resource-management/booking-vs-assignment.md).

## Time entries

Time entries that users log against a work order inherit the associated project and project task. This inheritance ensures that:

- Approved labor reflects against the correct project task and contributes to the project task’s effort completed hours.
- Approved time entries are also included in the overall actual hours for the project.

Currently, time entries don't appear in work order-level financial summaries or work order financial totals. Submitted but unapproved time entries don't impact project task effort completed hours, project progress, or project actual hours until they're approved.

For more information about time entry workflows, see [Time entry in Field Service and Project Operations](/dynamics365/field-service/project-operations-integration-time).

### Actuals and estimates

When the system generates time or material actuals or estimates through approval, each actual or estimate record includes a **Field Service** tab that displays the associated work order context. If the work order is linked to an agreement, the agreement and work order line reference appears.

This setup provides project managers with direct traceability from financial actuals back to the originating field service work, supporting audit and reconciliation workflows without requiring navigation to Field Service.

## Task-based billing

Task-based billing allows you to control how field service work is billed by assigning project tasks to specific contract lines, each with its own billing method. When time entries from Field Service flow into Project Operations, they inherit the billing behavior of the contract line associated with that task. Learn more in [Map projects and tasks to a project contract line](../pro/sales/mapping-projects-tasks-contract-line-sales.md).

## Related content

- [Create work orders from project tasks](project-operations-integration-po-work-order-task.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
