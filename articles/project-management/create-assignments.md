---
title: Create resource assignments
description: This topic provides information about creating generic and named resource assignments.
author: ruhercul
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ruhercul
---

# Create resource assignments

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


A resource assignment is the direct association of a project team member to a leaf node task. This topic provides information about the different ways to assign resources.

## Create a generic team member through task assignment


When you create a generic team member through task assignment, you create a placeholder or generic resource. This generic resource describes the characteristics of the named resource you ultimately want to work on the tasks. You then generate a requirement, or submit a request using the requirement, that is used to search for and book the named resource.

1. On the Schedule grid for a task, select the Resource icon in the **Resource** cell.
2. Type a name to serve as the placeholder resource’s name. For example, Program Manager.
3. Select **Create**, and in the **Quick Create Project Team Member** field, set the role for the generic resource.
4. Assign tasks as needed to this placeholder resource by selecting the resource on the **Resource Selector** for the task. The resources listed under **Team Members**.
5. When you’re finished assigning the generic resource, on the **Team** tab, select the generic resource, and then select **Generate Requirement** to create a resource requirement for the generic resource.
6. Select **Book** for the generic resource and then use the Schedule board to find and book a real resource. You can also submit the requirement for fulfillment by a resource manager.
7. When the generic resource is fully fulfilled (partial resource requirement fulfillment will not result in a resource assignment) with a named resource, the generic resource is removed from the team. The task assignments for the generic resource are assigned to the named resource that fulfilled the generic resource’s resource requirement.

## Assign a named resource from the list of all bookable resources

You can use the search box in the **Resource Picker** to search all active bookable resources and assign them to any leaf node task. Resources assigned this way are added to the team without any bookings. This is similar to adding a team member and selecting **None** as the allocation method. The resource is displayed on the **Team**, **Resource Assignment**, and **Reconciliation** tabs as resources with only assignments and a booking deficit. Book them if you want to use their availability.

1. From the task grid, board, or timeline, navigate to the **Assigned To** cell.
2. In the search box, start typing a name. The search results for the name are displayed in the **Resource Selector** under **Other Resources**.
3. Select the resource that you want to assign to the task or select the name of the resource under **Other Team Resources**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]