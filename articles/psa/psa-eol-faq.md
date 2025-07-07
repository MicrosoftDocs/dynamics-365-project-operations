---
title: Project Service Automation end of life FAQ
description: This article provides answers to frequently asked questions about the end of life for Microsoft Dynamics 365 Project Service Automation.
author: abriccetti
ms.date: 07/07/2025
ms.topic: faq
ms.custom: 
  - bap-template
  - evergreen
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Service Automation end of life FAQ

[!INCLUDE[banner](../includes/banner.md)]

This article provides answers to frequently asked questions about the end of life for Microsoft Dynamics 365 Project Service Automation.

## General, licensing, and cost

### When is Project Service Automation 3.x reaching its end of life? Is there an exception process?

The end-of-life date for Project Service Automation is March 31, 2025. *End of life* means the end of product support. After the end-of-support date, support tickets are resolved through a request to upgrade to Dynamics 365 Project Operations. The Product engineering team won't release regular maintenance updates for functional improvements, performance issues, security and compliance issues, or any other issues. Although customers can continue to access and use Project Service Automation after this date, you’re highly discouraged from using it.

After the end-of-support date, license grandfathering from a Project Service Automation license to a Project Operations license isn't supported.

### What's the licensing structure when I upgrade from Project Service Automation to Project Operations? Do I have to purchase a new stock-keeping unit (SKU)?

All Project Service Automation customers should already have their license upgraded to a Project Operations license. They should have a separate entitlement via a promotion code for Project Service Automation. No new purchase is required for these customers.

### What will my new cost structure look like? Can I be grandfathered into my existing cost structure? How are my existing enterprise volume discounts affected?

Because all customers have already been upgraded to Project Operations licenses, the cost structure shouldn't change.

### Where can I view the capability map that compares Project Operations to Project Service Automation 3.x?

For information about feature changes from Project Service Automation to Project Operations, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Where can I view the roadmap for Project Operations?

