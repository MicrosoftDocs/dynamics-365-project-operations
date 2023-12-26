---
title: Manage user profile to create expenses by using the Dynamics 365 expense management mobile app
description: This article explains how to manage user profile and notifications required to create or manage expenses using Dynamics 365 expense management mobile app.
author: mukumarm
ms.date: 12/19/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Manage expense report approvals by using the Dynamics 365 expense management mobile app

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios_

This article explains how to use the Dynamics 365 expense management mobile app to manage user profile.

Users are associated with a specific legal entity, and the legal entity is automatically set as the default in their user profile for expense creation and management. In certain situations, a user may be employed in multiple legal entities, requiring expenses to be generated within the appropriate legal entity. To document an expense within a specific legal entity, users may need to adjust the legal entity setting before initiating the expense creation process..

## Change legal entity

To create an expense in legal entity other than selected legal entity , follow below steps.

1. On your mobile device, open the **Power Apps** mobile app, and then open the **Expense management mobile** app.
1. Select the **User** on the left top of the mobile app. 
1. Select **Change legal entity** to change the current legal entity. 
1. Choose the **legal entity** for which the expense needs to be generated in the designated **selected legal entity** field. It will show a list of the **legal entities** where the present user holds employment.
1. Click **Done** to confirm the changes.

## Notifications

The user will receive notifications on the expense management mobile app for various cases. To access and take actions based on these notifications, users can navigate to the notification interface.

1. On your mobile device, open the **Power Apps** mobile app, and then open the **Expense management mobile** app.
1. Select the **User** on the left top of the mobile app. 
1. Select **Notifications** to view the list of notifications.
1. Select a notification related to **expense** or **expense report** from the notification list, it will take the user to the specfic expense or expense report.
1. User will get the **notifications** for the below cases:
   1. A new expense is created from credit card import.
   2. An expense report ready for approval.
   3. An expense ready for approval.
   4. An expense report is approved.
   5. An expense is approved. 

