---
title: Project and task limitations
description: Learn about limits for Project Operations projects and tasks.
author: aarondodell-msft
ms.date: 11/22/2023
ms.topic: conceptual
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: aarondodell
---

# Project and task limitations

You should be aware of the following limitations if you're using the work breakdown structure in Project Operations. These limits apply to projects and tasks. For more information, see [Project for the web limits and boundaries](/project-for-the-web/project-for-the-web-limits-and-boundaries).

## Project limitations

| Field                                              | Limit                |
| -------------------------------------------------- | -------------------- |
| Maximum total tasks for a project                  | 500\*                |
| Maximum total duration for a project               | 3650 days (10 years) |
| Maximum total resources for a project              | 300                  |
| Maximum total links (successor only) for a project | 600                  |
| Maximum total custom fields for a project          | 10                   |
| Maximum checklist items per task                   | 20                   |

\* We're currently running a private preview of increased task limits to 1,000 tasks per project. To request access, sign up at [Microsoft Dynamics 365 Project Operations Increased Task Limit Private Preview](https://aka.ms/PO1000tasklimit).

## Task limitations

| Field                                   | Limit                 |
| --------------------------------------- | --------------------- |
| Maximum hierarchy level                 | 10 levels             |
| Maximum links (successor + predecessor) | 20                    |
| Maximum duration of leaf task           | 1250 days             |
| Maximum duration of a summary task      | 3650 days (10 years)  |
| Maximum resources assigned to a task    | 20 resources          |
| Supported date range for a task         | 1/1/2000 - 12/31/2149 |
