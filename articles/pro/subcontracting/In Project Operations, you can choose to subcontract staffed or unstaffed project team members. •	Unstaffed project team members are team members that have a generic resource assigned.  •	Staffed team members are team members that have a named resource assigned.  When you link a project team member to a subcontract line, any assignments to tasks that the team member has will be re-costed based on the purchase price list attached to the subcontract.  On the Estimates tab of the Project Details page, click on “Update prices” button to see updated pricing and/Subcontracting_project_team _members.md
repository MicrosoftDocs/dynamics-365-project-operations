---
title: Subcontracting project team members
description: This topic provides an overview of the subcontracting capabilities in Project Operations that are part of the October 2021 early access release.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: tonyafehr 
ms.author: rumant
---

# Subcontracting project team members

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Project Operations, you can choose to subcontract staffed or unstaffed project team members.
•	Unstaffed project team members are team members that have a generic resource assigned. 
•	Staffed team members are team members that have a named resource assigned. 
When you link a project team member to a subcontract line, any assignments to tasks that the team member has will be re-costed based on the purchase price list attached to the subcontract.  On the Estimates tab of the Project Details page, click on “Update prices” button to see updated pricing and /or costing resulting from the decision to subcontract. 
Subcontracting an unstaffed project team member:
The Team Member details page has subcontract and subcontract line fields that allow a project manager to express that he or she would like to draw the capacity required from a subcontract. When deciding to subcontract a project team member that has a generic resource, follow the steps below:
a.	Choose a subcontract on the team member detail page to do this.
b.	You can only select subcontracts in Draft or Confirmed status. Closed or cancelled subcontracts cannot be selected. 
c.	Subcontract line field becomes visible once you have selected a subcontract.
d.	In the Subcontract line field, you can only select subcontract lines that are for time. You cannot select subcontract lines for Expense or Material
e.	The role required on the project team member record needs to match the role on the subcontract line. This is to ensure that the role whose time is being estimated on the project is the role being purchased on the Subcontract line. 
Once a generic team member is associated with a subcontract and subcontract line, worker type field on the generic team member row will be updated to Contract Worker and Subcontract Validity will be set to the value “Valid”.
Subcontracting a staffed project team member:
Like generic or unstaffed team members, staffed team member capacity required on a project can also be linked to a subcontract. When deciding to subcontract a named project team member, follow the steps below:
a.	Make sure that the named resource is setup as a contract worker type of bookable resource. Also, make sure is that the vendor field on the bookable resource matches the vendor on the subcontract that you are selecting. 
b.	You can only select subcontracts in Draft or Confirmed status. Closed or cancelled subcontracts cannot be selected. 
c.	Subcontract line field becomes visible once you have selected a subcontract.
d.	In the Subcontract line field, you can only select subcontract lines that are for time. You cannot select subcontract lines for Expense or Material
e.	The role on the project team member record needs to match with the role on the subcontract line. This is to ensure that the role whose time is being estimated on the project is the role being purchased on the Subcontract line. 

Named project team members that are set up as contract worker type of bookable resource will be show with a subcontract validity status of “Not valid” if they are not linked with a subcontract.  Once a named project team member is associated with a subcontract and subcontract line, worker type field on the team member row will be updated to Contract Worker and Subcontract Validity will be set to the value “Valid”.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
