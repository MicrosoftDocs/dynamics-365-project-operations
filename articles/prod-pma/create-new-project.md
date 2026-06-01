---
title: Create a new project
description: Learn how to create a new project step-by-step, assign resources, and define roles effectively. Start managing your projects with ease today!
author: abriccetti
ms.author: abriccetti
ms.date: 02/06/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: johnmichalak
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0

---

# Create a new project

[!include [banner](../includes/banner.md)]

Complete the following steps to create a new project.

1. On the **Project management** page, select **New project**, and enter the following values:

    - **Project type:** Time and material
    - **Project name:** XYZ Upgrade Phase 2
    - **Project group:** TM\_WIP
    - **Project contract ID:** 00000002

1. Select **Create project**.

## Assign a resource to a project

1. On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.
1. On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.
1. On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.
1. In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.

You can also assign categories for a resource as you require. The category type is either **Cost** or **Revenue**. The category type is determined by your organization. If you don't assign categories for a resource, Finance looks up the default category on hour prices for cost and revenue.

## Set up project resource and role characteristics

A project manager uses the project resourcing functionality to create the roles that the project requires. Use roles if you don't yet know the confirmed resources when you're reserving resources. Temporarily reserve roles as planned resources so you can continue the project planning stages.

:::image type="content" source="./media/projectresourcing05.jpg" alt-text="Screenshot of an example role configuration in the project resourcing interface." lightbox="./media/projectresourcing05.jpg":::

**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter. The junior project manager is still completing the scope of the project. The Resource Manager is currently identifying specific resources that the Resource Manager reserves to work on the new project. Because of the critical nature of the project, the project sponsor requests Senior project manager as one of the roles. The Resource Manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.

The following steps show how the Resource Manager sets up the Senior project manager role and associates resource characteristics with it. Later, use the role to search for available resources that match the required resource competencies.

1. On the **Setup roles** page, select **New**, and enter the following values:

    - **Role ID:** Senior Project Manager
    - **Description:** Senior Project Manager

1. Select **Create**.
1. Select the **Senior Project Manager** role, and then select **Configure characteristics**.
1. In the **Characteristics type** field, select **Skill**.
1. In the **Available characteristics** field, enter the skill to search for.
1. In the **Characteristic type** field, select **Certificate**.
1. In the **Available characteristics** field, enter the certificate type to search for.

## Assign a project resource to a project

1. On **All projects**, select the **XYZ Upgrade Phase 2** project.
1. On **Project team and scheduling**, select **Add**.
1. In the **Role** field, select **Team member**.
1. Select **Book from calendar**.
1. On **Resource availability**, select **View settings**.
1. On **Adjust view settings**, enter the following values:

    - **Format for date range view:** Day
    - **Display availability descriptions:** Yes
    - **Display remaining capacity:** Yes

1. In the list of resources, select a resource.
1. Select **Hard book** and **Full capacity**.

## Assign a default role to a resource

To help project or resource managers understand which resources they can reserve for a project, associate a default role with an existing resource or a newly acquired resource. For example, when Daniel is hired, he has the experience and skills to fill the Business analyst role. The Resource Manager assigns this role as Daniel's default role. The Resource Manager adds Daniel to a pool of business analysts who are available to work on projects.

During resource reservation, project managers can filter the role resources that are available to work on projects. They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment. They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.

**Scenario:** An approved project starts, and the Senior project manager role is reserved as a planned resource during the project planning stage. The Resource Manager acquires a resource to fulfill the Senior project manager role.

1. On the **Resources list** page, select **Daniel Goldschmidt**.
1. On the **Resource role** page, select **New**, and enter the following values:

    - **Effective:** Enter the current date.
    - **Expiration:** Enter **Never**.
    - **Role:** Enter **Senior Project Manager**.

1. Select **Save**, and then close the page.
1. On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
