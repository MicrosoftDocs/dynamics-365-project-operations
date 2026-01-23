---
title: Schedule assistant overview
description: This article provides information about working with the Schedule assistant to book resources.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Schedule assistant overview

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Use the schedule assistant to book resources based on requirements defined by the project manager. The schedule assistant relies on the parameters provided in the resource requirement to find the resource. The schedule assistant recommends resources that match relevant requirements, like time windows or skills needed.

After you identify suitable resources, the resource or project manager can book the resource to the work.

## Prerequisites

The schedule assistant is part of the Universal Resource Scheduling solution. This solution is included and installed with Dynamics 365 Project Operations, Dynamics 365 Field Service, and Dynamics 365 Customer Service.

## Matching requirements and resources

The schedule assistant generates a resource requirement based on details such as:

- Characteristics
- Roles
- Business units
- Resource preferences
- Effort contours
- Time zone

The schedule assistant uses these details to filter resources.

## Launch the schedule assistant

You can launch the schedule assistant in two ways. If you're using the hybrid mode, in the team member grid you can select any team member with an unfulfilled resource requirement, and then select **Book**. If you're using the central mode, the resource manager finds and selects the resource.

## Schedule assistant filters

After the Schedule assistant runs, it displays the details from the resource requirement as filtered values in the left pane. The resource manager or the project manager can fine-tune results by adjusting filters to meet the scheduling needs.

The filter pane shows work-related options, including:

- Work start and end
- Characteristics
- Roles
- Organizational units
- Resourcing company
- Resource types
- Preferred resources

[!INCLUDE[footer-include](../includes/footer-banner.md)]
