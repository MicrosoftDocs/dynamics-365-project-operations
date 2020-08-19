---
# required metadata

title: Generic resource requirement fulfillment
description: This topic provides information about booking named resources for a generic resource requirement.
author: ruhercul
manager: AnnBe
ms.date: 08/19/2020
ms.topic: article
ms.prod: 
ms.service: dynamics-project-operations
ms.technology: 

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: suvaidya
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Generic resource requirement fulfillment

You can book a named resource to replace generic resource that has a resource requirement.

1. In Project Service Automation (PSA), on the **Projects** page, click the **Team** tab.
2. Select the generic resource that has a resource requirement from the list and then click **Book**. Or, open the resource requirement and then click **Book**.


![Booking a generic team member](media/RM-how-to-14.png)


3. On the **Schedule Assistant** page, select a named resource to book onto your project team and then click **Book**.

![Booking a generic team member using schedule assistant](media/RM-how-to-15.png)

When the booking is complete and fulfilled by a named resource, the generic resource is replaced with the named resource.

![Named team member replacing a generic team member](media/RM-how-to-16.png)

The assignments on the schedule are updated with the named resource as well.

![Named team member assigned to project tasks](media/RM-how-to-17.png)

## Fulfill a generic resource with multiple named resources
Fulfilling a requirement for a generic resource with multiple named resources is similar to assigning a single named resource. For example, there is a task with a duration of five days and 120 hours of effort. This task can't be completed by one resource that works a typical eight-hour day over a five day week. 

![A task that needs 120 hours of effort over five days](media/RM-how-to-21.png)

The requirement is for 120 hours of robotics engineering over five days, which is 24 hours per day.

![Per day requirement](media/RM-how-to-22.png)

This is an example of when multiple named resources are needed to fulfill a generic resource request. You will need to book multiple resources to fulfill the requirement.

![Booking multiple resources to fulfill the requirement](media/RM-how-to-23.png)

The main difference in this scenario is that the generic resource remains on the team assigned to the task, and the booked named resource team members are not assigned as part of the position. The project manager can assign the work as appropriate to the named resources. The **Reconciliation** view can assist a project manager in breaking up the bookings across multiple resources to task assignments. This is not done automatically because in any scenario more complicated than the simple example above, such as where you have a bundle of tasks making up the requirement, the intent of how the project manager wants to assign, needs to be assumed by the system. Because the system can't understand intent, chances are that the assumptions will be different than intended and an incorrect or unpredictable result will happen. The predictable outcome is that the generic resource remains assigned until the project manager deliberately creates assignments, with the assistance of the **Reconciliation** view.


