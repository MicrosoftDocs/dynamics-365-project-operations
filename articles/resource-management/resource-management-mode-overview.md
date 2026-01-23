---
title: Resource management modes overview
description: This article provides information about Resource management functionality in Dynamics 365 Project Operations.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Resource management modes overview

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Dynamics 365 Project Operations supports two modes for executing the overall booking flow. You define the management mode as a project parameter and can change it if your business needs change.

## Central mode

For organizations that centralize the allocation of resources to projects, the Central mode provides a way to ensure project managers can define resource requirements at the project level. A resource manager handles the fulfillment of the resource requirements. Project managers can accept or reject resources that the resource manager proposes.

:::image type="content" source="./media/resource-management-central.png" alt-text="Screenshot of the Central mode resource management flow.":::

To manage resources by using the Central mode, see:

- [Assign generic bookable resources to a task and generate resource requirements](./assign-generic-resource-PO.md)
- [Book named resources from resource requirements](./book-named-resource-PO.md)
- [Submit a resource request](./submit-resource-request-PO.md)
- [Fulfill a resource request](./resource-fulfill-requests-PO.md)
- [Accept or reject a proposed project resource from a resource request](./accept-reject-proposed-resource-PO.md)

## Hybrid mode

For organizations that need flexibility in allocating resources, the hybrid mode enables both project managers and resource managers to book resources.

:::image type="content" source="./media/resource-management-hybrid.png" alt-text="Screenshot of the Hybrid mode resource management flow.":::

In addition to the supported central mode process, see the following articles to manage all other supported booking flows in the hybrid mode:

Book a resource directly to a project:

- [Book named bookable resources to a project team and assign tasks](./assign-named-bookable-resource-PO.md)

Book a resource from a resource requirement:

- [Assign generic bookable resources to a task and generate resource requirements](./assign-generic-resource-PO.md)
- [Book named resources from resource requirements](./book-named-resource-PO.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
