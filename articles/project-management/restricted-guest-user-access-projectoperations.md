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

To enable organizations to collaborate more effectively with external partners and contractors while maintaining security, the guest users from Microsoft Entra ID are allowed to access Microsoft Project/Microsoft Dynamics 365 Project Operations when the Restricted Guest Access (RGA) policy is enabled in Entra ID.

**However, there are some restrictions on the project access of guest users when RGA is enabled.**

## Restrictions on project access when RGA is enabled

This section contains a list of restrictions on project access when RGA is enabled.

- Guest users can't create a new Microsoft 365 group. However, they can add an existing Microsoft 365 groups to the project.
- Guest users can't modify a Microsoft 365 group, even if they're a group member or a group owner. This behavior is consistent for both Private and Public groups.
- If they're not part of the group, guest users can't search for the Microsoft 365 group members. If they search the group members, they receive the message **You don't have permission to view group members. Contact your administrator.**
- Guest users can access group members for groups that they're part of.
- Guest users can't add or remove members from the group.
- During a task assignment, a guest user can see only active team members from project. They're not able to view everyone else.
- When a guest user searches for a name that isn't in the **Teams** tab to perform the task assignment, they receive a warning message: **You have limited access to search only among project members.**

To learn more details about RGA policy, read the document[Restrict guest access permissions in Microsoft Entra ID](/entra/identity/users/users-restrict-guest-permissions)
