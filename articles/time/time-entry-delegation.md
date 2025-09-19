---
title: Time Entry Delegation (preview)
description: This article explains how team members can give access to create, modify and submit time entries on their behalf to another resource in their organisation.
author: mohitmenon
ms.date: 09/19/2025
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Time Entry Delegation feature overview (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Time Entry Delegation allows users to give another resource temporary access to view, create, modify and submit time entries on their behalf. Team members can assign one delegate for limited time period and keep track of time entries created or submitted by their delegates.

This article provides an overview of the Time Entry Delegation feature, which is currently released as a Production Ready Preview. The article contains the following sections:

- Enable Time Entry Delegation (Production Ready Preview) feature
- Delegate setup experience
- Logging time as a delegate
- Keeping track of time entries logged by a delegate
- Current limitations of the feature

## Enable Time Entry Delegation (Preview) feature

To enable Time Entry Delegation, follow these steps.

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.145.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Time Entry Delegation (Preview) feature**, and then select **OK**. If the text **Disable Time Entry Delegation (Preview)** is shown instead, it means the feature is already enabled.

After the feature is enabled, a new menu item named **Delegates (Production Ready Preview)** appears in the **My Work** section of the Project Operations and Team Member apps.

## Delegate Setup Experience


