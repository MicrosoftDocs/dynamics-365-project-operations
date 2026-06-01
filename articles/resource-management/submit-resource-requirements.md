---
title: Submit a resource request
description: You can submit a generated resource requirement as a resource request. The request is then sent to a Resource Manager for fulfillment. 
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Submit a resource request

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You can submit a generated resource requirement as a resource request. The system sends the request to a Resource Manager for fulfillment.

1. In Dynamics 365 Project Operations, on the **Projects** page, select the **Team** tab to view a list of bookable resources.
1. Select the generic resource that has a resource requirement from the list, and then select **Submit Request**.

The request status of the generic team member changes to **Submitted**.

The recipient of the resource request can partially fulfill the request by using one or more resources, or completely fulfill the resource request.

After the request is fulfilled, you add one or more named resources to the project as project team members. If one resource fulfills the resource requirement, the process deletes the generic team member associated with the resource request. 

When the recipient of the resource request proposes resources and is ready for the Project Manager to review the proposed resources, they should update the status of the resource request to **Needs Review**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
