---
title: Reviewing time entries created by the agent
description: This article explains how team members can review and submit time entries created by the agent.
author: mohitmenon
ms.date: 04/29/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Start using the Time Entry Agent as a Team Member

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

After a team member has set up their agent preferences as detailed in the previous section, from then on the experience of logging time entries will look like this:
- **Agent creates Draft time entries** for the user at the start of a week
-** User receives an alert on Teams** from the agent summarising entries created
- **User reviews created time entries** either in Teams or on the Project Operations web app
- **Modifies** entries if required and **submits** for approval

These steps and the behaviour of the Time Entry Agent are explained below.

## Agent's behaviour for creation of time entries

The Time Entry Agent (Production Ready Preview) creates time entries based on a user's preferences. 

### Selecting sources for time entries

Choices provided for source of time entries include **Project task assignments**, **Booked Capacity** and **Previous week's entries**. 
- For users who have selected only one of these 3 choices, the agent will only refer to number of hours that come as a result of that source on each day of a working week.
- For users who have selected more than one of these sources, the agent will prioritise information from **Project task assignments** first (since this has task level details), then **Booked capacity** and finally only if there is no information for assignments or bookings - it will use **Previous week's entries** as the fall-back source

### Frequency of creating time entries
- **When the entries are created:** The current behaviour of the agent is to **create all time entries for a week together**, at the beginning of the week as defined by a user's organisation.
- **Beginning of the week**: This is defined at an organisation level. For example, if an organisation has defined the **start of the week **as "Sunday" (Sunday to Saturday week) then the time entries will be created on Sunday for the entire upcoming week.
  - **Note: ** This beginning of the week is not the same as the "first working day of a week". The working days are decided based on a resource's working hours calendar.   

### External comments for time entries

If a user has asked the agent to create external comments for all time entries, this behaviour differs based on:
- **If Outlook calendar is not used to enhance comments:** In this case, external comments are generated at the same time as the creation of time entries (at the beginning of the week) by using time entry details like Project, Task, Role, etc.
- **If Outlook calendar must be used to enhance comments**: In this case, the time entries created at the beginning of the week are created without external comments. This is done because there may be Outlook meetings that get created later in the week. The external comments are then later created on the **last working day of the week**.
  - **Note:** Last working day is based on the resource's working hours calendar. For example, if the organisation's week is from Sunday to Saturday and the user has Monday to Friday as working days, then external comments will be generated on Friday morning.
 
> [!IMPORTANT]
> Since the agent creates time entries for a week on the first day (beginning) of that week, the agent must have been enabled by the user before this day to able to see such entries. If the agent was enabled in the middle of a week, the user will only receive entries from the agent starting from the next week.


 [!INCLUDE[footer-include](../includes/footer-banner.md)]
