---
title: Resource management modes overview
description: This topic provides information about Resource management functionality in Dynamics 365 Project Operations.
author: ruhercul
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: ruhercul
---

# Resource management modes overview

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Dynamics 365 Project Operations supports two modes in order for you to execute the overall booking flow. The mode of management is defined as a project parameter and can be modified if your business needs change.    

## Central mode
For organizations who centralize the allocation for resources to projects, the Central mode provides a way to ensure Project managers can define resource requirements at the project level. Fulfillment of the resource requirements is delegated to a Resource manager. Project managers can accept or reject resources that are proposed by the Resource manager.

![Central Mode](./media/resource-management-central.png)

To manage resources with the Central mode, see:

- [Assign generic bookable resources to a task and generate resource requirements](https://docs.microsoft.com/dynamics365/project-service/assign-generic-bookable-resource)
- [Book named resources from resource requirements](https://docs.microsoft.com/dynamics365/project-service/book-named-resource)
- [Submit a resource request](https://docs.microsoft.com/dynamics365/project-service/submit-resource-request)
- [Fulfill a resource request](https://docs.microsoft.com/dynamics365/project-service/resource-management-fulfill-requests)
- [Accept or reject a proposed project resource from a resource request](https://docs.microsoft.com/dynamics365/project-service/accept-reject-proposed-resource)

## Hybrid mode
For organizations who require flexibility in the allocation of resources, the hybrid mode enables both Project managers and Resource managers the ability to book resources.

![Hybrid Mode](./media/resource-management-hybrid.png)

In addition to the supported Central mode process, see the following topics to manage all other supported booking flows in the Hybrid mode:

Book a resource directly to a project:
- [Book named bookable resources to a project team and assign tasks](https://docs.microsoft.com/dynamics365/project-service/assign-named-bookable-resource)

Book a resource from a resource requirement:
- [Assign generic bookable resources to a task and generate resource requirements](https://docs.microsoft.com/dynamics365/project-service/assign-generic-bookable-resource)
- [Book named resources from resource requirements](https://docs.microsoft.com/dynamics365/project-service/book-named-resource)
