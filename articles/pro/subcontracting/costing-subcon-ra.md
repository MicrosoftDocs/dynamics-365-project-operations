---
title: Cost estimation of subcontracted resource assignments
description: This article explains some how Microsoft Dynamics 365 Project Operations calculates cost estimation of subcontracted resource assignments.
author: rumant
ms.date: 12/15/2023
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Cost estimation of subcontracted resource assignments

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Task assignments of subcontracted project team members are costed using the **Purchase** price list attached to the subcontract on the related team member record. This is different from how employee resource assignments are costed where task assignments of employee resources are costed using the **Cost** price list that is attached to the contracting unit of the project. 

For generic project team members that are subcontracted, the assignments are costed using a role-based price setup in the purchase price list attached to the subcontract. Purchase prices can also be set up specifically for each resource. These resource-specific prices will be given priority when costing task assignments of named project team members are contract workers. 

Priority of using role-specific purchase price versus resource-specific is driven by the setup of the pricing dimension priority in **Parameters > Amount-based-pricing dimensions**.

This functionality of dynamically deriving prices based on dimension setup for purchase prices of subcontractors is similar to how cost and bill rates are derived for full-time employees. 

## Creating task assignments for getting cost estimates of subcontractor resources

Task assignments for subcontractors can be created in two ways: 
- Using the **Tasks** tab.
- Using the **Team** tab.

### Creating resources assignments using the Tasks tab
Using the **Resources** list in the **Tasks** tab for a specific task, you can create a task assignment for a named resource or a generic resource. If you select a named resource from the **Assigned Resources** drop-down on the task and this resource is a contract worker, the named resource is assigned to the task and a corresponding project team member record is created with worker type set to **Contract Worker** and **Validity** set to **Invalid**. As a next step, you'll need to open the project team member record and select a subcontract and subcontract line. This will update the task assignment to have a reference to the subcontract and subcontract line and will also update the team member status to **Valid**.

If you choose to create a generic team member from the **Assigned Resources** drop-down on the task, the **Generic team member creation** dialog will allow you to select a subcontract and subcontract line. When the generic resource is assigned to the task and the corresponding project team member record is created, you'll notice that the project team member record is created with worker type set to **Contract Worker** and **Validity** set to **Valid**.

### Creating project team members using the Team tab
Using the Team tab on the project, you can create a generic or a named team member. When creating the team member, you can select the subcontract and subcontract line. After the team member is created, you'll need to assign the team member to a task using the **Assigned Resources** drop-down on the task. 

## Updating estimates
After you have assigned project team members to tasks, you'll need to navigate to the **Estimates** tab on the project and select **Update prices** to ensure that the cost rates of subcontractor resource assignments are updated based on the purchase price list attached to the subcontract. Estimates aren't generated for unassigned tasks in Microsoft Dynamics 365 Project Operations. As a result, you'll need to create task assignments to price and cost various tasks on your project. 

> [NOTE!] 
> Project team members that have **Worker type** as **Contract worker** but do not have a subcontract reference are flagged as **Invalid** on the **Project team members** grid. If there are any project team members with this status, open the project team member record and manually update the subcontract and subcontract line fields so that the financial cost estimate accurately reflects the subcontractor cost on the **Estimates** tab. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
