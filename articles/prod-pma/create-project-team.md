---
title: Create a project team
description: This article provides information about how to create and manage project teams.
author: tulsij
ms.author: dishantpopli
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
---

# Create a project team

[!include [banner](../includes/banner.md)]

To use the roles that you previously set up in a project, the project manager must associate the roles with the project. You can assign multiple roles for a project. To prevent confusion, the system automatically labels these roles during reservation. For example, if the project manager requires three software engineers, the system automatically generates three Software engineer roles with **software engineer 1**, **software engineer 2**, and **software engineer 3** as their labels. If you previously set role characteristics for the role, the system applies them as a filter during searches for a resource. You can add additional characteristics as required to further refine the search.

You can also customize view settings to give a better view of resource availability. You can choose to show hourly, daily, weekly, monthly, quarterly, and annual availability. You can also choose to show available and remaining capacity on resources. This option is useful for time management when you're estimating available time for activities or resource availability.

The project manager selects a role on the page and then, if there's an available resource that fits the requirement, selects to reserve a resource to fill the role. Note that the resources don't need to be reserved at this point in the planning stage. When you create a WBS, you can replace roles with staffed resources for the project. If you replace roles with staffed resources in the WBS, the resource setup automatically updates the project team listing and scheduling.

:::image type="content" source="./media/projectresourcing03.jpg" alt-text="Screenshot of project team listing that includes both roles and actual resources." lightbox="./media/projectresourcing03.jpg":::

The project manager has various options for booking a resource for a project, such as **Remaining capacity**, **Full capacity**, **Capacity percentage**, and **Specify hours**. You can cancel these booking options at any time if resource assignments change. The system supports two types of booking:

- **Hard Book** – The project manager approves and confirms the resource reservation to work on the engagement for the specified duration.
- **Soft book** – The project manager tentatively sets the resource reservation to work on the engagement for the specified duration.

The following procedure explains how to create a project team.

## Create a project team

1. On **All projects**, select a project, and then select **Edit**.
1. On the **Project team and scheduling** tab, in the **Schedule end date** field, enter the schedule start date plus one month. For example, if the schedule start date is June 24, 2017 (24/06/2017), enter **24/07/2017**.
1. Select **Add**.
1. In the **Add roles to the project** pane, in the **Role** field, select **Senior Project Manager**.
1. Select **Required competencies**.
1. On the **Choose characteristics** page, the characteristics that you previously set for the Senior project manager role are selected by default. Select **OK**.
1. On the **Add roles to project** page, in the **Number of resources** field, enter **1**.
1. In the **Resource** field, the lookup shows all resources that have the required competencies. Select **Daniel Goldschmidt**, and then select **Create**.
1. On the **Project** page, select **Add**.
1. In the **Add roles to the project** pane, in the **Role** field, select **Team member**. In the **Number of resources** field, enter **5**.
1. Select **Create**.
1. On the **Projects** page, select **Fulfill resource**.

## Monitor project teams

1. On **All projects**, select the **Project ID** link for the **XYZ Upgrade Phase 2** project.
1. On the **Project team and scheduling** FastTab, verify that the project resources that are listed are correct.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
