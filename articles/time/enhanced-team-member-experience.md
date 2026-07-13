---
title: Enhanced Team Member experience (Preview)
description: Learn how team members can keep track of assigned tasks and projects that they're staffed on, using the enhanced team member app experience in Microsoft Dynamics 365 Project Operations.
author: mohitmenon
ms.date: 07/13/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Enhanced team member experience (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

The enhanced team member experience helps you keep track of projects and tasks that you staff each week. It helps you break down the tasks into milestones (checklist items) that are private to you, and it streamlines the process of logging time entries.

This article provides an overview of the new experience and explains how to:

- Enable the Enhanced Team Member experience feature.
- Keep track of projects that you're booked on.
- Keep track of project tasks you're assigned to.
- Add a personal checklist and notes for your tasks.
- Streamline logging of weekly time entries.

## Enable the Enhanced Team Member experience

To enable the Enhanced Team Member experience feature, follow these steps:

1. Ensure that your Microsoft Dynamics 365 Project Operations environment is updated to version **4.166.0.X or later**. This feature isn't available in earlier versions.
1. Sign in to Project Operations as a system administrator.
1. In the left pane, change the area to **Settings**.
1. In the **General** section, select **Parameters**.
1. A list of organization units appears. Double-tap (or double-click) the **Organization Units** row for the columns that aren't links.
1. On the **Project Parameters** page, in the **Feature Control** field, select **Feature Control**.
1. Select **Enable Enhanced Team Member experience feature**, and then select **OK**. If the text **Disable Enhanced Team Member experience feature** appears instead, the feature is already enabled.

After you enable the feature, two new menu items named **Assignments** and **Projects** display in the **My Work** section of the **Project Operations Team Member app only**.

## Track projects that you're booked on

You can view a list of projects for which your capacity is booked and the booking is active in the displayed time period. You can navigate to other weeks to keep track of completed or upcoming projects as well.

> [!NOTE]
> You can configure the list of fields visible within this grid through Power Apps by updating the view named _My Bookings_, within the _Bookable Resource Booking_ table.

To track your project bookings, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select the **Bookings** menu item under **My Work**.

### View time-phased project bookings

To view your time-phased project bookings, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select the **Bookings** menu item under **My Work**. Switch from **My Bookings** view to **My Time Phased Bookings**.
1. Select **Daily**, **Weekly**, or **Monthly** to change the time horizon (set to **Weekly** by default). The selected horizon determines how your bookings are grouped and shows the total hours you're staffed on for that period.
1. The time icon allows team members to show or hide staffed hours for each time slice as well.

## Track project tasks that you're assigned to

You can view a list of project tasks that you're assigned to during the displayed week. You can also go to other weeks to keep track of completed or upcoming task assignments.

> [!NOTE]
> You can configure the list of fields visible within this grid through Power Apps by updating the view named _My Assignments_, within the _Resource Assignment_ table.

To track of project tasks that you're assigned to, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select the **Assignments** menu item under **My Work**.

### View time-phased task assignments

To view your time-phased task assignments, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select the **Assignments** menu item under **My Work**. Switch from **My Bookings** view to **My Time Phased Assignments**.
1. Select **Daily**, **Weekly**, or **Monthly** to change the time horizon (set to **Weekly** by default). The selected horizon determines how your assignments are grouped and shows the total hours you're staffed on for that period.
1. The time icon allows team members to show or hide assigned hours for each time slice as well.

## Add a personal checklist and notes for your tasks

To add a personal checklist and notes for your tasks, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select the **Assignments** menu item under **My Work**.
1. Select the name of the project task (hyperlink) for which you want to add checklist items or notes. A side pane appears with tabs named **My Check-list** and **Notes**.

### Manage a checklist for your project task

Within **My Check-list**, you can:

- **Add an item** to build your checklist.
- Use the radio button (check-box) to **clear an item** from the list when it's complete.
- **Remove items by using the delete icon**.

Each of these actions update the **Overall Progress** at the bottom of this side pane.

### Add notes for a project task

To add notes for a project task, follow these steps:

1. Within **Notes**, select **Add Note** to create a new note. Each note has a title and body, with the option of attaching one file as well. Supported formats include: PDFs, txt, doc, docx, xls, xlsx, csv, ppt, pptx, png, jpg, and jpeg. The file size limit is 5 MB.
1. Select **Add Note and Close** to save the note.

You can also edit or delete notes.

> [!NOTE]
> Only you can view the checklist items and notes you add. Other team members and even Project Managers can't view them.

## Streamline logging of weekly time entries

Before the enhanced team member experience, users started their time entry process from a blank grid without context of projects or tasks that they worked on for that week. Now, team members can use their staffed projects or assigned tasks as the reference for logging time entries.

To log time entries, follow these steps:

1. Go to the Project Operations Team Member app.
1. Select **Assignments** under **My Work**. Select the week you want to log time entries for.
   1. Select **Log time**. The system creates draft time entries for the selected week, based on **Task Assignment hours** for that week. A dialog appears with confirmation of time entry creation along with the number of hours logged.
   1. Go to **Time Entries** and select the corresponding week to review the created entries before submitting for approval.
1. Similarly, select **Projects** under **My Work**. Select the week you want to log time entries for.
   1. Select **Log time**. The system creates draft time entries for the selected week, based on **Booked Project capacity** for that week. A dialog appears with confirmation of time entry creation along with the number of hours logged.
   1. Go to **Time Entries** and select the corresponding week to review the created entries before submitting for approval.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
