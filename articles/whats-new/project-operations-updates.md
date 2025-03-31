---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: abriccetti
ms.topic: conceptual
ms.custom: 
  - bap-template
  - evergreen
ms.date: 03/20/2025
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Operations Updates

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_

## Project Operations Components

Dynamics 365 Project Operations consists of two components:

- Project Operations on Dataverse environment covers capabilities from opportunity to proforma invoicing. Dataverse is used in the lite deployment and resource/non-stocked scenarios deployment of Project Operations.
- Project Management and Accounting in the Dynamics 365 Finance environment covers expense management capabilities, project accounting, and revenue recognition. The Finance and Operations app environment is used in Project Operations for resource/non-stocked based scenarios and Project Operations for stocked/production-based scenarios.

## Project Operations Station & Geographical Regions

| **Station**   | **Geographical Location**                                                                   |
|---------------|---------------------------------------------------------------------------------------------|
| **Station 1** | First Release (FRE)                                                                         |
| **Station 2** | South America, Canada, India, France, South Africa, Switzerland, Korea, Germany, Norway     |
| **Station 3** | Asia-Pacific, United Kingdom, Australia, Japan, United Arab Emirates, US Gov High Sovereign |
| **Station 4** | Europe, Middle East, and Africa                                                             |
| **Station 5** | North America                                                                               |

## Project Operations Release Notes
- Project Operations latest release notes for [Resource/non-stocked](whats-new-feb-2025-resource-based.md) scenario.
- Project Operations latest release notes for [Lite deployment](../pro/whats-new/whats-new-feb-2025-lite.md) scenario.
- Project Operations latest release notes for [stocked/production](../prod-pma/whats-new/whats-new-Feb-2024-stocked.md) scenario.

## Project Operations Latest Version

| **Project Operations on Dataverse Environment** | **Project Management and Accounting in Finance and Operations Apps Environment** | **Project App on Dataverse Environment** |
|:-----------------------------------------------:|:--------------------------------------------------------------------------------:|:----------------------------------------:|
|                   4.124.0.1450                  |                                      10.0.43                                     |                1.0.124.1450              |

> [!IMPORTANT]
> - The minimum supported versions of Project Operations and Project in Dataverse are 4.28.0.XX and 1.0.28.X respectively.
> - For Project Operations Resource/non-stocked scenario, we recommend that you use dual-write orchestration version 2.3.1.15 or higher.
> - If you're using an older version of either product, contact Microsoft support for assistance in upgrading.

## Release Schedule for Project Operations on Dataverse Environment

> [!IMPORTANT]
> - New updates for Project Operations on the Dataverse Environment are released on a monthly basis.
> - Customers are expected to receive their **"Auto Update"** approximately **one week** after the **"Self Update Start Date"**.
> - The **"Auto Update Start Date"** marks the beginning of the upgrade rollout from Microsoft.
> - **"Auto Updates"** are managed by Microsoft and are executed on the dates specified in the table below. The timing of these updates adheres to the maintenance window defined for your environment. For instructions on defining a maintenance window, see [Manage Maintenance Window](https://learn.microsoft.com/en-us/power-platform/admin/manage-maintenance-window).
> - If an **"Auto Update"** cannot be completed, the update will be attempted again the next day for up to a week, within the defined maintenance window for your environment.
> - Depending on the station, region, and other factors, _**the release may reach customers within the stipulated one-week timeframe.**_

| **Version/Station** | **Station 1**              | **Station 1**              | **Station 2**              | **Station 2**              | **Station 3**              | **Station 3**              | **Station 4**              | **Station 4**              | **Station 5**              | **Station 5**              |
|---------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|
|                     | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** |
| **4.140.0.X**       | 11 April, 2025             | 18 April, 2025             | 18 April, 2025             | 25 April, 2025             | 25 April, 2025             | 02 May, 2025               | 02 May, 2025               | 09 May, 2025               | 09 May, 2025               | 16 May, 2025               |
| **4.141.0.X**       | 09 May, 2025               | 16 May, 2025               | 16 May, 2025               | 23 May, 2025               | 23 May, 2025               | 30 May, 2025               | 30 May, 2025               | 06 June, 2025              | 06 June, 2025              | 13 June, 2025              |
| **4.142.0.X**       | 13 June, 2025              | 20 June, 2025              | 20 June, 2025              | 27 June, 2025              | 27 June, 2025              | 04 July, 2025              | 04 July, 2025              | 11 July, 2025              | 11 July, 2025              | 18 July, 2025              |
| **4.143.0.X**       | 11 July, 2025              | 18 July, 2025              | 18 July, 2025              | 25 July, 2025              | 25 July, 2025              | 01 August, 2025            | 01 August, 2025            | 09 August, 2025            | 09 August, 2025            | 16 August, 2025            |

## Release Schedule for Project Management and Accounting in the Finance and Operations Apps Environment

See the [Service Update Availability](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases) for the Project Management and Accounting in the Finance and Operations Apps Environment Release Schedule. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
