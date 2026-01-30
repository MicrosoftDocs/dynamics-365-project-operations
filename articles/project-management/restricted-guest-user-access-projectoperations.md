---
title: Restricted Guest User Access support for Project Operations
description: Learn how to enable Restricted Guest Access (RGA) in Microsoft Project Operations to collaborate securely with external partners while maintaining data protection.
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
author: poojafandan
---

# Restricted Guest User Access support for Project Operations

[!INCLUDE[banner](../includes/banner.md)]

To enable organizations to collaborate more effectively with external partners and contractors while maintaining security, enable the Restricted Guest Access (RGA) policy in Microsoft Entra ID. When you enable this policy, guest users from Microsoft Entra ID can access Microsoft Project and Microsoft Dynamics 365 Project Operations.

**However, the RGA policy enforces some restrictions on the project access of guest users.**

## Restrictions on project access when RGA is enabled

This section lists the restrictions on project access when RGA is enabled.

- Guest users can't create a new Microsoft 365 group. However, they can add an existing Microsoft 365 groups to the project.
- Guest users can't modify a Microsoft 365 group, even if they're a group member or a group owner. This behavior is consistent for both Private and Public groups.
- If they're not part of the group, guest users can't search for the Microsoft 365 group members. If they search the group members, they receive the message **You don't have permission to view group members. Contact your administrator.**
- Guest users can access group members for groups that they're part of.
- Guest users can't add or remove members from the group.
- During a task assignment, a guest user can see only active team members from project. They're not able to view everyone else.
- When a guest user searches for a name that isn't in the **Teams** tab to perform the task assignment, they receive a warning message: **You have limited access to search only among project members.**

For more information about the RGA policy, see [Restrict guest access permissions in Microsoft Entra ID](/entra/identity/users/users-restrict-guest-permissions).

[!INCLUDE[footer-include](includes/footer-banner.md)]
