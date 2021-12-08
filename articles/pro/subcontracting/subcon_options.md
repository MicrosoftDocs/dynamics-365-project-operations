---
title: Subcontracting options for project team members
description: This topic explains the subcontracting options for Project team members in Project Operations.
author: rumant
ms.date: 12/03/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Subcontracting options for project team members

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Project Operations, you can evaluate the subcontracting options available for one or more Project Team Members. Subcontracting options available are:

•	Create a new subcontract and or create new lines on an existing subcontract for the selected project team members 
•	Reserve against an already existing subcontract and subcontract line. 

You can review and choose from the available subcontracting options for generic project team members or for project team members that have been staffed with a named resource who is a contract worker. 

There are no subcontracting options available for 

a.	Project team members that have been staffed with an Employee. 
b.	Project team members that are already associated to a Subcontract and Subcontract line. 

To review and choose from the available subcontracting options for a Generic or unstaffed project team member, follow these steps:

1.	Select one or more project team member records where the resource is a generic resource.
2.	Ensure that none of the project team member records selected are already subcontracted. 
3.	Click on Subcontracting options on from ribbon actions available on the project team members sub grid.
4.	Subcontracting options dialog opens. If you selected only one project team member record in Step 1, then this dialog shows 2 options:

a.	Create new subcontract lines

b.	Reserve against an existing subcontract

If you selected multiple project team member records in Step 1, there is only one option available on the Subcontracting Options dialog that is to create a new subcontract lines.

5.	The option to reserve against an existing subcontract line will allow you to select a subcontract and subcontract line that you wish to reserve against. When selecting a subcontract line to reserve capacity, you should ensure that the subcontract line selected is for time and that the role required on the project team member matches with the role that was purchased on the subcontract line. 
6.	When you select to create new subcontract lines for the project team members, the system will allow you to select the subcontract that you wish to create these lines. The subcontract that you are selecting to create new lines in should be in Draft status. With this option to create new subcontract lines for the selected project team members, the system will create one subcontract line for time for each project team member. The role, hours and dates will be copied from the project team member to each subcontract line that is created.  
7.	Once a generic team member is associated with a subcontract and subcontract line, worker type field on the generic team member row will be updated to Contract Worker and Subcontract Validity value will be set to the value “Valid”.

## Subcontracting a staffed project team member:

Like generic or unstaffed team members, you also view Subcontracting options for a staffed project  team member as long as the staffed team member is a contract worker.  To review and choose from the available subcontracting options for a staffed or named project team member, follow these steps:

1.	Select one or more project team member records where the resource is a named contract worker.
2.	Ensure that none of the project team member records selected are already subcontracted. 
3.	Click on Subcontracting options on from ribbon actions available on the project team members sub grid.
4.	Subcontracting options dialog opens. If you selected only one project team member record in Step 1, then this dialog shows 2 options:
a.	Create new subcontract lines
b.	Reserve against an existing subcontract

If you selected multiple project team member records in Step 1, there is only one option available on the Subcontracting Options dialog, that is to create a new subcontract lines.

5.	The option to reserve against an existing subcontract line will allow you to select a subcontract and subcontract line that you wish to reserve against. When selecting a subcontract line to reserve capacity, you should ensure that
a.	The subcontract line selected is for time 
b.	The role required on the project team member matches with the role that was purchased on the subcontract line. 
c.	Vendor that the Contract Worker is associated to is the same as the vendor on the Subcontract 

6.	When you select to create new subcontract lines for the project team members, the system will allow you to select the subcontract that you wish to create these lines. With this option too, similar to the one above, you should ensure that the vendor the Contract Worker belongs to is the same as the vendor on the Subcontract 
7.	The subcontract that you are selecting to create new lines in should be in Draft status. With this option to create new subcontract lines for the selected project team members, the system will create one subcontract line for time for each project team member. The role, hours and dates will be copied from the project team member to each subcontract line that is created.  
8.	Once a named team member is associated with a subcontract and subcontract line, worker type field on the generic team member row will be updated to Contract Worker and Subcontract Validity value will be set to the value “Valid”.

## Re-costing subcontractor assignments:

When a project team member (generic or named) is linked to subcontract lines using the Subcontracting options dialog, any assignments to tasks that the team member has will be re-costed based on the purchase price list attached to the subcontract.  On the Estimates tab of the Project Details page, click on “Update prices” button to see updated pricing and /or costing resulting from the decision to subcontract. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