For information about features that are coming in the next wave, see [Plan and prepare for Dynamics 365 Project Operations in 2024 release wave 1](https://aka.ms/POroadmap).

## Setup experience

### How do I upgrade from Project Service Automation to Project Operations? Where do I start? Can I self-start the upgrade?

You can do an upgrade by triggering the installation of Project Operations in a Project Service Automation environment from the Admin portal. Customers should always do a few trial upgrade runs in test organizations that are copies of their production organization. They should then validate the integrity of the resulting data in the upgraded Project Operations environment.

For detailed steps that show how to validate customizations, see [Testing and refactoring customizations](upgrade-project-operations-non-stocked.md#testing-and-refactoring-customizations).

This process might take a significant amount of time for customers that have large data volumes and/or heavy customizations.

### How long does the upgrade take?

The average upgrade takes about three hours. However, we've seen customer upgrades that take more than six hours. The amount of time that an upgrade takes depends on your data and customization volume. Every customer should test the upgrade in a test organization that's a copy of their production organization. In this way, runtime or upgrade issues won't be a surprise when they occur in the production organization.

### If a standard upgrade fails, it can be reattempted. Can upgrades from Project Service Automation 3.x to Project Operations also be reattempted if they fail?

Failed upgrades can be reattempted only for transient errors, such as errors that are related to the environment infrastructure. For permanent errors, such as data corruption, retries don't help. For any upgrade failure, if the error is unclear from the Admin portal, look for detailed error information at **Settings** \> **Upgrade Logs** in Project Service Automation. If the error is missing or unclear, contact the Microsoft Support team.

### Are my role and permission setups carried forward, or do I have to do another security review of the system?

In general, all roles and permissions should be carried forward during the upgrade. Some new roles are created in Project Operations and might have to be assigned to specific users after the upgrade.

### How is my data upgraded?

A data model conversion changes the names of some entities. For more information, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Is there any data loss during the upgrade?

No data is lost during the data model conversion.

### Can I revert to Project Service Automation 3.x after I upgrade to Project Operations?

No. After the upgrade is completed, you can't roll back to Project Service Automation.

### Unlike standard update rollup (UR) upgrades, the upgrade from Project Service Automation to Project Operations is large. What kind of support does Microsoft offer for this process?

We're committed to ensuring the success of your upgrade to Project Operations. We provide robust documentation, and Project Service Automation includes more error logs that explain upgrade failures. If you encounter issues with the upgrade process, contact the Microsoft Support team for assistance.

### Can I upgrade directly from Project Service Automation 3.x to Project Operations for Resource and non-stocked based scenarios, or is the upgrade available only for Project Operations Deal to proforma invoicing scenarios (Core deployment)?

No. Only upgrades to Project Operations Deal to proforma invoicing scenarios (Core deployment) are supported.

### After I upgrade to Project Operations Deal to proforma invoicing scenarios (Core deployment), how do I upgrade to Project Operations for Resource and non-stocked based scenarios?

Upgrade from Project Operations Deal to proforma invoicing scenarios (Core deployment) to Project Operations for Resource and non-stocked based scenarios isn't currently supported.

## Functional experience

### Project Operations includes a new task scheduling engine. What happens to my existing projects?

Your current projects are brought into Project Operations in either [external scheduling](../project-management/external-scheduling.md) mode or [add-in scheduling](plan-work-in-project-operations-add-in.md) mode, depending on your usage of scheduling in Project Service Automation. You can then convert the projects so that they're scheduled by Project for the web (the default scheduling engine in Project Operations). Project for the web is the only task scheduling engine in Project Operations. If you require that these projects are externally scheduled, you must have your own custom scheduling logic or build a custom integration to another scheduling system.

### I have projects that exceed the limits of Project for the web. Can I continue to work on them?

Yes. You can manage the projects by using either external scheduling or the Project Desktop client add-in. For more information, see [Plan your work in Microsoft Project with the Project Operations add-in](plan-work-in-project-operations-add-in.md), or download [Dynamics 365 Project Operations Add-in for Microsoft Project](https://www.microsoft.com/download/details.aspx?id=105733). If you want to convert the projects to Project for the web later, they must conform to the limits of Project for the Web.

### Are the limits of Project for the web published?

Yes. For more information, see [Project and task limitations](../project-management/project-and-task-limitations.md).

> [!NOTE]
> We're continually improving our product. We have a roadmap to increase these limits so that we can better serve our customers in the future.

### Can I create new projects that are externally scheduled?

Yes, you can create new projects that use external scheduling. However, the desktop client add-in is available only for environments that were upgraded from Project Service Automation.

### For downstream workflows such as estimating pricing or reporting time, is there any loss in functionality if I choose to schedule projects externally?

External scheduling has some limitations. For more information, see [Functional limitations](../project-management/external-scheduling.md#functional-limitations). Otherwise, all downstream workflows work if the external scheduling engine updates follow the same data model as Project Operations.

### If I have existing projects that are scheduled by Project for the web, can I change them so that they're externally scheduled instead?

This change in scheduling mode isn't supported for projects that were previously created in Project Operations. However, you can choose to create new projects as externally scheduled.

### What about the Microsoft Project add-in that the Project Operations team released? Can I use it for my projects?

The Project desktop client add-in is available in environments that were upgraded from Project Service Automation, and that have projects that don't meet the restrictions of Project for the web. The availability of this add-in continues only for a limited time as we work to increase the limits of Project for the web.

> [!NOTE]
> The Project Operations license doesn't include the Project desktop client that was included in Project Service Automation. To use the add-in, you must purchase the license separately.

### Can I use the new scheduling engine, Project for the web, for my existing projects?

Yes, you can use Project for the web for existing projects that are within the limits of Project for the web. When you view a Project Service Automation project entity in Project Operations, you can use the **Convert** button on the Action Pane to change the scheduling engine to Project for the web.

### Can I preview the scheduling changes when the scheduling engine is changed, and can I undo the scheduling engine change?

The conversion process can't be undone. We recommend that you copy a project record to test the conversion.

## Technical and functional experience

### When I upgrade, will all my customizations continue to work?

During the upgrade from Project Service Automation to Project Operations, changes are made to the data model and user interface (UI). These changes might break some of your customizations.

### How do I determine which customizations will be broken before I upgrade?

To get a sense of the customizations that might be affected by the upgrade, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Is there a best practice document for creating customizations in Project Operations?

Project Operations is a Dataverse application, and similar best practices apply across all Dataverse applications. To review the best practices and technical considerations for scheduling entities in Project Operations, see [Use Project schedule APIs to perform operations with Scheduling entities](../project-management/schedule-api-preview.md).

### Is the data model between Project Service Automation and Project Operations the same? Are the changes published?

For information about changes to Dataverse entities and fields from Project Service Automation to Project Operations, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
