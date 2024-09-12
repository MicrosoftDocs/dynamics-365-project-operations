---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: abriccetti
ms.topic: conceptual
ms.custom: 
  - bap-template
  - evergreen
ms.date: 08/01/2024
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Operations updates

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_



## Project Operations components

Dynamics 365 Project Operations consists of two components:

- Project Operations on Dataverse environment covers capabilities from opportunity to proforma invoicing. Dataverse is used in the lite deployment and resource/non-stocked scenarios deployment of Project Operations.
- Project management and accounting in the Dynamics 365 Finance environment covers expense management capabilities, project accounting, and revenue recognition. The finance and operations app environment is used in Project Operations for resource/non-stocked based scenarios and Project Operations for stocked/production-based scenarios.

## Project Operations release notes
- Project Operations latest release notes for [Resource/non-stocked](whats-new-july-2024-resource-based.md) scenario.
- Project Operations latest release notes for [Lite deployment](../pro/whats-new/whats-new-july-2024-lite.md) scenario.
- Project Operations latest release notes for [stocked/production](../prod-pma/whats-new/whats-new-Feb-2024-stocked.md) scenario.

## Project Operations latest version

| Project Operations on Dataverse environment | Project management and accounting in finance and operations apps environments | Project App on Dataverse Environments |
| --- | --- | --- |
| 4.108.0.53 | 10.0.40 | 1.0.108.52 |

> [!NOTE]
> The minimum supported versions of Project Operations and Project in Dataverse are 4.28.0.XX and 1.0.28.X respectively. If you are using an older version of either product, contact Microsoft support for assistance in upgrading

For Project Operations Resource/non-stocked scenario, we recommend that you use dual-write Orchestration version 2.3.1.15 or higher.

## Release schedule for Project Operations on Dataverse environment

Updates for Project Operations on Dataverse environment are available monthly. 

| Station | Region | Current version number | Auto updates start for Lite or Resource/non-stocked deployments * | Next version number | Next version number available for self-update | Auto updates start for Next version |
|-----------|-----------------------|-----------------|--------------------|---------------------|---------------------|---------------------|
| Station 1 |   &nbsp;              |    &nbsp;       | &nbsp;             |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | First Release         |  4.108.0.53     | September 2, 2024   | 4.120.0.x    | September 27, 2024          | October 4, 2024   |
| Station 2 |   &nbsp;              |    &nbsp;       | &nbsp;             |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | South America         |  4.108.0.53     | September 2, 2024   | 4.120.0.x   | October 4, 2024          | October 11, 2024   |
|   &nbsp;  | Canada                |  4.108.0.53     | September 2, 2024   | 4.120.0.x    | October 4, 2024          | October 11, 2024   |
|   &nbsp;  | India                 |  4.108.0.53     | September 2, 2024   | 4.120.0.x    | October 4, 2024          | October 11, 2024   |
|   &nbsp;  | France                |  4.108.0.53     | September 2, 2024   | 4.120.0.x    | October 4, 2024         | October 11, 2024   |
|   &nbsp;  | South Africa          |  4.108.0.53     | September 2, 2024   | 4.120.0.x   | October 4, 2024          | October 11, 2024   |
|   &nbsp;  | Switzerland           |  4.108.0.53     | September 2, 2024   | 4.120.0.x    | October 4, 2024          | October 11, 2024   |
| Station 3 |      &nbsp;           |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | Japan                 |  4.108.0.53     | September 6, 2024   | 4.120.0.x    | October 11, 2024         | October 18, 2024   |
|   &nbsp;  | Asia Pacific          |  4.108.0.53     | September 6, 2024   | 4.120.0.x    | October 11, 2024          | October 18, 2024   |
|   &nbsp;  | Great Britain         |  4.108.0.53     | September 6, 2024   | 4.120.0.x    | October 11, 2024          | October 18, 2024   |
|   &nbsp;  | Oceania               |  4.108.0.53     | September 6, 2024   | 4.120.0.x    | October 11, 2024          | October 18, 2024    |
|   &nbsp;  | United Arab Emirates  |  4.108.0.53     | September 6, 2024   | 4.120.0.x    | October 11, 2024          | October 18, 2024   |
| Station 4 |     &nbsp;            |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | Europe                |  4.108.0.53     | September 09, 2024   | 4.120.0.x    | October 18, 2024          | October 25, 2024    |
| Station 5 |     &nbsp;            |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | North America         |  4.108.0.53     | September 12, 2024  | 4.120.0.x   | October 25, 2024          | November 1, 2024    |

__\*__ Auto updates are managed by the Dataverse platform and run on the date defined in the previous table. Time of run respects the maintenance window defined for your environment. To define a maintenance window for your environment, see [Manage maintenance window](/power-platform/admin/manage-maintenance-window).

If auto update is unable to complete, update of your environment on the date defined in the previous table. It will try again the next day for up to a week during the defined maintenance window for your environment

> [!NOTE]
> Hotfix version **4.106.0.88** is available for versions **4.106.0.25** and **4.106.0.58**. Customers are encouraged to initiate a self-upgrade to address any issues encountered with the earlier version.

## Release schedule for Project management and accounting in the finance and operations apps environment

Refer to the [Service update availability](/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-releases?toc=%2fdynamics365%2ffinance%2ftoc.json) for the release schedule for Project management and accounting in the finance and operations apps environment. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
