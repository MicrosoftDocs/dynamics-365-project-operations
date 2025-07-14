---
# required metadata

title: Get recommendations for a project team member (preview)
description: This article explains how to get optimal recommendations for team members before you book them on a project.
author: mohitmenon
ms.date: 03/19/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Get recommendations for a project team member (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

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

## How resources are suggested

To get more information about any suggested resource and interpret that resource's recommendation score, follow one of these steps.

- Select the information symbol next to the resource's name.
- Double-tap (or double-click) the whitespace in the row for the resource.
- Select the row for the resource, and then select **View details**.

Each suggested resource is assigned a **recommendation score**, which is a number out of 10. This score indicates the resource's appropriateness for the specific team member requirement. It's based on a combination of the following metrics (factors): **Experience Fit**, **Skill-match**, **Cost Impact**, and **Availability**. The following list explains the relevant factors and sections:

- **Experience Fit (%)** – This metric represents, as a percentage, the similarity between work that the resource did on previous project tasks and the team member requirements that are being staffed. It also considers the number of hours the resource previously worked on similar project tasks.
- **Skill-match (%)** – This metric is relevant only to team member requirements that also have one or more required skills. It represents the percentage of required skills that a resource meets or exceeds the minimum proficiency for.
- **Cost Impact** – This metric represents, in the project's currency, the estimated total cost (not the exact value) that might be incurred by staffing a resource on the team member requirement. For suggested resources from units that use a different currency, the cost impact is converted to the project's currency before it's shown.
- **Availability (%)** – This metric represents the percentage of the team member duration (in hours) that a suggested resource is available to book (per the schedule board).
- **Relevant past experience** – This section consists of three parameters: the number of similar project tasks, the projects that were worked on, and the number of hours that were worked on the similar project tasks (adjusted for the similarity percentage of the experience). This section is used to arrive at the **Experience Fit (%)** metric.
- **Task-wise score** – This metric provides an overall recommendation score for each individual task that's part of the team member requirement. The task-wise recommendation scores are eventually used to arrive at the overall recommendation score.

> [!NOTE]
> By default, the list of suggested resources shows both contract workers and full-time employees. To view only full-time employees, disable the **Include contractors** option.
>
> By default, the initial list of suggested resources is limited to 20 resources. You can use the **View more suggestions** button to extend the list by five resources at a time.

## Provide inputs to configure suggested resources

Users can configure which resourcing units and factors are considered, together with their relative importance when resources are suggested.

- **Resourcing units to consider:** By default, only the resourcing unit that's mentioned on the team member requirement is considered and used to provide suggestions. However, you can modify the resourcing units that are considered by selecting one or more units in the **Show resources from** dropdown list.

    After you modify the resourcing units, tap (or click) anywhere outside the dropdown list to update the suggestions so that they include resources across the selected units.

- **Factors to consider:** The settings symbol in the upper right of the side pane lets you modify default settings and include/exclude factors to arrive at the list of suggested resources. Each factor that's included can also be assigned a relative importance (**High**, **Medium**, or **Low**) that's used to score all suggested resources.

    - By default, all factors are included and are set to **Medium** importance, unless a project is over budget or running behind schedule. If a project is over budget, the **Cost Impact** factor is set to **High** importance. If a project is running behind schedule, both the **Experience Fit** factor and the **Availability** factor are set to **High** importance.
    - To exclude a factor, disable the option next to the factor's name. Use the slider to set the relative importance of an included factor to **Low**, **Medium**, or **High**. When you finish making changes, select **Apply** to update the list of suggested resources based on the configured settings.

> [!NOTE]
> Modified settings persist for only one team member requirement. Default settings are restored each time that you close the side pane or generate suggested resources for another team member.

## Next steps

To learn how to narrow down the list of suggestions by comparing resources, shortlisting them, and finally booking a team member, see [Compare and book from suggested resources](./compare-and-book-from-suggested-resources.md).
