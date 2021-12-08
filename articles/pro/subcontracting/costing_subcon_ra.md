---
title: Cost estimation of subcontracted resource assignments
description: This topic explains some how Microsoft Dynamics 365 Project Operations calculates cost estimation of subcontracted resource assignments.
author: rumant
ms.date: 12/03/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Cost estimation of subcontracted resource assignments

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Task assignments of subcontracted project team members are costed using the **Purchase** price list attached to the Subcontract on the related team member record. This is different than how Employee resource assignments are costed where task assignments of employee resources are costed using the **Cost** price list that is attached to the Contracting unit of the project. 

For generic project team members that are subcontracted, the assignments are costed using a role-based price setup in the purchase price list attached to the subcontract. Purchase prices can also be setup specifically for each resource and this given priority when costing task assignments of named project team members who are contract workers. 
Priority of using role-specific purchase price vs resource-specific is driven by the setup of pricing dimension priority in **Parameters**->**Amount-based-pricing dimensions**.

This functionality of dynamically deriving prices based on dimension setup for purchase prices of subcontractors is similar to how cost and bill rates are derived for full-time employees. 

## Creating task assignments for getting cost estimates of subcontractor resources

Task assignments for subcontractors can be created in 2 ways: 
### Creating resources assignments using the Tasks tab
Using the resources dropdown in the tasks tab for a specific task, you can create a task assignment for a named resource or a generic resource. 
If you pick a named resource from the “Assigned Resources” dropdown on the task and this resource is a contract worker, the named resource is assigned to the task and a corresponding project team member record is created with worker type set to Contract Worker and Validity set to ‘Invalid’. As a next step, you will need to open the project team member record and pick a subcontract and subcontract line. This will update the task assignment to have a reference to the subcontract and subcontract line and will also update the team member status to ‘Valid’. 

If you choose to create generic team member from the “Assigned Resources” dropdown on the task, the generic team member creation dialog will allow you to pick a subcontract and subcontract line. When the generic resource is assigned to the task and the corresponding project team member record is created, you will notice that the project team member record is created with worker type set to Contract Worker and Validity set to ‘Valid’.  

### Creating project team members using the Team tab and then assign the project team member to a task. 
Using the Team tab on the project, you can create a generic or a named team member. When creating the team member, you have the option to select the subcontract and subcontract line. Once the team member is created, you will need to assign the team member to a task using the “Assigned Resources” dropdown on the Task. 

## Updating Estimates
Once you have assigned project team members to tasks you will need to navigate to the Estimates tab on the project and click on **Update prices** to ensure that the cost rates of subcontractor resource assignments are updated based on the purchase price list attached to the subcontract. Note that estimates are not generated for unassigned tasks in Project Operations. So, it is required that you create task assignments to price and cost various tasks on your project. 
Note: Project team members that have **Worker type** as **Contract worker** but do not have a subcontract reference are flagged as **Invalid** on the **Project team members** grid. When you see any project team members with this status, open the project team member record and manually update the subcontract and subcontract line fields so that the financial cost estimate accurately reflects the subcontractor cost on the Estimates tab. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
