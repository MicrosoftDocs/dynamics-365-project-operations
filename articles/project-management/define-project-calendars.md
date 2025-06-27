---
# required metadata

title: Define and edit project calendars
description: This article provides information about how to apply a calendar template to a project to track the project schedule.
author: abriccetti
ms.date: 11/13/2023
ms.topic: how-to
 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: johnmichalak
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Service industries
ms.author: ruhercul
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Define and edit project calendars

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

## Setting a project's calendar

When a project is created, you must apply a calendar template to the project. The default calendar template is chosen automatically, but it can be changed before the project is saved. The calendar template defines the following project attributes:

- Working hours, including start and end time
- Working days
- Calendar exceptions such as nonworking days

The calendar template applied to a project is a copy of the calendar template defined in your organization’s settings.

> [!NOTE]
> If you change the calendar template, those changes don't propagate to the working hours of the project. To change the working hours of the project, a new template must be applied.

To create a calendar template for your organization, there are two key requirements:

- Define the desired working hours of the template using a new or existing bookable resource.
- Create a new calendar template and associate the template with the bookable resource.

**Define the working hours of the template**

1. Go to **Resources** \> **Resources**.
2. Create a new resource to reference in the calendar template, or select an existing resource.
3. Select the **Work Hours** tab of the resource and complete the instructions in [Set work hours for a resource](/dynamics365/field-service/set-work-hours-resource) to configure the calendar rules.

**Create a new calendar template**

1. Go to **Settings** \> **Calendar Template**.
2. Select **New**, and enter a name, description, and template resource.

> [!NOTE]
> When a resource is referenced in a calendar template, a copy of the resource’s calendar is associated with the calendar template. If the working hours of the copied template change, those changes don't propagate to the calendar template.

You can now associate the work template with a project calendar template.

## Edit a project's calendar

Once a project is saved, there are two ways to edit the project's calendar. First you can apply a new calendar template to the project by selecting the **Calendar** drop-down menu on the ribbon and then selecting **Change Template**. Selecting **Change Template** opens a dialog box where a new calendar template can be applied to the project.

Alternatively, the work hours of the project can be directly edited by selecting the **Calendar** tab on the project entity. This tab displays the projects work hours calendar and allows for edits to those work hours to be made directly. These edits can be applied to the project's work breakdown structure by selecting the **Calendar** drop-down menu on the ribbon, and then selecting **Sync** from that menu.

> [!NOTE]
> When a project's calendar is changed, those changes don't propagate to the calendar template assigned to the project.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

