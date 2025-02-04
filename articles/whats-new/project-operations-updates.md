---
title: Project Operations updates
description: This article provides information about the released versions of Dynamics 365 Project Operations.
author: abriccetti
ms.topic: conceptual
ms.custom: 
  - bap-template
  - evergreen
ms.date: 01/27/2025
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
- Project Operations latest release notes for [Resource/non-stocked](whats-new-dec-2024-resource-based.md) scenario.
- Project Operations latest release notes for [Lite deployment](../pro/whats-new/whats-new-dec-2024-lite.md) scenario.
- Project Operations latest release notes for [stocked/production](../prod-pma/whats-new/whats-new-Feb-2024-stocked.md) scenario.

## Project Operations latest version

| Project Operations on Dataverse environment | Project management and accounting in finance and operations apps environments | Project App on Dataverse Environments |
| --- | --- | --- |
| 4.122.0.690 | 10.0.41 | 1.0.122.685 |

> [!NOTE]
> The minimum supported versions of Project Operations and Project in Dataverse are 4.28.0.XX and 1.0.28.X respectively. If you are using an older version of either product, contact Microsoft support for assistance in upgrading

For Project Operations Resource/non-stocked scenario, we recommend that you use dual-write Orchestration version 2.3.1.15 or higher.

## Release schedule for Project Operations on Dataverse environment

Updates for Project Operations on Dataverse environment are available monthly. 

| Station | Region | Current Version Number | Auto Updates Start Date for Lite or Resource/Non-Stocked Deployments * | Next Version Number | Next Version Number Available For Self Update | Auto Updates Start For Next Version |
|-----------|---------------|-----------------|-------------------------|--------------|------------------------|--------------------|
| Station 1 | &nbsp;        | &nbsp;          | &nbsp;                  | &nbsp;       | &nbsp;                 | &nbsp;             |
| &nbsp;    | First Release | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 14, 2025      | February 21, 2025  |
| Station 2 | &nbsp;        | &nbsp;          | &nbsp;                  | &nbsp;       | &nbsp;                 | &nbsp;             |
| &nbsp;    | Canada        | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 21, 2025      | February 28, 2025  |
| &nbsp;    | India         | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 21, 2025      | February 28, 2025  |
| &nbsp;    | France        | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 21, 2025      | February 28, 2025  |
| &nbsp;    | South Africa  | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 21, 2025      | February 28, 2025  |
| &nbsp;    | Switzerland   | 4.123.0.510      | February 05, 2025        | 4.124.0.x    | February 21, 2025      | February 28, 2025  |
| &nbsp;    | Korea         | 4.123.0.510      | NA                        | 4.124.0.x    | February 21, 2025      | February 28, 2025   |
| Station 3 | &nbsp;        | &nbsp;          | &nbsp;                  | &nbsp;       | &nbsp;                 | &nbsp;             |
| &nbsp;    | Germany       | 4.123.0.510      | February 07, 2025        | 4.124.0.x    | February 28, 2025      | March 07, 2025  |
| Station 4 | &nbsp;        | &nbsp;          | &nbsp;                  | &nbsp;       | &nbsp;                 | &nbsp;             |
| &nbsp;    | UK            | 4.122.0.690      | December 16, 2024        | 4.123.0.510    | February 07, 2025      | February 13, 2025  |
| Station 5 | &nbsp;        | &nbsp;          | &nbsp;                  | &nbsp;       | &nbsp;                 | &nbsp;             |
| &nbsp;    | USA           | 4.122.0.690      | December 20, 2024        | 4.123.0.510    | February 13, 2025      | February 20, 2025  |

__\*__ Auto updates are managed by the Dataverse platform and run on the date defined in the previous table. Time of run respects the maintenance window defined for your environment. To define a maintenance window for your environment, see [Manage maintenance window](/power-platform/admin/manage-maintenance-window).

If auto update is unable to complete, update of your environment on the date defined in the previous table. It will try again the next day for up to a week during the defined maintenance window for your environment

> [!NOTE]
> Hotfix Version **4.123.0.338** is available for versions **4.123.0.510**. Customers are encouraged to initiate a self-upgrade to address any issues encountered with the earlier versions.

## Release schedule for Project management and accounting in the finance and operations apps environment

See the [Service update availability](/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-releases?toc=%2fdynamics365%2ffinance%2ftoc.json) for the Project management and accounting in the finance and operations apps environment release schedule. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
