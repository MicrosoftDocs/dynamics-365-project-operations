---
# required metadata

title: Define and edit project calendars
description: This article provides information about how to apply a calendar template to a project to track the project schedule.
author: abriccetti
ms.date: 11/13/2023
ms.topic: article
ms.prod: 
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

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

When a project is created, you must apply a calendar template to the project. The default calendar template will be chosen automatically, but it can be changed before the proejct is saved. The calendar template defines the following project attributes:

- Working hours, including start and end time
- Working days
- Calendar exceptions such as non-working days

The calendar template that's applied to a project is a copy of the calendar template defined in your organization’s settings.

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
> When a resource is referenced in a calendar template, a copy of the resource’s calendar is associated with the calendar template. If the working hours of the copied template change, those changes will not propagate to the calendar template.

You can now associate the work template with a project calendar template.

## Edit a project's calendar

Once a project is saved, there are two ways to edit the project's calendar. First you can apply a new calendar template to the project by selecting the drop down menu on the ribbon and then selecting change template. This will open a dialog box where a new calendar template can be applied to the project.

Alternatively, the work hours of the project can be directly edited by selecting the calendar tab on the project entity. This tab displays the projects work hours calendar, and allows for edits to those work hours to be made directly. These edits can be applied to the project's work breakdown structure by selecting the calendar drop down menu on the ribbon, and then selecting sync from that menu. Alternatively, the updates will be applied automatically when a new Microsoft Project for the Web project session is started by navigating to the tasks tab, following at least 30 minutes of inactivity on the project's tasks tab.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

