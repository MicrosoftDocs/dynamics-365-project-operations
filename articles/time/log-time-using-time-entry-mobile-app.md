---
title: Log time using Dynamics 365 Time Entry Mobile App (Preview)
description: This article provides information about logging time using the new Time Entry Mobile App (Preview).
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/21/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Log time using Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

## Create a time entry

Time entries can be created in multiple ways using the mobile app. These are summarised below.

### Create a time entry through Quick Create form

1. Login to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
2. The app loads with **My Time** as the default landing page.
3. Click the "+" (new time entry) icon at the bottom of the page to open the quick create form.
4. Enter values for fields like Duration, Project, Task, Role etc and click **Save time**. 

> [!NOTE]
> **Project** and **Task** are required in order to create a time entry for **Work** type time entries.

### Create a time entry from Project Assignments (My Work)

1. Login to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
2. The app loads with **My Time** as the default landing page.
3. Tap **My Work** to navigate to this page. A list of Projects and Project Tasks will be visible if your organisation uses assignments within project planning.
4. Select **Create** for the Project Task you'd like to log time entries on.
5. This opens the quick create form with pre-filled fields for **Project**, **Task**, **Role**.
6. Modify duration and any other necessary fields. Hit **Save time** to create the entry.

### Create a time entry using the Timer

1. Login to the **Power Apps** mobile app using your Project Operations user and launch **Dynamics 365 Time Entry (Production Ready Preview)**.
2. The app loads with **My Time** as the default landing page.
3. Tap **Timer** to navigate to this page.
4. Hit **Start** or the **Play** button on top to begin a new timer recording. Let this go on as long as your dedicated work is in progress. 
5. Hit **Stop** to end the timer. This creates a new timer recording with a timestamp in the name for reference.
6. Click **Create** to convert this timer recording into a time entry. The quick create form is opened once again with Duration populated from the recording.
7. Modify any other necessary fields and hit **Save time** to create the entry.
8. You may also **Delete** any unused recordings using the delete icon, if they are no longer required.
 
> [!NOTE]
> Timer recordings round off to the nearest minute when stopped. This implies any recordings less than one minute will have duration set to one minute by default.


## Modify or Delete existing time entries



## Submit or Recall time entries

Multi Select

## Track completion of logging time


