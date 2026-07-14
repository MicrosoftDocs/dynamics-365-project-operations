---
title: What's new June 2026 - Project Operations Core
description: Learn about quality updates that are available in the June 2026 release of Microsoft Dynamics 365 Project Operations Core.
author: mohitmenon
ms.author: mohitmenon
ms.topic: whats-new
ms.custom:
  - evergreen
  - bap-template
ms.date: 07/01/2026
ms.update-cycle: 1095-days
ms.reviewer: johnmichalak
---

# What's new June 2026 - Project Operations Core

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.168.3456.2.

## Features included in this release

| **Feature area** | **Feature name** | **More information** |
| --- | --- | --- |
| Project Budget Management | **Enable Multiple Project Budget Drafts** <br><br> This feature enables users to create and maintain multiple draft budget versions for a project. The feature enables comparing of alternatives to select the appropriate budget for submission and approval. To improve usability, budgets are now available in the left navigation pane for quick access and easier management of multiple budget drafts. In addition, budget actions are conveniently available next to each budget version on the Budget tab, enabling faster administration and version control. | [Project Budget Management](..//budget/projectbudgetmanagement.md) |
| Time Entry | **Modern Grid as the default time entry interface** <br><br> The Modern Time Entry Grid is now the default time entry grid interface within Project Operations. This change includes enhancements that let you show or hide columns visually without losing their information. | [Modern Time Entry Grid](../../time/modern-time-entry-grid.md) |

## Quality updates

### Project Operations on Dataverse

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| Billing | 5989595 | Importing Invoice line transactions doesn't trigger recalculation on parent Invoice line or Invoice. |
| Pricing | 6241494 | Role price caching creates discrepancies in cost price calculation when there's a markup over purchase price. |
| Pricing | 6269966 | When field level security is enabled on Role Price price, Quote Line Detail price isn't defaulted despite unit matching with price list. |
| Pricing | 6307015 | Deletion of estimate lines fails due to cascading delete conflict. |
| Project Estimates | 5820605 | Planned sales display in sales amount in cost currency instead of converting from sales Currency. |
| Sales | 6296854 | Fee Amount calculated field can produce negative values when base amount is zero on project-based quote lines. |
| Subcontracting | 6364896 | Estimates show $0 for contract worker booked via Schedule Board to fulfill generic resource requirement. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
