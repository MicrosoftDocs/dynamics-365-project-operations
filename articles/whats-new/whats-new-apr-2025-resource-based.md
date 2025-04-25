---
title: What's new April 2025 - Project Operations for resource/non-stocked based scenarios
description: This article provides information about the quality updates that are available in the April 2025 release of Microsoft Dynamics 365 Project Operations for resource/non-stocked based scenarios.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom: 
  - bap-template
  - evergreen
ms.date: 04/25/2025
ms.reviewer: johnmichalak

---

# What's new April 2025 - Project Operations for resource/non-stocked based scenarios

[!INCLUDE[banner](../includes/banner.md)]

**Applies To:**  Project Operations for resource/non-stocked based scenarios.

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.140.0.239.
- Project management and accounting in a Microsoft Dynamics 365 Finance environment version 10.0.43.

## Project Operations dual-write maps updates

The following table shows the Dual-write maps that are modified or added in the Project Operations March 2024 release.

| **Entity map** | **Updated version** | **Comments** |
| --- | --- | --- |
| Project Operations integration contract line milestones (msdyn_contractlinescheduleofvalues) | 1.0.0.6 | Latest version updated |

For a current list and versions of Project Operations dual-write maps, see [Project Operations dual-write map versions](../environment/resource-dual-write-maps.md).

Always run the latest version of the map in your environment and enable all related table maps as you update your Project Operations Dataverse solution and Finance solution version. Some features and capabilities might not work correctly if the latest version of the map isn't activated. You can view the active version of the map in the **Version** column on the **Dual-write** page. To activate a new version of the map, select **Table map versions**, select the latest version, and then save the selected version. If you customized an out-of-box table map, reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).

If you encounter an issue when you start the map, follow the instructions in the [Missing table columns issue on maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-troubleshooting-finops-upgrades#missing-table-columns-issue-on-maps) section of the Dual-write troubleshooting guide.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Time Entry |**Time Entry Agent** <br><br> This agent creates draft time entries for team members based on their project assignments, bookings or previous week's entries and allows them to review the entries through MS Teams. The agent can also generate external comments for all entries, enhanced by Outlook meeting details. Finally, team members will also receive alerts for missing submissions| |
| Actuals |**Corrections for entry journal actuals** <br><br> Actuals which were created via entry journals can now be corrected via our correction journal process.| |
| Approvals |**Approvals Agents** <br><br> This agent reviews submitted time, expense, and material usage entries and classifies them as "Ready for Approval" or "Needs review". The classification can assist project managers in making approvals decisions. The agent also includes an auto-approve mode where records marked as "Ready for approval" are automatically approved.| |
| Project Financials |**Use the modern architecture for existing legal entities with project data** <br><br> In the 10.0.43 release version of Finance & Operations, the "Use the modern architecture for existing legal entities with project data" feature lets you complete all existing transactions and close existing projects in the Project management and accounting module.| |
| Project Financials |**Enable actuals validation to prevent invalid actuals** <br><br> This optional feature enables more validations for actuals records that are integrated from Microsoft Dataverse into the finance and operations infrastructure. This feature pre-validates the actuals before allowing records to be created during the import from staging process.| |

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference No.** | **Quality Update** |
| --- | --- | --- |

### Project management and accounting in Finance

For information about the bug fixes that are included in this update, sign in to Microsoft Dynamics 365 Lifecycle Services, and view the [KB article](https://fix.lcs.dynamics.com/Issue/Details?kb=0&bugId=988112&dbType=3&qc=43dd064fcfe4d60f5434aafc5c6c738ffe2c57da200521808114fae9ff567a68).
