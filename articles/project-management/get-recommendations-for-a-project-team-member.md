---
# required metadata

title: Get recommendations for a project team member
description: This article provides information about getting optimal recommendations for a team member, before booking them onto the project.
author: mohitmenon
ms.date: 1/10/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Get recommendations for a project team member

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Get suggested resources 

Follow these steps to begin using recommended resources for a project team member:

1. Ensure you have completed the [prerequisites for using resource recommendations](./getting-started-with-resource-recommendations.md).
2. Navigate to **Projects** > **Select a project** that needs to be staffed with one or more resources.
3. Go to the **Team** tab to view the list of team members on this project.
4. Select any one team member row that is not already booked with a named resource. _(Do not select more than one row at a time)_
5. A new **Suggest Resources** button will appear next to **Subcontracting Options**. Click this button.
6. A loading screen will appear and after a few seconds, the list of recommended resources will be displayed within the side-pane. 


## View more details to evaluate suggested resources

Each suggested resource is assigned a **recommendation score** _(out of 10)_ to signify their appropriateness to that particular team member requirement. This score is currently based only on how relevant their past experience on projects is to a team member requirement, this will be augmented to include additional factors _(Cost, Availability, Utilisation & Skill-match in upcoming releases)_. The suggested resources are sorted in decreasing order of this score.


  >[!NOTE]
  > While displaying suggested resources, contract workers are also displayed along with full-time employees by default. Disable the **Show Contractors** toggle to display only full-time employees.


To get more information about a suggested resource and interpret their recommendation score, follow any one of these two steps:

1. Directly click the **information icon** next to any resource's name OR
2. Select any one suggested resource rows through the grid and then click **View Details** button.

This displays additional information related to past experience of that resource. The metrics being displayed are summarised below:

  - **Experience Match** (%) refers to the percentage similarity between work done by this resource on previous project tasks and the team member requirements being staffed.
  - **Relevant past experience** consists of 3 parameters: number of similar project tasks and projects worked on as well as the number of hours worked on these similar project tasks (adjusted for experience match %).
  - **Task-wise score** provides the recommendation score, for each task that is a part of the team member requirement. 

## Shortlist resources to narrow down suggestions

All suggested resources are displayed across two tabs - _Suggested_ and _Shortlisted_. By default, the _Shortlisted_ tab is empty and all suggestions are contained within the _Suggested_ tab only. There are multiple ways to shortlist resources that fit the staffing criteria: 

  - From the _Suggested_ tab, on selecting **View Details** for a resource - you may navigate to other resources using the **Next** and **Previous** buttons.
      - Within this view, use the **Shortlist** button to add a resource to the Shortlisted tab.
  - Alternatively, select one or more resource rows from the _Suggested_ tab and click **Shortlist**. These resources will now appear in the **Shortlisted** tab, where more resources can be similarly added.
    
Similarly, a resource from the _Shortlisted_ tab can be removed and returned to the _Suggested_ tab by using the **Remove** button.

## Continue to book shortlisted resources

The final step to complete staffing of a team member from the list of recommendations, is to *Book* a resource. Follow these steps to complete booking a resource:

  - Once you have narrowed down your list to the desired number of resources, navigate to the **Shortlisted** tab and select **Continue Booking**.
  - This creates a new resource requirement or updates an existing requirement and re-directs you to the **Schedule Board**, where information about the resources' availability will be visible to make the final booking decision.
  - For more information on using the **Schedule Board** to book a resource, please refer to [booking from the schedule board](dynamics365/project-operations/resource-management/book-project#book-from-the-schedule-board). 
