---
# required metadata

title: Get recommendations for a project team member (preview)
description: This article explains how to get optimal recommendations for team members before you book them on a project.
author: mohitmenon
ms.date: 02/14/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Get recommendations for a project team member (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

[!INCLUDE [preview-banner](../includes/preview-banner.md)]

## Get suggested resources

To get suggested resources, follow these steps.

1. Ensure that you complete the [prerequisites for using resource recommendations](./getting-started-with-resource-recommendations.md).
1. Go to **Projects**, and select a project that must be staffed with one or more resources.
1. On the **Team** tab, review the list of team members on the selected project.
1. Select the row for one team member that isn't already booked with a named resource.

    > [!IMPORTANT]
    > Don't select more than one row at a time.
1. Select the **Suggest resources** button that appears next to **Subcontracting options**. A loading message appears. After a few seconds, the side pane shows a list of suggested resources.

## View more details to evaluate suggested resources

Each suggested resource is assigned a **recommendation score** (out of 10) to indicate the resource's appropriateness for the specific team member requirement. Currently, this score is based only on the relevance of the resource's past experience on projects to a team member requirement. In upcoming releases, it is augmented so that it includes more factors, such as cost, availability, utilization, and skill match. The suggested resources are listed in decreasing order of their recommendation scores.

> [!NOTE]
> By default, both contract workers and full-time employees are shown in the list of suggested resources. To show only full-time employees, disable the **Show contractors** option.
>
> By default, the initial list of suggested resources is limited to 20 resources. You can use the **View more suggestions** button to extend the list by five resources at a time.
To get more information about any suggested resource and interpret that resource's recommendation score, follow one of these steps.

- Select the information symbol next to the resource's name.
- Select the row for the resource in the grid, and then select the **View details** button.

Both steps open additional information that's related to the past experience of the resource. The following metrics are shown:

- **Experience match (%)** – This metric represents, as a percentage, the similarity between work that the resource did on previous project tasks and the team member requirements that are being staffed.
- **Relevant past experience** – This metric consists of three parameters: the number of similar project tasks, projects that were worked on, and the number of hours that were worked on those similar project tasks (adjusted for the **Experience match %** metric).
- **Task-wise score** – This metric provides the recommendation score for each task that's part of the team member requirement.

## Shortlist resources to narrow down suggestions

The suggested resources are shown on two tabs: **Suggested** and **Shortlisted**. By default, the **Shortlisted** tab is empty, and all suggestions appear on the **Suggested** tab. To shortlist resources that meet the staffing criteria, follow one of these steps on the **Suggested** tab.

- Select **View details** for a resource. In the details view, use the **Shortlist** button to add a resource to the **Shortlisted** tab. You can go to other resources by using the **Next** and **Previous** buttons.
- Select one or more resource rows, and then select **Shortlist**. The selected resources appear on the **Shortlisted** tab. You can add more resources in a similar way.

To remove a resource from the **Shortlisted** tab and return it to the **Suggested** tab, use the **Remove** button.

## Continue to book shortlisted resources

After you narrow down the list of suggested resources, the last step to finish staffing a team member from the list of recommendations is to *book* a resource.

To book a resource, on the **Shortlisted** tab, select **Continue booking**. A new resource requirement is created, or an existing requirement is updated. You're redirected to the **schedule board**, where you can review information about the resources' availability and use it to make the final booking decision.

For more information about how to use the schedule board to book a resource, see [Book from the schedule board](/dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board).
