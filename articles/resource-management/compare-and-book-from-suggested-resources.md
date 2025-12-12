---
# required metadata

title: Compare and book from suggested resources (preview)
description: This article explains how to narrow down the list of suggested resources and book one of them as a team member.
author: mohitmenon
ms.date: 03/19/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Compare and book from suggested resources (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

## Narrow down suggestions by shortlisting resources

The suggested resources are shown on two tabs: **Suggested** and **Shortlisted**. By default, the **Shortlisted** tab is empty, and all suggestions appear on the **Suggested** tab. To shortlist resources that meet the staffing criteria, follow one of these steps on the **Suggested** tab.

- Select **View details** for a resource. In the details view, use the **Shortlist** button to add the resource to the **Shortlisted** tab. You can go to other resources by selecting the **Next** and **Previous** buttons.
- Select one or more resource rows, and then select **Shortlist**. The selected resources appear on the **Shortlisted** tab. You can add more resources in a similar way.

To remove a resource from the **Shortlisted** tab and return it to the **Suggested** tab, use the **Remove** button.

## Compare multiple suggested resources together

It can be time-consuming to use the **View details** button to go through all the suggested resources. In addition, this approach doesn't scale well. To make it easier to evaluate scores and metrics for multiple resources simultaneously, the capability to **compare** resources is provided.

The **Compare** button becomes available after you select more than one resource on the **Suggested** tab. When you select **Compare**, a pop-up window shows a grid where the selected resources are sorted in decreasing order of overall recommendation score. Filtering and sorting capabilities are available for the **Recommendation Score**, **Worker Type**, **Resourcing Unit**, and **Vendor Name** columns of the **Compare** grid. However, the grid also contains **Worker Type**, **Vendor/Resourcing Unit Name**, **Experience Fit (%)**, **Cost Impact**, **Availability**, and **Skill-Match** columns that can't be used for filtering or sorting.

You can use the **Compare** grid to compare resources based on their scores and metrics. You can shortlist resources directly from the pop-up window by using the **Shortlist** button. Those resources then become available on the **Shortlisted** tab in the side pane of the main window.

## Book from the shortlisted resources list

After you narrow down the list of suggested resources, you can finish staffing a team member from the list of recommendations by **booking** a resource.

To book resources from the **Shortlisted** tab, select one or more resources, and then select **Continue booking**. Alternatively, select one or more resources in the **Compare** grid, and then select **Continue booking**.

A new resource requirement is created. Alternatively, an existing requirement is updated for the team member and now includes the condition to book only from the selected resources. You're redirected to the **schedule board**, where you can review information about the resources' availability and use it to make the final booking decision.

> [!NOTE]
> If the schedule board doesn't show any or all of the resources that you selected, the missing resources probably aren't available for the entire duration of the team member requirement, or the resourcing units differ. Select **Filters** to go to the **Schedule Assistant Filter** section. Clear the **Organizational Units** field or select the **Ignore Duration** checkbox under **Advanced**. Then select **Search** again.

For more information about how to use the schedule board to book a resource, see [Book from the schedule board](/dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board).
