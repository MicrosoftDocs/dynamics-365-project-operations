---
title: What's new 2023 wave 1 early access - Project Operations Core deployment
description: This article provides information about the features available in the 2023 wave 1 early access release of Project Operations Core deployment.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: ramagadu
---

# What's new 2023 wave 1 early access - Project Operations Core deployment

_**Applies To:** Project Operations Core_

This article applies to the following Microsoft Dynamics 365 Project Operations components and versions:

- Project Operations on Microsoft Dataverse environment version 4.84.0.9

The release is only applied when an environment is [opted into Early Access](/power-platform/admin/opt-in-early-access-updates#how-to-enable-early-access-updates).

## Removed feature flags in this release

The following table lists the feature flags removed from Feature control. These features are enabled by default when you update to this build version.

| Feature area | Feature flag name | More information |
| --- | --- | --- |
|Billing and Pricing|Enable material pricing methods.|[Set up cost and sales rates for materials](/dynamics365/project-operations/pricing-costing/set-up-cost-sales-rates-materials).|
|Billing and Pricing|Enable bulk confirm.|[Bulk-confirm proforma project-based invoices](/dynamics365/project-operations/proforma-invoicing/bulk-confirm-project-invoices).|

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Opportunity Management|**Minimize the creation of roles and categories for performance**. </br>This feature works to minimize this data creation to what’s included in the quote line details and ultimately what’s included in the associated project plan. </br>In metadata updates, changes were made to quote and contract line forms to display both overrides and global tables. New and delete buttons were reinstated for override subgrids, and quote and contract line forms were added for all override types. The override main forms now include references to quote or contract lines. In UI, references for overrides are locked in noncreate forms, and unsupported billing type options like null, complimentary, and not available were removed. ||

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3183709|Role Prices configuration missing logic around Pricing Dimensions </br></br>The logic within **Amount based pricing dimensions** has been updated to reflect applicable to cost, applicable to purchase, applicable to sales for the Role Price creation. You can only set the Resource, Resourcing Unit (etc.) field(s) if it's applicable and configured within **Settings** > **Amount Based Pricing Dimensions**. Those fields for Role Price are now hidden to avoid confusion if there's no dimension configuration.|
