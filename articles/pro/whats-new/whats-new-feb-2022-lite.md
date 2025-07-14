---
title: What's new February 2022 - Project Operations Core deployment
description: This article provides information about the quality updates that are available in the February 2022 release of Project Operations Core deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new February 2022 - Project Operations Core deployment

_Applies To: Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Dataverse environment version 4.28.0.120

## Features included in this release

As of this release, you can add up to 300 team members to a single project. Previously, the limit on the number of team members was 150. For more information, see [Project limits](../../project-management/project-and-task-limitations.md).

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
| Billing and pricing | 2497369 | Material correction must follow the date value in the **Correction** parameters. |
| Billing and pricing | 2498697 | Improved the security configuration for **Time entry recall**. |
| Billing and pricing | 2517455 | The **Refreshed invoice line transactions** action must not be allowed to be triggered multiple simultaneous times for the same invoice. |
| Billing and pricing | 2517465 | The **Deactivate invoice line details** action is blocked because it isn't supported. |
| Billing and pricing | 2556660 | Fixed the date effectivity checks that are done on the price list that is attached to a project parameters record. |
| Opportunity management | 2369202 | Corrected the business logic that verifies that price lists that have overlapping effectivity dates can be attached to the same project contract. |
| Opportunity management | 2385965 | Corrected the behavior on the **Customers** tab of the **Project contract** page when you select **Save and close**. |
