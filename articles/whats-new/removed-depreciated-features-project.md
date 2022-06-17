---
title: Removed or deprecated features in Dynamics 365 Project Operations
description: This article describes features that have been removed, or that are planned for removal from Dynamics 365 Project Operations.
author: sigitac
ms.date: 03/16/2022
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

## Features removed or deprecated in the Project Operations March 2022 release

### Project management and accounting "Always create adjustment transaction" parameter

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Adjustment transactions are required for audit purposes. After deprecation, this parameter will be hidden. The system will always create adjustment transactions, just as it currently does when the parameter is set to **Yes**. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will hide the parameter and change the system behavior so that adjustment transactions are always created. |

### Project management and accounting "Use adjustment date as new project date" parameter

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | This parameter was originally used to allow for adjustments when a fiscal period was closed. However, it's no longer required, because the accounting date of the transaction can be changed to the first date of the open period, if it's configured. The project date must not be changed, because it represents the date when transaction occurred. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will hide the parameter and change the system behavior so that the project date is never changed on adjustments. |

### Resource request workflow in Project Operations for stocked/production-based scenarios

| &nbsp; | &nbsp; |
|--------|--------|
| **Reason for deprecation/removal** | Deprecated because of low usage and transaction volume limitations. |
| **Replaced by another feature?** | No |
| **Product areas affected** | Application |
| **Deployment option** | Project Operations for production/stocked scenarios |
| **Status** | Deprecated: By March 1, 2023, we will disable the option to request resources for the project by using the workflow. |

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
