---
title: Log time using Dynamics 365 Time Entry Mobile App (Preview)
description: This article provides information about logging time using the new Time Entry Mobile App (Preview).
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/25/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Log time using Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

This article provides information about logging time using the new Time Entry Mobile App (Preview).

## Create a time entry

Time entries can be created in multiple ways using the mobile app. 

### Create a time entry through Quick Create form

To create a time entry through Quick Create form, follow these steps.

1. Log in to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
1. The app loads with **My Time** as the default landing page.
1. Open the quick create form by selecting the "+" (new time entry) icon at the bottom of the page.
1. Enter values for fields like Duration, Project, Task, Role, and select **Save time**. 

> [!NOTE]
> **Project** and **Task** are required in order to create **Work** type time entries using the mobile app.

### Create a time entry from Project Assignments (My Work)

To create a time entry from Project Assignments (My Work), follow these steps.

1. Log in to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
1. The app loads with **My Time** as the default landing page.
1. Tap **My Work** to navigate to this page. A list of Projects and Project Tasks is visible if your organization uses assignments within project planning.
1. Select **Create** for the Project Task you'd like to log time entries on. This step opens the quick create form with prefilled fields for **Project**, **Task**, and **Role**.
1. To create the entry, modify duration and any other necessary fields, then select **Save time**.

### Create a time entry using the Timer

To create a time entry using the Timer, follow these steps.

1. Log in to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
1. The app loads with **My Time** as the default landing page.
1. Tap **Timer** to navigate to this page.
1. Select the **Start** or **Play** button on top to begin a new timer recording. Let the timer go on as long as your dedicated work is in progress. 
1. Select **Stop** to end the timer. A new timer recording is created with timestamp in the name for reference.
1. Select **Create** to convert this timer recording into a time entry. The quick create form is opened once again with Duration populated from the recording.
1. To create the entry, modify any other necessary fields, and select **Save time**.
1. You may also **Delete** any unused recordings using the delete icon, if they aren't required anymore.
 
> [!NOTE]
> Timer recordings round off to the nearest minute when stopped. This constraint implies any recordings less than one minute have a duration set to one minute by default.

## Modify existing time entries

To modify existing time entries, follow these steps.

1. Navigate to **My Time** section of the mobile app.
1. Select any day of the week where time entries are present.
1. To **Edit** a draft entry tap the **Edit** button. This step opens the **Edit time entry** form where users can modify the necessary fields and **Save time**.
 
## Submit, recall, or delete time entries

### Multi-select time entries

To multi-select time entries, follow these steps.

1. Navigate to **My Time** section of the mobile app.
1. Tapping the white space on a time entry selects it. Similarly, tapping it once again unselects the entry.
1. Doing so for multiple time entries together leads to multi-selection of entries and the actions available to the user depend on the time entry statuses of each entry.  

### Delete time entries

To delete time entries, follow these steps.

1. Navigate to **My Time** section of the mobile app.
1. Select one or more draft time entries.
   - If all entries selected are in editable state (_Draft, Returned_), users get the option to **Delete** the entries by tapping the Delete icon.
   - If any one of the selected entries is read-only (for example: Submitted or Approved), the Delete icon won't appear.

### Submit or Recall time entries

To submit or recall time entries, follow these steps.

1. Navigate to **My Time** section of the mobile app.
1. Select one or more time entries.
   - If all entries selected are in editable state (_Draft, Returned_), users get the option to **Submit** the entries using the Submit (arrow) icon.
   -  If all entries selected are in **Submitted** state, users get the option to **Recall** using the respective icon.
   -  On trying to **Recall** an **Approved** time entry, users are asked to enter a justification for Recall Request.

## Track completion of logging time

To track completion of logging time, follow these steps.

1. Log in to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
1. The app loads with **My Time** as the default landing page.
1. Tap **My Week** to navigate to this page. You may track day-wise hours logged and the weekly total hours through the two visualizations available in this section of the app.


### Known accessibility issues

These accessibility issues are being worked on currently to be resolved.

- Screen Reader doesn't read out accurate labels for expand, collapse, and pin capabilities within **My Work** page.
- Screen Reader isn't able to read out the duration values within **My Week** charts and occasionally reads labels that aren't visible.
- Screen Reader doesn't announce certain headings and states for pages
- Screen Reader focus doesn't return to the Calendar control on activating the calendar from new time entry form.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
