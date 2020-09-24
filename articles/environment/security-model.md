---
# required metadata

title: Security model
description: 
author: stsporen
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Security Model

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations contains a unique security model that allows for a role-based business security model that collaborates with Microsoft Office Groups. 


## Security roles
Project Operations front-end capabilities include the following roles:

| Role                          | Description                                                                                                                                                                 | Scope |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|
| Practice manager              | Supports cross-project reporting.                                                                                                            | Business unit              |
| Project approver              | Approves time and expenses against a project.                                                                                                                              | Busines unit |
| Project billing administrator | Creates the invoice proposal.                                                                                                                                                 | Business unit |
| Project manager               | Creates the project plan and requests resources.                                                                                                                              | Business unit |
| Project resource              | Team members who can be booked and report time.                                                                                                          | Business unit|
| Resource manager              | All resource management functions (fulfill resource requests and bookings) seperated to support a hybrid Project manager + Resource manager configuration and a single central Resource manager role | Business unit |


Microsoft Project for the Web includes the following roles:
| Role                          | Description                                                                                                          | Scope |                                                       
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----|
| Project user | Collabortive user of Project who is able to create their own projects and view any projects shared with them.| User|
| Project system | Role used for application context. This is a system role and should not be used by customers. | Global|

## Security enforcement
Actions that are performed at the project level are performed in the context of the logged in user. This means that in order to create, open, or delete a project, the user is required to have access available in CDS. Access in CDS may be granted through any of the possible mechanisms included in the platform. For example, a user with a larger scope may access the project or if an explicit project share action has been performed which grants the user access.

It's important to consider this when creating projects in Project Operations.

## Modern group collaboration with Project Operations
Project for the Web and Project Operations support modern groups for collaboration. Users added to the project through a group are able to edit the project plan.

Project for the Web adds users to the group automatically upon assignment.

Groups allow the permissions of the project and supporting collaboration artifacts to be worked on collaboratively. The following diagram depicts the events and state changes that happen during the group assignment process.

Project Operations does not create a group through implicit action and only does so through the explicit action of pressing groups.

Group member search in the group management dialog is limited to those who if set are part of the environments secuirty group (see [Control user access to environments: security groups and licenses](https://docs.microsoft.com/en-us/power-platform/admin/control-user-access))

![Group mode](../media/groupsmode.png)

1. The Project is created and owned by the creating User.
2. The Project owner is update the team.
3. The Owner team is mapped to the specified or created Office Group.
4. The original owner of the Project is added to the Office Group.

## Deployment recommendation
As our approach to the office group collaboration model evolves, we will be adding the ability to include an intersection of user role and group membership to provide more detailed control over time. Customers that deploy Project Operations today are encouraged to focus on a traditional Microsot Dynamics 365 security model.

For more information, see [Security in Common Data Service](https://docs.microsoft.com/en-us/power-platform/admin/wp-security).

## Project Operations and Microsoft Dynamics 365 Finance security
Project Operations includes the following roles:

- Project manager
- Project accountant

For more information about security in Finance, see [Role-based security](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/sysadmin/role-based-security).


