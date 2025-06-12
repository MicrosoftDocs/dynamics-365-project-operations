---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: abriccetti
ms.topic: article
ms.custom: 
  - bap-template
  - evergreen
ms.date: 06/12/2025
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Operations Updates

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_

## Project Operations Components

Dynamics 365 Project Operations consists of two components:

- Project Operations on Dataverse environment covers capabilities from opportunity to proforma invoicing. Dataverse is used in the lite deployment and resource/non-stocked scenarios deployment of Project Operations.
- Project Management and Accounting in the Dynamics 365 Finance environment covers expense management capabilities, project accounting, and revenue recognition. The finance and operations apps environment is used in Project Operations for resource/non-stocked based scenarios and Project Operations for stocked/production-based scenarios.

## Project Operations Station & Geographical Regions

| **Station**   | **Geographical Location**                                                                   |
|---------------|---------------------------------------------------------------------------------------------|
| **Station 1** | First Release (FRE)                                                                         |
| **Station 2** | South America, Canada, India, France, South Africa, Switzerland, Korea, Germany, Norway     |
| **Station 3** | Asia-Pacific, United Kingdom, Australia, Japan, United Arab Emirates, US Gov High Sovereign |
| **Station 4** | Europe, Middle East, and Africa                                                             |
| **Station 5** | North America                                                                               |

## Project Operations Release Notes
- Project Operations latest release notes for [resource/non-stocked](whats-new-feb-2025-resource-based.md) scenario.
- Project Operations latest release notes for [lite deployment](../pro/whats-new/whats-new-feb-2025-lite.md) scenario.
- Project Operations latest release notes for [stocked/production](../prod-pma/whats-new/whats-new-Feb-2024-stocked.md) scenario.

## Project Operations Latest Version

| **Project Operations on Dataverse Environment** | **Project Management and Accounting in Finance and Operations Apps Environment** | **Project App on Dataverse Environment** |
|:-----------------------------------------------:|:--------------------------------------------------------------------------------:|:----------------------------------------:|
|                   4.140.0.1087                  |                                      10.0.43                                     |                1.0.140.653              |

> [!IMPORTANT]
> - The minimum supported versions of Project Operations and Project in Dataverse are 4.28.0.XX and 1.0.28.X respectively.
> - For Project Operations resource/non-stocked scenario, we recommend that you use Dual-write orchestration version 2.3.1.15 or higher.
> - If you're using an older version of either product, contact Microsoft support for assistance in upgrading.

## Release Schedule for Project Operations on Dataverse Environment

> [!IMPORTANT]
> - New updates for Project Operations on the Dataverse Environment are released on a monthly basis.
> - Customers are expected to receive their **"Auto Update"** approximately **one week** after the **"Self Update Start Date"**.
> - The **"Auto Update Start Date"** marks the beginning of the upgrade rollout from Microsoft.
> - **"Auto Updates"** are managed by Microsoft and are executed on the dates specified in the following table. The timing of these updates adheres to the maintenance window defined for your environment. For instructions on defining a maintenance window, see [Manage Maintenance Window](/power-platform/admin/manage-maintenance-window).
> - If an **"Auto Update"** can't complete, the update is attempted again the next day for up to one week, within the defined maintenance window for your environment.
> - Depending on the station, region, and other factors, _**the release may reach customers within the stipulated one-week timeframe.**_

## Standard Release Cycle

| **Version/Station** | **Station 1**              | **Station 1**              | **Station 2**              | **Station 2**              | **Station 3**              | **Station 3**              | **Station 4**              | **Station 4**              | **Station 5**              | **Station 5**              |
|---------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|
|                     | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** |
| **4.140.0.651** <br> Refer HotFix (**4.140.0.1087**)      | April 25, 2025             | April 25, 2025             | April 25, 2025             | May 02, 2025               | May 02, 2025               | CANCELED              | CANCELED               | CANCELED               | CANCELED               | CANCELED              |
| **4.141.0.975** <br> Refer HotFix (**4.140.0.1552**)      | May 23, 2025               | CANCELED               | May 23, 2025               | CANCELED               | CANCELED               | CANCELED               |CANCELED               | CANCELED              | CANCELED              | CANCELED             |
| **4.142.0.X**       | June 18, 2025              | June 20, 2025              | June 20, 2025              | June 27, 2025              | June 27, 2025              | July 04, 2025              | July 04, 2025              | July 11, 2025              | July 11, 2025              | July 18, 2025              |
| **4.143.0.X**       | July 11, 2025              | July 18, 2025              | July 18, 2025              | July 25, 2025              | July 25, 2025              | August 01, 2025            | August 01, 2025            | August 09, 2025            | August 09, 2025            | August 16, 2025            |
| **4.144.0.X**       | August 08, 2025            | August 15, 2025            | August 15, 2025            | August 22, 2025            | August 22, 2025            | August 29, 2025            | August 29, 2025            | September 05, 2025         | September 05, 2025         | September 12, 2025         |
| **4.145.0.X**       | September 12, 2025         | September 19, 2025         | September 19, 2025         | September 26, 2025         | September 26, 2025         | October 03, 2025           | October 03, 2025           | October 10, 2025           | October 10, 2025           | October 17, 2025           |

## HotFix Release Cycle

| **Version/Station** | **Station 1**              | **Station 1**              | **Station 2**              | **Station 2**              | **Station 3**              | **Station 3**              | **Station 4**              | **Station 4**              | **Station 5**              | **Station 5**              |
|---------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|
|                     | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** |
| **4.140.0.1087**    | May 13, 2025               | May 13, 2025               | May 13, 2025               | May 13, 2025               | May 14, 2025               | May 14, 2025               | May 14, 2025               | May 14, 2025               | May 16, 2025               | May 23, 2025               |
| **4.141.0.1552**    | May 30, 2025               | June 06, 2025               | May 30, 2025               | June 06, 2025               | May 30, 2025               | June 06, 2025               | June 06, 2025               | June 13, 2025               | June 13, 2025               | June 20, 2025               |


## Release Schedule for Project Management and Accounting in the Finance and Operations Apps Environment

See the [Service Update Availability](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases) for the Project Management and Accounting in the Finance and Operations Apps Environment Release Schedule. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
