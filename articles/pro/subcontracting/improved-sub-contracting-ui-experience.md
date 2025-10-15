---
title: Improved Subcontracting user experience
description: This article explains how to enable the improved subcontracting module's user experience and lists the set of changes. 
author: nimaski
ms.date: 10/10/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Improved subcontracting user experience

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP and Project Operations Core_

This article presents an overview of the improved user experience in the **Subcontracting** module in Microsoft Dynamics 365 Project Operations.

## Prerequisites

To use the enhanced subcontracting module's user experience, enable the following feature:
- **Enable Subcontracting UX enhancements for smoother navigation and insights**

Steps to enable feature
1. Sign in to **Microsoft Dynamics 365 Project Operations**.
1. In the left navigation, switch the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. You see a list of organization units. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, select **Feature Control** in the top ribbon.
1. Select **Enable Subcontracting UX enhancements for smoother navigation and insights**.
1. Select **Enable** in the confirmation dialog.

> [!NOTE]
> To revert to the previous experience, disable the feature by selecting **Disable Subcontracting UX enhancements for smoother navigation and insights** under **Feature Control**.

## Improvements

The following UX improvements are introduced in the Subcontracting module with this feature. Here's the first set of changes; more enhancements are planned in upcoming releases under the same feature flag.

### Enhanced Subcontract main form
The subcontract main form is redesigned with the following updates:
1. Fields under the **General** tab are now logically organized into sections for subcontract details, vendor information, and contracting unit details.
1. A new **Subcontract Price Lists** tab is added for better handling and management of price lists.
1. A new **Insights** tab provides visibility into:
    - Actuals logged against the subcontract.
    - Subcontract line consumption.
    - Vendor invoice details related to the subcontract.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
