---
title: Dynamics 365 Time Entry Mobile App (Preview)
description: Learn about the new Microsoft Dynamics 365 Time Entry Mobile App (Preview).
author: mohitmenon
ms.author: mohitmenon
ms.date: 02/25/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Dynamics 365 Time Entry Mobile App (Preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

This article provides information about the new Microsoft Dynamics 365 Time Entry Mobile App (Preview).

## Introduction to the mobile app

Users of Dynamics 365 Project Operations who have a valid Team Member or Full Project Operations license can use the Time Entry Mobile App to track time while they are on the go. This app is developed by using a Power Apps canvas app, and users can access it from the Power Apps mobile app.

Use the mobile app to complete these tasks:

- Create new time entries from scratch, and submit them.
- Review time entries that were previously submitted or created as a draft.
- Gain visibility into projects and tasks that a user is currently assigned to.
- View charts that provide a weekly summary of time entries that are logged.
- Use the new timer functionality to record dedicated periods of work, and then turn the timer recordings into time entries.

## Sections in the mobile app

The Time Entry Mobile App has four sections or pages that team members can interact with to log their time entries. This section provides an overview of each page and describes what tasks can be performed on it.

### My Time

- The **My Time** page is the default landing page when the app is initially opened.
- This page contains a day-wise list of time entries, together with a summary of hours that were submitted or approved for that day. The header total can be used to track the completion of hours that are logged daily.
- Users can navigate across the days of each work week. (The beginning and end of a work week are aligned with the **Time Entry** grid in Project Operations.)
- Users can switch between weeks by using either arrow keys or the calendar control in the upper right of the page.
- Users can create new time entries from scratch by selecting the plus sign button (**&plus;**) at the bottom of the page to open the Quick Create dialog. This button is present on all pages of the app.

### My Work

- The **My Work** page shows users a list of projects and project tasks that they are currently assigned to.
- For every assigned task, this page provides details such as the role, end date, and hours that were logged. In this way, the page helps users keep track of their work streams, 

### My Week

The **My Week** page provides two charts:

- An overview of the time entries that were logged across each day of the week. This chart is color-coded by time entry status.
- The percentage composition of total hours that were logged during the week, grouped by time entry status.

In addition, the user's local time zone is highlighted. (Time zone information is based on the location where the mobile device is being used.)

> [!NOTE]
> The device time zone that is shown is considered the time zone for entries that are created by using the app. This rule applies even if a different time zone is selected in the user's personalization settings in Project Operations.

### Timer

- On the **Timer** page, users can begin and end a timer to track dedicated durations of project work that is done throughout the day.
- Users can convert timer recordings into time entries by selecting **Create** and providing details such as the project name and task.

## Get access to the mobile app

Because the Time Entry Mobile App is currently released as a **production-ready preview**, system administrators must *share* it with users in an organization before it can be used to log time entries. Learn more in [Enable the Dynamics 365 Time Entry Mobile App](enable-time-entry-mobile-app.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
