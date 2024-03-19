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

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

## Shortlist resources to narrow down suggestions

The suggested resources are shown on two tabs: **Suggested** and **Shortlisted**. By default, the **Shortlisted** tab is empty, and all suggestions appear on the **Suggested** tab. To shortlist resources that meet the staffing criteria, follow one of these steps on the **Suggested** tab.

- Select **View details** for a resource. In the details view, use the **Shortlist** button to add a resource to the **Shortlisted** tab. You can go to other resources by using the **Next** and **Previous** buttons.
- Select one or more resource rows, and then select **Shortlist**. The selected resources appear on the **Shortlisted** tab. You can add more resources in a similar way.

To remove a resource from the **Shortlisted** tab and return it to the **Suggested** tab, use the **Remove** button.


## Compare multiple suggested resources together

Individually navigating through each suggested resource using **View Details** could be time consuming and does not scale well. To make it easier to evaluate scores and metrics for multiple resources simultaneously, the ability to **Compare** resources has been provided. This can be used by:

1. Select more than one resources from the **Suggested** tab. This enables the **Compare** button on the top-right. Click this button.
2. This leads to a pop-up window that contains a grid of only the selected resources, sorted in decreasing order of their overall recommendation score.
3. This grid also contains columns for _Worker Type_, _Vendor/Resourcing Unit Name_, _Experience Fit (%),_, _Cost Impact_, _Availability_ and _Skill-Match_ for each resource. Filtering and sorting is available only for _Recommendation Score_, _Worker Type_, _Resourcing Unit_ and _Vendor Name_.
4. This grid can be used to compare resources together based on their scores and metrics. Resources can then be directly short-listed using the **Shortlist** button, this will make them available under the _Shortlisted_ tab of the main side-pane.

## Continue to book from shortlisted resources

After you narrow down the list of suggested resources, the last step to finish staffing a team member from the list of recommendations is to *book* a resource.

- To book a resource from the **Shortlisted** tab, select one or more resources and click **Continue booking**.
- Alternatively, select one or more resources from the **Compare** grid and then click **Continue booking**.
- A new resource requirement is created, or an existing requirement is updated. You're redirected to the **schedule board**, where you can review information about the resources' availability and use it to make the final booking decision.

For more information about how to use the schedule board to book a resource, see [Book from the schedule board](/dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board).

