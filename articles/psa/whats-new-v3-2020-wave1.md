---
title: What's new or changed in Project Service Automation version 3.x wave 1 2020
description: This article provides information about what is new and changed in Project Service Automation version 3 wave 1 2020.
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 04/09/2024
ms.topic: article
author: stsporen
ms.author: abriccetti
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---


# What's new or changed in Project Service Automation version 3 wave 1 2020

[!include [banner](../includes/psa-now-project-operations.md)]

The article highlights key upgrade considerations when moving to the latest release of Project Service Automation (PSA) version 3.x wave 1 2020.

## Time entry
The time entry experience has been extended to deliver capabilities for extending time entry into more customer scenarios. This includes the capability to add entry types, which now drive specific behavior based on the field schema name **Time Entry Settings**, displayed as **Time Source**. A new solution, called Time, Expense, Statusing, and Approvals (TESA) has been added to support this functionality.

### Upgrade consideration
To support this functionality, the roles within PSA have been updated to include new privileges. These privileges grant read access to the new entity, **Time Entry Settings**.

Users who require the ability to log time should be granted the user role **Time Entry User** in addition to existing roles. This role includes the new functionality and ensures that time entry will continue to work.

Additionally, if you have any custom app modules that include all forms for the time entry entity, you will be required to remove the **TESA time Entry Quick Create Form** from the module.

### Currently extended time entry changes
To minimize the impact to current users of time entry, this role change is the only core requirement necessary to continue utilizing time entry. If you have created custom views or separate time entry experiences, you must set the **Time Entry Setting** fields to the correct PSA value.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
