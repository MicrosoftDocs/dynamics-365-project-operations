---
title: Removed or deprecated features in Dynamics 365 Project Operations
description: This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Project Operations.
author: sigitac
ms.date: 03/16/2022
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# Removed or deprecated features in Dynamics 365 Project Operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, and Project Operations for stocked/production-based scenarios_

This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Project Operations.

- A *removed* feature is no longer available in the product.
- A *deprecated* feature is not in active development and may be removed in a future update.

This list is intended to help you consider these removals and deprecations for your own planning.

> [!NOTE]
> Detailed information about objects in Finance and Operations apps can be found in the [**Technical reference reports**](/dynamics/s-e/global/axtechrefrep_61). You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.

## Features removed or deprecated in the Project Operations March 2022 release

### Project management and accounting parameter "Always create adjustment transaction"

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | When deprecated, this setting will be hidden. The system will always create adjustment transactions, as this setting would be set to **Yes**. Adjustment transactions are required for audit purposes.|
| **Replaced by another features?** | No |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will hide the setting and change the system behavior to always create adjustment transactions. |

### Project management and accounting parameter, "Use adjustment date as new project date"

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | This setting was originally used to allow adjustments when a fiscal period was closed. This setting is no longer required, as the accounting date of the transaction can be changed to the first date of the open period, if configured. The Project date must not be changed because it represents when transaction occurred. |
| **Replaced by another features?** | No |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will hide the setting and change the system behavior to never change the project date on adjustment. |

### Resource request workflow in Project Operations for stocked/production- based scenarios

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Depreciated due to low usage and transaction volume limitations. |
| **Replaced by another features?** | No |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will disable the option to request resources for the project using the workflow. |


### Project invoice proposal form without header and lines view

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated due to improved the form that was introduced with the feature key, **Use Project invoice proposal and invoice journal forms with the Header and Lines view**. |
| **Replaced by another features?** | Yes |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios; Project Operations for resource/ non-stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will turn off the legacy form and turn the feature key, **Use Project invoice proposal and invoice journal forms with the Header and Lines view** on by default. |

## Features removed or deprecated in the Project Operations December 2021 release

### Collaboration workspaces

[Create or link to a collaboration workspace (Project)](/dynamicsax-2012/appuser-itpro/create-or-link-to-a-collaboration-workspace-project)

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated due to low usage. Customers using Project Operations for resource/non-stocked scenarios can leverage [Collaboration with Office Groups](../project-management/collaboration-groups.md). |
| **Replaced by another features?** | No |
| **Product areas affected** | Application  |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By December 1, 2022, we plan to no longer support Collaboration workspaces. |
