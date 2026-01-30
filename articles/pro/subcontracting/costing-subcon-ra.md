---
title: Cost estimation of subcontracted resource assignments
description: Learn how to manage subcontractor cost estimation in Dynamics 365, from creating task assignments to updating prices for accurate project costing.
author: rumant
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Cost estimation of subcontracted resource assignments

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You cost task assignments for subcontracted project team members by using the **Purchase** price list attached to the subcontract on the related team member record. This approach differs from how you cost employee resource assignments. You cost task assignments for employee resources by using the **Cost** price list attached to the contracting unit of the project.

For generic project team members that you subcontract, cost assignments by using a role-based price setup in the purchase price list attached to the subcontract. You can also set up purchase prices specifically for each resource. These resource-specific prices take priority when costing task assignments for named project team members who are contract workers.

The setup of the pricing dimension priority in **Parameters > Amount-based-pricing dimensions** drives the priority of using role-specific purchase price versus resource-specific prices.

This functionality of dynamically deriving prices based on dimension setup for purchase prices of subcontractors is similar to how you derive cost and bill rates for full-time employees.

## Creating task assignments for getting cost estimates of subcontractor resources

You can create task assignments for subcontractors in two ways:

- Use the **Tasks** tab.
- Use the **Team** tab.

### Creating resources assignments by using the Tasks tab

By using the **Resources** list in the **Tasks** tab for a specific task, you can create a task assignment for a named resource or a generic resource. If you select a named resource from the **Assigned Resources** drop-down on the task and this resource is a contract worker, you assign the named resource to the task and create a corresponding project team member record with worker type set to **Contract Worker** and **Validity** set to **Invalid**. As a next step, you need to open the project team member record and select a subcontract and subcontract line. This step updates the task assignment to have a reference to the subcontract and subcontract line and also updates the team member status to **Valid**.

If you choose to create a generic team member from the **Assigned Resources** drop-down on the task, the **Generic team member creation** dialog allows you to select a subcontract and subcontract line. When you assign the generic resource to the task and create the corresponding project team member record, you set the worker type to **Contract Worker** and **Validity** to **Valid**.

### Creating project team members by using the Team tab

By using the Team tab on the project, you can create a generic or a named team member. When you create the team member, select the subcontract and subcontract line. After you create the team member, assign the team member to a task by using the **Assigned Resources** drop-down on the task.

## Updating estimates

After you assign project team members to tasks, go to the **Estimates** tab on the project and select **Update prices** to update the cost rates of subcontractor resource assignments based on the purchase price list attached to the subcontract. Microsoft Dynamics 365 Project Operations doesn't generate estimates for unassigned tasks. As a result, you need to create task assignments to price and cost various tasks on your project.

> [!NOTE]
> Project team members that have **Worker type** as **Contract worker** but don't have a subcontract reference appear as **Invalid** on the **Project team members** grid. If any project team members have this status, open the project team member record and manually update the subcontract and subcontract line fields so that the financial cost estimate accurately reflects the subcontractor cost on the **Estimates** tab.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
