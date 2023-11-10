---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: sigitac
ms.date: 09/18/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Project Operations updates

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_



## Project Operations components

Dynamics 365 Project Operations consists of two components:

- Project Operations on Dataverse environment covers capabilities from opportunity to proforma invoicing. Dataverse is used in the lite deployment and resource/non-stocked scenarios deployment of Project Operations.
- Project management and accounting in the Dynamics 365 Finance environment covers expense management capabilities, project accounting, and revenue recognition. The finance and operations app environment is used in Project Operations for resource/non-stocked based scenarios and Project Operations for stocked/production-based scenarios.

## Project Operations release notes
- Project Operations latest release notes for [Resource/non-stocked](whats-new-sept-2023-resource-based.md) scenario.
- Project Operations latest release notes for [Lite deployment](../pro/whats-new/whats-new-sept-2023-lite.md) scenario.
- Project Operations latest release notes for [stocked/production](../prod-pma/whats-new/whats-new-sept-2023-stocked.md) scenario.

## Project Operations latest version

| Project Operations on Dataverse environment | Project management and accounting in finance and operations apps environments | 
| --- | --- |
| 4.87.0.190 | 10.0.35 |

For Project Operations Resource/non-stocked scenario, we recommend that you use dual-write Orchestration version 2.3.1.15 or higher.

## Release schedule for Project Operations on Dataverse environment

Updates for Project Operations on Dataverse environment are available monthly. 

| Station | Region | Current version number | Auto updates for Lite deployment * | Auto updates for Resource/non-stocked deployment * | Next version number | Next version generally available |
|-----------|-----------------------|-----------------|--------------------|---------------------|---------------------|---------------------|
| Station 1 |   &nbsp;              |    &nbsp;       | &nbsp;             |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | First Release         |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 10, 2023   |
| Station 2 |   &nbsp;              |    &nbsp;       | &nbsp;             |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | South America         |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | Canada                |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | India                 |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | France                |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | South Africa          |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | Switzerland           |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
| Station 3 |      &nbsp;           |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | Japan                 |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | Asia Pacific          |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | Great Britain         |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | Oceania               |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
|   &nbsp;  | United Arab Emirates  |  4.87.0.190     | October 27, 2023   | October 27, 2023    | 4.88.0.127          | November 17, 2023   |
| Station 4 |     &nbsp;            |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | Europe                |  4.87.0.190     | November 3, 2023   | November 3, 2023    | 4.88.0.127          | December 1, 2023    |
| Station 5 |     &nbsp;            |     &nbsp;      |     &nbsp;         |      &nbsp;         |      &nbsp;         |      &nbsp;         |
|   &nbsp;  | North America         |  4.87.0.190     | November 10, 2023  | November 10, 2023   | 4.88.0.127          | December 8, 2023    |

__\*__ Auto updates are managed by the Dataverse platform and run on the date defined in the table above. Time of run respects the maintenance window defined for your environment. To define a maintenance window for your environment, see [Manage maintenance window](/power-platform/admin/manage-maintenance-window).

If auto update is unable to complete, update of your environment on the date defined in the above table. It will try again the next day for up to a week during the defined maintenance window for your environment

## Release schedule for Project management and accounting in the finance and operations apps environment

Please refer to the [Service update availability](/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-releases?toc=%2fdynamics365%2ffinance%2ftoc.json) for the release schedule for Project management and accounting in the finance and operations apps environment. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
