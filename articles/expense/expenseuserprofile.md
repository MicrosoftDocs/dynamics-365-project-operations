---
title: Manage user profiles and notifications by using the Dynamics 365 expense management mobile app
description: This article explains how to use the Microsoft Dynamics 365 expense management mobile app to manage the user profiles and notifications that are required to create or manage expenses.
author: mukumarm
ms.date: 12/19/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage user profiles and notifications by using the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations for stocked/production-based scenarios_

This article explains how to use the Microsoft Dynamics 365 expense management mobile app to manage the user profiles and notifications that are required to create or manage expenses.

Users are associated with a specific legal entity. That legal entity is automatically set as their default legal entity in their user profile for expense creation and management. In situations where a user is employed in multiple legal entities, expenses must be generated in the appropriate legal entity. To document an expense in a specific legal entity, users might have to adjust the legal entity setting before they initiate the expense creation process.

## Change the legal entity

To create an expense in a legal entity other than the selected legal entity, follow these steps.

1. On your mobile device, open the **Power Apps** mobile app, and then open the **Expense management mobile** app.
1. In the upper left of the mobile app, select the user.
1. Select **Change legal entity** to change the current legal entity.
1. In the designated **Selected legal entity** field, select the legal entity that the expense must be generated for. The field lists all the legal entities where the current user is employed.
1. Select **Done** to confirm the change.

> [!NOTE]
> A change to the legal entity in the user profile in the Expense management mobile app sets the default legal entity in the Dynamics 365 Finance user profile.

## Access notifications

In the expense management mobile app, users receive notifications in the following situations:

- A new expense is created from credit card import.
- An expense report is ready for approval.
- An expense is ready for approval.
- An expense report is approved.
- An expense is approved. 

To access the notifications and take action based on them, use the notification interface.

1. On your mobile device, open the **Power Apps** mobile app, and then open the **Expense management mobile** app.
1. In the upper left of the mobile app, select the user.
1. Select **Notifications** to view the list of notifications.
1. In the notification list, select a notification that's related to an expense or expense report. You're taken to the specific expense or expense report, where you can take the required action.
