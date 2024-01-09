---
# required metadata

title: Get recommendations for a project team member (preview)
description: This article provides information about getting optimal recommendations for a team member, before booking them onto the project.
author: mohitmenon
ms.date: 1/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Get recommendations for a project team member (preview)

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

> [!IMPORTANT]
> The functionality that's described in this article is available as part of a Public Preview release. The functionality and the content of this article are subject to change. 


## Get suggested resources 

To get suggested resources, follow these steps.

1. Ensure you complete the [prerequisites for using resource recommendations](./getting-started-with-resource-recommendations.md).
2. Navigate to **Projects** and then select a project that needs to be staffed with one or more resources.
3. Go to the **Team** tab to view the list of team members on this project.
4. Select any one team member row that isn't already booked with a named resource. _(Don't select more than one row at a time.)_
5. A new **Suggest resources** button appears next to **Subcontracting options**. Select this button.
6. A loading screen appears and after a few seconds, the list of recommended resources is displayed within the side-pane. 


## View more details to evaluate suggested resources

Each suggested resource is assigned a **recommendation score** _(out of 10)_ to signify their appropriateness to that particular team member requirement. This score is currently based only on how relevant their past experience on projects is to a team member requirement. This recommendation score will be augmented in future releases to include more factors (such as Cost, Availability, Utilization, and Skill-match) in upcoming releases. The suggested resources are sorted in decreasing order of this score.


>[!NOTE]
> While displaying suggested resources,  by default, contract workers are also displayed along with full-time employees. To display only full-time employees, disable the **Show contractors** toggle.
> By default, the initial list of suggested resources is limited to 20 resources. This can be extended by 5 resources at a time using the **View more suggestions** button.


To get more information about a suggested resource and interpret their recommendation score, follow one of these two steps:

- Select the **information icon** next to any resource's name.
- Select any one suggested resource rows through the grid and then select the **View details** button.

This displays additional information related to past experience of that resource. The following list summarizes the metrics being displayed.

  - **Experience match (%)** refers to the percentage similarity between work done by this resource on previous project tasks and the team member requirements being staffed.
  - **Relevant past experience** consists of 3 parameters: number of similar project tasks, projects worked on, and the number of hours worked on these similar project tasks (adjusted for experience match %).
  - **Task-wise score** provides the recommendation score for each task that is a part of the team member requirement. 

## Shortlist resources to narrow down suggestions

The suggested resources display across two tabs: **Suggested** and **Shortlisted**. By default, the **Shortlisted** tab is empty, and all suggestions are contained within the **Suggested** tab. There are multiple ways to shortlist resources that fit the staffing criteria: 

  - From the **Suggested** tab, select **View details** for a resource. You can navigate to other resources using the **Next** and **Previous** buttons.
      - Within this view, use the **Shortlist** button to add a resource to the Shortlisted tab.
  - Alternatively, select one or more resource rows from the **Suggested** tab and select **Shortlist**. These resources appear on the **Shortlisted** tab. More resources can be similarly added.
    
Similarly, a resource from the **Shortlisted** tab can be removed and returned to the **Suggested** tab by using the **Remove** button.

## Continue to book shortlisted resources

The final step to complete staffing of a team member from the list of recommendations is to *Book* a resource. 

To book a resource, after you narrow down your list to the desired number of resources, navigate to the **Shortlisted** tab and select **Continue booking**. Selecting  **Continue booking** creates a new resource requirement or updates an existing requirement and redirects you to the **Schedule board**, where information about the resources' availability is visible to make the final booking decision.

For more information on using the **Schedule board** to book a resource, see [booking from the schedule board](/dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board). 
