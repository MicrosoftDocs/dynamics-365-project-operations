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

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

## Narrow down suggestions by shortlisting resources

The suggested resources are shown on two tabs: **Suggested** and **Shortlisted**. By default, the **Shortlisted** tab is empty, and all suggestions appear on the **Suggested** tab. To shortlist resources that meet the staffing criteria, follow one of these steps on the **Suggested** tab.

- Select **View details** for a resource. In the details view, use the **Shortlist** button to add a resource to the **Shortlisted** tab. You can go to other resources by selecting the **Next** and **Previous** buttons.
- Select one or more resource rows, and then select **Shortlist**. The selected resource appears on the **Shortlisted** tab. You can add more resources in a similar way.

To remove a resource from the **Shortlisted** tab and return it to the **Suggested** tab, use the **Remove** button.


## Compare multiple suggested resources together

Navigating through each suggested resource using **View Details** can be time consuming and doesn't scale well. To make it easier to evaluate scores and metrics for multiple resources simultaneously, the ability to **Compare** resources is provided. 

To enable the **Compare** button, select more than one resource from the **Suggested** tab. Select the **Compare** button. A pop-up window appears that contains a grid of only the selected resources, sorted in decreasing order of their overall recommendation score. This grid also contains columns for **Worker Type**, **Vendor/Resourcing Unit Name**, **Experience Fit (%)**, **Cost Impact**, **Availability**, and **Skill-Match**. Filtering and sorting is available only for **Recommendation Score**, **Worker Type**, **Resourcing Unit**, and **Vendor Name**. This grid can be used to compare resources together based on their scores and metrics. Resources can then be directly short-listed using the **Shortlist** button, making them available under the **Shortlisted** tab of the main side-pane.

## Book from the shortlisted resources list

After you narrow down the list of suggested resources, the next step to finish staffing a team member from the list of recommendations is to *book* a resource.

To book a resource from the **Shortlisted** tab, select one or more resources and select **Continue booking**. Alternatively, select one or more resources from the **Compare** grid and then select **Continue booking**. 

A new resource requirement is created, or an existing requirement is updated for this team member to include the condition to book from the selected resources only. You're redirected to the **schedule board**, where you can review information about the resources' availability and use it to make the final booking decision.

> [!NOTE]
> If none or fewer than the selected resources are visible on the schedule board, this is most likely due to them not being available for the entire duration of the team member requirement or a difference in resourcing units.
> Navigate to the **Schedule Assistant Filter** section by selecting **Filters**, and clear the **Organizational Units** field or by check the **Ignore Duration** box under **Advanced**. Select **Search** again.

For more information about how to use the schedule board to book a resource, see [Book from the schedule board](/dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board).


