---
title: Configure Schedule Board to show contract workers and subcontracted capacity
description: Learn how to configure the Schedule Board in Dynamics 365 Project Operations to display subcontracted resource capacity and contract workers for efficient staffing.
author: rumant
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Configure Schedule Board to show contract workers and subcontracted capacity

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

You can use Schedule Board in Microsoft Dynamics 365 Project Operations to search for resources in two ways:

- General resource search without the context of any specific project-based resource requirement.
- Requirement-specific resource search where the project requirement provides the context for the resources suggested.

To notify the schedule board of subcontracted resource capacity and contract workers, update the Schedule Board settings. These updates include:

- Update Schedule Board settings for general resource search.
- Update Schedule Board settings for requirement-based resource search.

## Update Schedule Board settings for general resource search

### Update filters for general resource search

When you search for a resource, update the filters available on the schedule board so that you can also search for external resources by specifying any or all of the following options:

- Worker type, whether the resources shown are contract workers or employees.
- Vendor company to which a resource belongs.
- Resources that belong to a specific subcontract or subcontract line.

### Update retrieve resource query

Update the query used for searching to use these additional filter attributes. Use the following steps to update Schedule Board configuration for general resource search:  

1. Open **Schedule Board Settings** for a specific Schedule Board.
1. Open the **General settings** tab and scroll to **Other settings**.
1. In the list of settings in this section, update the **Filter Layout** to **Default Filter Layout for Project Operations  Core**.
1. Update **Retrieve Resources Query** to **Default Retrieve Resources Query for Project Operations  Core**.

:::image type="content" source="../media/BoardSettings.png" alt-text="Screenshot of updating Schedule Board settings for general resource search.":::

## Update Schedule Board settings for requirement–based resource search

### Update filters for requirement-specific resource search

When you search for a resource, update the filters available on the schedule board so that you can also search for external resources by specifying any or all of the following options:

- Worker type, whether the resources shown are contract workers or employees.
- Vendor company to which a resource belongs.
- Resources that belong to a specific subcontract or subcontract line.

### Update retrieve resource query for requirement-specific resource search

Update the query that you use for searching to include these extra filter attributes. Use the following steps to update the Schedule Board configuration for requirement-based resource search:

1. Open **Schedule Board Settings** for a specific Schedule Board. Select **Open Default settings** to open the settings for requirement-specific search.
1. Open the **General settings** tab and scroll to **Other settings**.
1. In the list of settings in this section, update the **Filter Layout** to **Default Filter Layout for Project Operations  Core**.
1. Update **Retrieve Resources Query** to **Default Retrieve Resources Query for Project Operations  Core**.
1. Open the **Schedule Types** tab and go to **Project**.
1. Under the settings for **Project**, update **Schedule Assistant Retrieve Resources Query** to **Default Retrieve Resources Query for Project Operations  Core** and update **Schedule Assistant Retrieve Constraints Query** to **Default Retrieve Constraints Query for Project Operations  Core**.

:::image type="content" source="../media/SASettings.png" alt-text="Screenshot of updating Schedule Board settings for requirement-based resource search.":::

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
