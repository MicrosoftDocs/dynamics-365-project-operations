---
title: Project Service Automation end of life FAQ
description: This article provides answers to frequently asked questions about the end of life for Project Service Automation.
author: abriccetti
ms.date: 03/1/2024
ms.topic: faq
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Project Service Automation end of life frequently asked questions

[!INCLUDE[banner](../includes/banner.md)]

This article provides answers to frequently asked questions about the end of life for Project Service Automation.

## General, licensing, and cost

### When is PSA 3.x reaching its end-of-life? Is there an exception process for this?

End-of-life means end of product support. After the end of support date, support tickets are resolved with a request to upgrade to Microsoft Dynamics 365 Project Operations. The Product engineering team won't release regular maintenance updates for functional improvements, performance issues, security and compliance issues, or any other issues. Customers are able to access and continue using Dynamics 365 Project Service Automation (PSA) beyond this date; although, we highly discourage this use. After this date, license grandfathering isn't supported from a PSA license to a Project Operations license.

### What is the licensing structure when upgrading from PSA to Project Operations? Do I need to purchase a new SKU?

All PSA customers should have already had their license upgraded to Project Operations, with a separate entitlement via a promotion code for PSA. No new purchase is required for these customers.

### What will my new cost structure look like? Can I be grandfathered into my existing cost structure? How are my existing enterprise volume discounts impacted?

As all customers have been upgraded to Project Operations licenses already, the cost structure shouldn't change.

### Where can I see the capability map of Project Operations compared to PSA 3.x?

For information about feature changes from PSA to Project Operations, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Where can I see the roadmap for Project Operations?

