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


## Understanding how resources are suggested

To get more information about any suggested resource and interpret that resource's recommendation score, follow any one of these steps.
  - Select the information symbol next to the resource's name **OR**
  - Double click the whitespace on any of the suggested resource's grid rows **OR**
  - Select the row for the resource in the grid, and then select the **View details** button

Each suggested resource is assigned a **recommendation score** (out of 10) to indicate the resource's appropriateness for the specific team member requirement. This score is based on a combination of **Experience Fit**, **Availability**, **Cost Impact** incurred and **Skill-match**. Each of these factors and sections is explained below:
- **Experience fit (%)** – This metric represents, as a percentage, the similarity between work that the resource did on previous project tasks and the team member requirements that are being staffed. This also considers the number of hours worked on past similar project tasks.
- **Skill-match (%)** - This is only relevant to a team member requirement that also has one or more required skills. This metric represents the % of required skills that a resource has or exceeds the minimum proficiency on.
- **Cost Impact** - This represents an estimated total cost (not the exact value) that could be incurred by staffing a resource on this team member requirement, in the project's currency. Cost impact for suggested resources from units that use a different currency will be displayed after converting to the project's currency.
- **Availability (%)** - This represents the percentage of the team member duration (in hours) that a suggested resources is available to book (as per schedule board).
- **Relevant past experience** – This section consists of three parameters: the number of similar project tasks, projects that were worked on, and the number of hours that were worked on those similar project tasks (adjusted for similarity % of the experience). This section is used to arrive at the **Experience Fit (%)** factor.
- **Task-wise score** – This metric provides an overall recommendation score, for each individual task that's part of the team member requirement. The task-wise recommendation scores are eventually used to arrive at the overall recommendation score.

> [!NOTE]
> By default, both contract workers and full-time employees are shown in the list of suggested resources. To show only full-time employees, disable the **Include contractors** option.
>
> By default, the initial list of suggested resources is limited to 20 resources. You can use the **View more suggestions** button to extend the list by five resources at a time.


## Provide inputs to configure suggested resources

Users are provided with the ability to configure 1) Which resourcing units to consider and 2) Which factors to consider, along with their relative importance while suggesting resources (settings).

- **Resourcing units to consider:** By default, only the resourcing unit mentioned on the team member requirement is considered to provide suggestions. This can be modified by selecting one or more resourcing units from the _Show resources from_ drop-down list.
  - Modifying the selected resourcing units and clicking anywhere outside the drop-down will initiate a refresh of the suggestions to then include resources across the units selected.
    
- **Factors to consider:** The settings icon on the top-right of the side-pane gives users the ability to modify default settings and include or exclude factors to arrive at the list of suggested resources. Each included factor can also be given a relative importance (High, Medium or Low) that will be used to score all suggested resources.
  - By default all factors are included and set to "Medium" importance unless a project is over budget or running behind schedule. When a project is over budget, **Cost Impact** is set to "High" and when a project is running behind schedule, both **Experience Fit** and **Availability** are set to "High".
  - To exclude a factor, disable the toggle next to the factor's name. Use the "importance" slider to set relative importance as Low, Medium or High for an included factor. Finally select **Apply** to update the list of suggested resources based on the configured settings.
> [!NOTE]
> Any modified settings will only persist for one team member requirement and will be defaulted back each time you close the side-pane or generate suggested resources for another team member.

Continue to the [next section](./compare-and-book-from-suggested-resources.md) to learn how to narrow down the list of suggestions by comparing resources, short-listing them and finally booking a team member.

