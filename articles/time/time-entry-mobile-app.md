---
title: Time Entry Mobile App (Preview)
description: This article provides information about the new Time Entry Mobile App (Preview).
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/21/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

## Introduction

The Dynamics 365 Time Entry mobile app now allows users with a valid Team Member license to continue and complete their time tracking on-the-go. This app is developed by using a Microsoft Power Apps canvas app and can be accessed by users from the Power Apps mobile app.

This mobile app can be used to:
- Create and submit new time entries from scratch,
- Review time entries that were previously submitted or created as a draft,
- Get visibility into projects and tasks that the user is currently assigned to,
- View a weekly summary of time entries logged in the form of charts and
- Use an **all-new timer** functionality to record dedicated periods of work and turn them into time entries

The next section provides an overview of the views visible within the mobile app and describes what can be achieved in each of them.

## Overview of sections within the app

This mobile app primarily has 4 sections or pages that team members can interact with to log their time entries. These views and their contents are summarised below.

### My Time

- This is the **default landing page** on initial load of the app
- It consists of a day-wise list of time entries, with a summary of hours submitted (or approved) for that day. This allows users to track completion of hours logged daily.
- Users can navigate across days of each work week __(the start and end of a work week are aligned with the Time Entry Grid in Project Operations)__
- Users can also switch between weeks using the arrow keys or calendar control on the top-right
- A “+” (new time entry) button at the bottom allows users to create a new entry from scratch using the quick create form. This button is present across all sections of the app.

### My Work

- This view provides users with a list of Projects and Project Tasks to which they are currently assigned.
- Details like _Role_, _End Date_ and _Hours Logged_ are provided for every assigned task, to help users keep track of their work streams.

### My Week

- This section consists of **two charts**:
 - An overview or summary of time entries logged across each day of the week (color coded by time entry status) and
 - The percentage (%) composition of total hours logged during that week, grouped by time entry status
- In addition to this, the user’s local time zone (based on the where their mobile device is being used) is highlighted. 

> [!NOTE]
> The device time zone displayed above is considered as the **time zone for entries created** by using the mobile app __(even if the user’s personalisation settings within Project Operations have a different time zone selected)__.

### Timer

- This section allows users to **start and stop a timer** to track dedicated durations of project work done throughout the day
- These timer recordings can then be converted into time entries using **Create** option and providing details of Project Name, Task, etc



Since this app is currently released as a **Production Ready Preview**, it must be “shared” with users in an organisation by system administrators, before it can be used to log time entries. Please review the next section to understand how to enable this app for team member users in your organisation.


