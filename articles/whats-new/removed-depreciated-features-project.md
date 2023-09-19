---
title: Removed or deprecated features in Dynamics 365 Project Operations
description: This article describes features that have been removed, or that are planned for removal from Dynamics 365 Project Operations.
author: sigitac
ms.date: 09/15/2023
ms.topic: article
ms.prod:
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Removed or deprecated features in Dynamics 365 Project Operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_

This article describes features that have been removed, or that are planned for removal from Dynamics 365 Project Operations.

- A *removed* feature is no longer available in the product.
- A *deprecated* feature is not in active development and may be removed in a future update.

This list is intended to help you consider these removals and deprecations for your own planning.

> [!NOTE]
> Detailed information about objects in finance and operations apps can be found in the [**Technical reference reports**](/dynamics/s-e/global/axtechrefrep_61). You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of finance and operations apps.

## Features removed or deprecated in the Project Operations October 2023 release

### Project management and accounting adjustment parameter for "Invoiced"

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Transactions are much more difficult to audit if they are adjusted after they have been invoiced. This behavior causes confusion for the small number of users who use this functionality.  |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By October 1, 2024, we will hide the parameter and change the system behavior so that adjustment transactions cannot be created for invoiced transactions. |

### Project management and accounting "Allow for projects with multiple funding sources" parameter

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | This parameter was originally added before feature management was available. However, it's no longer required, because the functionality can now be safely enabled for sales orders and multiple funding sources. Multiple funding sources should now always be optionally configurable in the project contract. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By October 1, 2024, we will hide the parameter and change the system behavior so that the system behaves as if the parameter is always enabled, but multiple funding sources aren't required. |

## Features removed or deprecated in the Project Operations March 2022 release

### Project management and accounting "Always create adjustment transaction" parameter

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Adjustment transactions are required for audit purposes. After deprecation, this parameter is hidden. The system always creates adjustment transactions, just as it currently does when the parameter is set to **Yes**. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Removed as of 10.0.32.|

### Project management and accounting "Use adjustment date as new project date" parameter

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | This parameter was originally used to allow for adjustments when a fiscal period was closed. However, it's no longer required, because the accounting date of the transaction can be changed to the first date of the open period, if it's configured. The project date must not be changed, because it represents the date when transaction occurred. The project date no longer changes on adjustments. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Removed as of 10.0.32.

### Resource request workflow in Project Operations for stocked/production-based scenarios

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated because of low usage and transaction volume limitations. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated as of 10.0.32 with the removal of enabling  workflow. Many objects marked as obsolete and some objects removed. |

### Project invoice proposal page without Header and Lines views

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated because of improvements to the page that was introduced together with the **Use Project invoice proposal and invoice journal forms with the Header and Lines view** feature key. |
| **Replaced by another feature?** | Yes |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios; Project Operations for resource/ non-stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will turn off the earlier (legacy) page and turn on the **Use Project invoice proposal and invoice journal forms with the Header and Lines view** feature key by default. |

## Features removed or deprecated in the Project Operations December 2021 release

### Collaboration workspaces

[Create or link to a collaboration workspace (Project)](/dynamicsax-2012/appuser-itpro/create-or-link-to-a-collaboration-workspace-project)

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated due to low usage. Customers using Project Operations for resource/non-stocked scenarios can leverage [Collaboration with Office Groups](../project-management/collaboration-groups.md). |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By December 1, 2022, we plan to no longer support Collaboration workspaces. |