Features coming in the next wave can be found at [Plan and prepare for Dynamics 365 Project Operations in 2024 release wave 1](https://aka.ms/POroadmap).

## Setup experience

### How do I upgrade from PSA to Project Operations? Where do I start? Can I self-start the upgrade?

An upgrade can be done by triggering the installation of Project Operations on a PSA environment from the Admin portal. Customers should always try a few trial upgrade runs in test orgs that are copies of their production org, and then validate the integrity of the resulting data in the upgraded Project Operations environment.

For detailed steps on how to validate customizations, see [Testing and refactoring customizations](upgrade-project-operations-non-stocked.md#testing-and-refactoring-customizations).

This process may take a significant amount of time for customers with large data volumes and/or heavy customizations.

### How long does the upgrade last?

The average upgrade takes about three hours to complete, but we have seen customer upgrades take more than six hours. The length of time an upgrade takes depends on your data and customization volume. Every customer should test the upgrade on a test org that is a copy of your production org so run time or upgrade issues aren't a surprise in your production org.

### In a standard upgrade, failed upgrades can be retried. Is this also true for upgrading PSA 3.x to Project Operations?

It's only true for transient errors, like errors related to environment infrastructure, etc. For permanent errors, like data corruption, retrying doesn't help. For any upgrade failure, if the error is unclear from the Admin Portal, look for detailed error information in PSA **Settings** \> **Upgrade Logs**. If the error is missing or unclear, reach out to the Microsoft Support team.

### Do my role and permission setups carry forward, or do I have to do another security review of the system?

In general, all roles and permissions should carry forward during upgrade. There are some new roles created in Project Operations that may need to be assigned to certain users after the upgrade.

### How is my data upgraded?

A data model conversion changes the names of some entities. For more information, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Is there any data loss during the upgrade?

There isn't data lost in the data model conversion.

### Can I revert to PSA 3.x after upgrading to Project Operations?

Once the upgrade is complete, there you can't roll back to PSA.

### Unlike standard UR upgrades, PSA to Project Operations is a large upgrade. What kind of support does Microsoft offer for this process?

We're committed to ensuring the success of your upgrade to Project Operations. We have robust documentation, and more error logs within PSA that explain upgrade failures. If you encounter issues with the upgrade process, reach out to Microsoft support to get further assistance.

### Can I upgrade directly from PSA 3.x to Project Operations for Resource and non-stocked based scenarios, or is the upgrade only available to Project Operations Deal to proforma invoicing scenarios (Lite deployment)?

Only upgrades to  Project Operations Deal to proforma invoicing scenarios (Lite deployment) are supported.

### After I upgrade to  Project Operations Deal to proforma invoicing scenarios (Lite deployment), how do I upgrade to Project Operations for Resource and non-stocked based scenarios?

Upgrade from  Project Operations Deal to proforma invoicing scenarios (Lite deployment) to Project Operations for Resource and non-stocked based scenarios isn't supported at this time.

## Functional experience

### Project Operations ships with a new task scheduling engine. What happens to my existing projects?

Your current projects are brought into Project Operations in either the [external scheduling](../project-management/external-scheduling.md), or the [add-in scheduling](plan-work-in-project-operations-add-in.md)) mode depending on your usage of scheduling in PSA. From there, you can convert these projects to be scheduled by Project for the web (the default scheduling engine in Project Operations). Project for the web is the only task scheduling engine in Project Operations. If you need these projects to be externally scheduled, you need to have your own custom scheduling logic or build a custom integration to another scheduling system.

### I have projects that exceeds Project for the web limits. Can I continue to work on them?

Yes. These projects can be managed using external scheduling, or using the Project Desktop client add-in. For more information, see [Plan your work in Microsoft Project with the Project Operations add-in](plan-work-in-project-operations-add-in.md), or download the [Dynamics 365 Project Operations Add-in for Microsoft Project](https://www.microsoft.com/en-us/download/details.aspx?id=105733). Later, if you want to convert them to Project for the web, they need to conform to the limits for Project for the Web.

### Are the Project for the Web’s limits published?

Yes, for more information, see [Project and task limitations](../project-management/project-and-task-limitations.md). 

> [!NOTE]
> We're continually improving our product and have a roadmap to increase these limits to better serve our customers in the future.

### Can I create new projects that are externally scheduled?

Yes, you can create new projects that use external scheduling; however, the desktop client add-in is only available for environments that have been upgraded from PSA.

### For downstream workflows like estimating pricing or reporting time, is there any loss in functionality when choosing to schedule projects externally?

For information about limitations of external scheduling, see [Functional limitations](../project-management/external-scheduling.md#functional-limitations). Other than the limitations listed, all other downstream workflows work if the external scheduling engine updates follow the same data model as Project Operations.

### Can I switch existing projects from Project for the web scheduled to externally scheduled?

This change in scheduling mode isn't supported for projects already created in Project Operations. You can however choose to create new projects as externally scheduled.

### What about the Microsoft Project Add-in shipped by the Project Operations team? Can I use that for my projects?

The Project desktop client add-in is available in environments that have upgraded from PSA and have projects that don't meet the restrictions of Project for the web. This will only continue for a limited time as we work to increase limits for Project for the web. 

> [!NOTE]
> The Project Operations license doesn't include the Project desktop client (that was included in PSA). This license needs to be purchased separately to use the add-in.

### Can I use the new scheduling engine, Project for the web, for my existing projects?

Yes, for projects that are within the limitations of Project for the web. When you view a PSA project entity in Project Operations, a convert button on the ribbon allows the scheduling engine to change to Project for the web.

### Can I preview the scheduling changes when changing the scheduling engine, and can I undo the scheduling engine change?

The conversion process can't be undone. We recommend copying a project record to test the conversion.

## Technical and functional experience

### When upgrading, do all my customizations continue to work?

There are data model and UI changes when upgrading from PSA and to Project Operations. These changes may potentially break some of your customizations.

### How do I determine what customizations will be broken before I upgrade?

To get a sense of which customizations may be impacted by the upgrade, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).

### Is there a best practice document for creating customizations in Project Operations?

Project Operations is a Dataverse application, and best practices apply similarly across Dataverse applications. To review the best practices and technical considerations for scheduling entities in Project Operations, see [Use Project schedule APIs to perform operations with Scheduling entities](../project-management/schedule-api-preview.md).

### Is the data model between PSA and Project Operations same? Are the changes published?

For information regarding changes to Dataverse entities and fields from PSA to Project Operations, see [Feature changes from Project Service Automation to Project Operations](psa-project-operations-changes.md).
