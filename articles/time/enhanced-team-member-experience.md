---
title: Enhanced Team Member experience (preview)
description: This article explains how team members can keep track of assigned tasks and projects that they are staffed on, using the enhanced team member app experience in Project Operations.
author: mohitmenon
ms.date: 04/20/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Enhanced Team Member Experience Overview (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The Enhanced Team Member experience enables users to keep track of projects and tasks that they are staffed on every week, further break down their tasks into milestones (check-list items) that are private to them and streamline the process of logging time entries. 

> [!NOTE]
> This is a Preview feature and will receive regular updates over upcoming monthly releases of Project Operations.

This article provides an overview of the new experience and use these capabilities effectively:

- Enable the Enhanced Team Member experience feature.
- Keep track of projects that you're staffed on. 
- Keep track of Project Tasks you're assigned to.
- Add a personal check-list and notes for your tasks.
- Streamline logging of weekly time entries.

## Enable the Enhanced Team Member experience

To enable this feature, follow these steps:

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.166.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units should appear. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Enhanced Team Member experience feature**, and then select **OK**. If the text **Disable Enhanced Team Member experience feature** is shown instead, the feature is already enabled.

After the feature is enabled, users will see two new menu items named **Assignments** and **Projects** under the **My Work** section of the **Project Operations Team Member app only**.

## Keep track of Projects that you're staffed on

- Navigate to the Project Operations Team Member app.
- Select the **Projects** menu item under **My Work**.

Here, you can view a list of Projects for which you've been added as a team member and your membership on that project is active in the displayed week. You may navigate to other weeks to keep track of completed or upcoming projects as well.

> [!NOTE]
> The list of fields visible within this grid can be configured via Power Apps by updating the view named _My Projects_, within the _Team Member_ table.

## Keep track of Project Tasks that you're assigned to

- Navigate to the Project Operations Team Member app.
- Select the **Assignments** menu item under **My Work**.

Here, you can view a list of Project Tasks to which you've been assigned during the displayed week. You may navigate to other weeks to keep track of completed or upcoming task assignments as well.

> [!NOTE]
> The list of fields visible within this grid can be configured via Power Apps by updating the view named _My Assignments_, within the _Resource Assignment_ table.

## Add a personal check-list and notes for your tasks

- Navigate to the Project Operations Team Member app.
- Select the **Assignments** menu item under **My Work**.
- Select the name of Project Task (hyperlink) for which you'd like to add check-list items or notes. A side pane will appear with tabs named **My Check-list** and **Notes**.

### Managing a check-list for your Project Task 

- Within **My Check-list**, users can **Add an item** to build their check-list, use the radio button (check-box) to **clear an item** from the list when it is completed, and **remove items using the delete icon** as well.
  - Each of these steps updates the **Overall Progress** at the bottom of this side pane. 

### Adding Notes for a Project Task

- Within **Notes**, users can select **Add Note** to create a new note.
- Each Note has a title and body, with the option of attaching one file as well _(supported formats include: PDFs, txt, doc, docx, xls, xlsx, csv, ppt, pptx, png, jpg, jpeg formats supported; File size limit: 5 MB)_
- Select **Add Note and Close** to save the note.
- Notes can be edited or deleted as well.

> [!NOTE]
> The check-list items and notes added by a user can only be viewed by them, not by other team members or even Project Managers. 

## Streamline logging of weekly time entries

Prior to the enhanced team member experience, users would begin their time entry process from a blank grid without context of Projects or Tasks that they've been working on for that week. Now, team members can use their staffed Projects or assigned Tasks as the reference for logging time entries. Follow these steps:

- Navigate to the Project Operations Team Member app.
- Select **Assignments** under **My Work**. Pick the week you'd like to log time entries for.
  - Click **Log time**. Draft time entries get created for the selected week, based on **Task Assignment hours** for that week.
  - A dialog should appear with confirmation of time entry creation (along with number of hours logged).
  - Users can navigate to **Time Entries** and select the corresponding week to review the created entried before submitting for approval.
- Similarly select **Projects** under **My Work**. Pick the week you'd like to log time entries for.
  - Click **Log time**. Draft time entries get created for the selected week, based on **Booked Project capacity** for that week.
  - A dialog should appear with confirmation of time entry creation (along with number of hours logged).
  - Users can navigate to **Time Entries** and select the corresponding week to review the created entried before submitting for approval.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
