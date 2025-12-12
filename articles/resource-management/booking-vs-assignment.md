---
title: Bookings vs assignments
description: This article provides information the differences between resource bookings and resource assignments.
author: tulsij
ms.author: tulsijhaveri
ms.date: 05/28/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Bookings vs assignments

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Bookings are the hard or soft allocation of resources to a project. Hard bookings consume a resource's capacity. Bookings represent organizational concepts for teams so that they can understand how resources will be engaged across various projects. Dynamics 365 Project Operations considers bookings a project-level concept. 

Unlike bookings, assignments are the commitment of resources to project tasks in the project schedule. The resources can be named or generic.  When a resource requirement is derived from the project task assignments, Project Operations uses the effort contours of the resources assignment to build the contours of the resource requirement details. However, a reference to the resource assignments isn't maintained. Updates to the bookings derived from the resource requirement don't update any resource assignments.

Typically, the sum of the bookings for a resource will equal the sum of the resource's assignments across one or many tasks. However, Project Operations doesn't enforce this agreement. The **Reconciliation** view shows the Project manager places where a resource's bookings and assignments don't agree.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
