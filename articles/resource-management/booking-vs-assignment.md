---
title: Bookings vs assignments
description: This topic provides information the differences between resource bookings and resource assignments.
author: ruhercul
manager: Annbe
ms.date: 10/26/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: ruhercul
---

# Bookings vs assignments

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Bookings are the hard or soft allocation of resources to a project. Hard bookings consume a resource's capacity. Bookings represent organizational concepts for teams so that they can understand how resources will be engaged across various projects. Dynamics 365 Project Operations considers bookings a project-level concept. 

Unlike bookings, assignments are the commitment of resources to project tasks in the project schedule. The resources can be named or generic. 

Typically, the sum of the bookings for a resource will equal the sum of the resource's assignments across one or many tasks. However, Project Operations doesn't enforce this agreement. The **Reconciliation** view shows the Project manager places where a resource's bookings and assignments don't agree.
