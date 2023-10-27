---
title: Restricted Guest User Access support for Project Operations
description: This article provides information about Restricted Guest User Access support for Project Operations
ms.date: 10/27/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
author: poojafandan
---

# Restricted Guest User Access support for Project Operations

[!INCLUDE[banner](../includes/banner.md)]

To enable organizations to collaborate more effectively with external partners and contractors while maintaining security, the guest users from Azure Active Directory (AAD) are allowed to access Project/Project Operations (PO) when Restricted Guest Access (RGA) policy is enabled in AAD.

**However, there are some restrictions on the project access of guest users when RGA is enabled.**

**When RGA is enabled:**

- The guest users cannot create a new M365 group. However, they can add existing M365 groups to the project.
- The guest users cannot modify an M365 group, even if they are a group member or a group owner. This behavior is consistent for both Private and Public groups.
- The guest users cannot search for the M365 group members, if they are not part of the group. If they search the group members, they receive the message ""You don't have permission to view group members. Contact your administrator.
- Guest users can access Group members that they are part of.
- Guest users cannot add/remove members from the group.
- During a task assignment, a guest user can see only active team members from project. They are not able to view 'everyone else'.
- In case Guest user searches for a name that is not in Teams tab to perform the task assignment, they would receive a warning message: "You have limited access to search only among project members."

To learn more details about RGA policy, read the document[https://learn.microsoft.com/en-us/entra/identity/users/users-restrict-guest-permissions](https://learn.microsoft.com/en-us/entra/identity/users/users-restrict-guest-permissions)
