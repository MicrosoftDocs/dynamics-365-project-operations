---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: abriccetti
ms.topic: concept-article
ms.custom: 
  - bap-template
  - evergreen
ms.date: 02/24/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Operations Updates

_**Applies To:** Project Operations Integrated with Enterprise Resource Planning (ERP), Project Operations Core, and Project Operations for manufacturing-based scenarios_

## Project Operations Components

Dynamics 365 Project Operations consists of two components:

- Project Operations on Dataverse environment covers capabilities from opportunity to proforma invoicing. Dataverse is used in the Project Operations Core and Project Operations Integrated with ERP scenarios deployment of Project Operations.
- Project Management and Accounting in the Dynamics 365 Finance environment covers expense management capabilities, project accounting, and revenue recognition. The finance and operations apps environment is used in Project Operations Integrated with ERP and Project Operations for manufacturing.

## Project Operations Station & Geographical Regions

| **Station**   | **Geographical Location**                                                                                           |
|---------------|---------------------------------------------------------------------------------------------------------------------|
| **Station 1** | First Release (FRE)                                                                                                 |
| **Station 2** | South America, Canada, India, France, South Africa, Switzerland, Korea, Germany, Norway                             |
| **Station 3** | Asia-Pacific, United Kingdom, Japan, United Arab Emirates, US Government Community Cloud High (GCC High)            |
| **Station 4** | Europe, Middle East, and Africa                                                                                     |
| **Station 5** | North America and Australia                                                                                         |

## Project Operations Release Notes
- Project Operations latest release notes for [Project Operations Integrated with ERP](whats-new-feb-2026-resource-based.md) scenario.
- Project Operations latest release notes for [Core deployment](../pro/whats-new/whats-new-feb-2026-lite.md) scenario.
- Project Operations latest release notes for [Project Operations for manufacturing](../prod-pma/whats-new/whats-new-Feb-2024-stocked.md) scenario.

## Project Operations Latest Version

| **Project Operations on Dataverse Environment** | **Project Management and Accounting in Finance and Operations Apps Environment** | **Project App on Dataverse Environment** |
|:-----------------------------------------------:|:--------------------------------------------------------------------------------:|:----------------------------------------:|
|                   4.162.0.962                   |                                      10.0.46                                     |                1.0.162.956               |

> [!IMPORTANT]
> - The minimum supported versions of Project Operations and Project in Dataverse are 4.28.0.XX and 1.0.28.X respectively.
> - For Project Operations Integrated with ERP scenario, we recommend that you use Dual-write orchestration version 2.3.1.15 or higher.
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
| **4.145.0.1040** <br> Refer to HotFix (**4.145.0.1361**) | September 12, 2025         | September 19, 2025         | September 19, 2025         | September 26, 2025         | September 26, 2025         | October 03, 2025           | October 03, 2025           | October 10, 2025           | October 10, 2025           | October 17, 2025           |
| **4.160.0.1159**  <br> Refer to HotFix (**4.160.0.2877**) | October 17, 2025           | October 24, 2025           | October 24, 2025           | CANCELED          | October 24, 2025           | CANCELED          | CANCELED          | CANCELED          | CANCELED          | CANCELED          |
| **4.161.0.1688**  | January 06, 2025          | January 20, 2026          | January 06, 2025          | January 20, 2026          | January 06, 2025          | January 20, 2025          | January 13, 2026           | CANCELED           | January 13, 2026           | CANCELED           |
| **4.162.0.962**    | February 02, 2026           | February 02, 2026           | February 02, 2026           | February 06, 2026          | February 02, 2026           | February 06, 2026          | February 06, 2026          | February 19, 2026          | February 06, 2026          | February 19, 2026          |
| **4.163.0.581**   | February 20, 2026          | February 27, 2026          | February 27, 2026          | March 13, 2026             | February 27, 2026          | March 13, 2026             | March 13, 2026             | March 27, 2026             | March 13, 2026             | March 27, 2026             |
| **4.164.0.x**     | March 20, 2026             | March 27, 2026             | March 27, 2026             | April 10, 2026             | March 27, 2026             | April 10, 2026             | April 10, 2026             | April 24, 2026             | April 10, 2026             | April 24, 2026             |

## HotFix Release Cycle

| **Version/Station** | **Station 1**              | **Station 1**              | **Station 2**              | **Station 2**              | **Station 3**              | **Station 3**              | **Station 4**              | **Station 4**              | **Station 5**              | **Station 5**              |
|---------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|
|                     | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** | **Self Update Start Date** | **Auto Update Start Date** |
| **4.145.0.1361**    | Not Applicable             | Not Applicable             | Not Applicable             | Not Applicable             | October 24, 2025           | Not Applicable             | October 24, 2025           | October 24, 2025           | October 24, 2025           | October 24, 2025           |
| **4.160.0.2288**    | November 11, 2025             | November 11, 2025             | November 11, 2025             | November 11, 2025             | November 11, 2025           | November 14, 2025             | November 14, 2025           | CANCELED           | November 14, 2025           | CANCELED           |
| **4.160.0.2774**    | November 21, 2025             | November 21, 2025             | November 21, 2025             | November 21, 2025             | November 21, 2025           | November 21, 2025             | November 21, 2025           | December 03, 2025           | November 21, 2025           | December 03, 2025           |
| **4.160.0.2877**    | December 09, 2025             | December 09, 2025             | December 09, 2025             | December 09, 2025             | December 09, 2025           | December 09, 2025             | December 09, 2025           | December 10, 2025           | December 09, 2025           | December 10, 2025           |



## Release Schedule for Project Management and Accounting in the Finance and Operations Apps Environment

See the [Service Update Availability](/dynamics365/fin-ops-core/dev-itpro/get-started/public-preview-releases) for the Project Management and Accounting in the Finance and Operations Apps Environment Release Schedule. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
