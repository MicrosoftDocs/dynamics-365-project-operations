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
- **User receives an alert on Teams** from the agent summarising entries created
- **User reviews created time entries** either in Teams or on the Project Operations web app
- **Modifies** entries if required and **submits** for approval
- Agent sends **reminder to submit any "missing" hours** on the last working day of a week

These steps and the behaviour of the Time Entry Agent are explained below.

## Agent's behaviour for creation of time entries

The Time Entry Agent (Production Ready Preview) creates time entries based on a user's preferences. 

### Selecting sources for time entries

Choices provided for source of time entries include **Project task assignments**, **Booked Capacity** and **Previous week's entries**. 
- For users who have selected only one of these 3 choices, the agent will only refer to number of hours that come as a result of that source on each day of a working week.
- For users who have selected more than one of these sources, the agent will prioritise information from **Project task assignments** first (since this has task level details), then **Booked capacity** and finally only if there is no information for assignments or bookings - it will use **Previous week's entries** as the fall-back source

### Frequency of creating time entries
- **When the entries are created:** The current behaviour of the agent is to **create all time entries for a week together**, at the beginning of the week as defined by a user's organisation.
- **Beginning of the week**: This is defined at an organisation level. For example, if an organisation has defined the **start of the week** as "Sunday" (Sunday to Saturday week) then the time entries will be created on Sunday for the entire upcoming week.
  - **Note**: _The "start of the week" is not the same as the "first working day of a week". The working days are decided based on a resource's working hours calendar.  _ 

### External comments for time entries

If a user has asked the agent to create external comments for all time entries, this behaviour differs based on:
- **If Outlook calendar is not used to enhance comments:** In this case, external comments are generated at the same time as the creation of time entries (at the beginning of the week) by using time entry details like Project, Task, Role, etc.
- **If Outlook calendar must be used to enhance comments**: In this case, the time entries created at the beginning of the week are created without external comments. This is done because there may be Outlook meetings that get created later in the week. The external comments are then later created on the **last working day of the week**.
  - **Note**: _Last working day is based on the resource's working hours calendar. For example, if the organisation's week is from Sunday to Saturday and the user has Monday to Friday as working days, then external comments will be generated on Friday morning._
 
> [!IMPORTANT]
> Since the agent creates time entries for a week at the "start" of that week, the agent must have its preferences set up and been given consent by the user **before this day**, for the entries to be created. If the agent was enabled after the start of a week, the user will only get entries from the agent starting from the next week.

## Getting alerts for created time entries 

The agent sends an alert for the following activities:
- As soon as it creates time entries for the week _(at the Start of a week)_,
- When it generates external comments for the week _(last working day of the week)_ and
- To remind the user to submit any "missing" hours _(last working day of the week)_

### Reviewing time entries created by the agent

For alerts related to created time entries or external comments, the user will receive an adaptive card showing a summary of their current work week's time entries (see image).

:::image type="content" source="../media/reviewentries.png" alt-text="Screenshot showing the starter message in Teams.":::  

Elements of this card that the user must be aware of:
- **Day-wise summary**: Total hours for that day and number of hours that need review (since they are created by the agent) are highlighted.
  - Days that have entries created by the agent will be **highlighted with an asterix** on the left.
- **Submit all**: Selecting this button will submit **all Draft hours** for this week.
- **Open in Web**: Clicking this link will navigate the user to a new browser window or tab with the Project Operations time entry module filtered on the current week.
- **View Day**: Users can view details of the individual time entries created for a day by selecting the _View Day_ button, next to each day of the week.
  - Doing so will load a new adaptive card, that contains the individual time entries for that date (see image).

:::image type="content" source="../media/daywiseentries.png" alt-text="Screenshot showing the starter message in Teams.":::

### Modifying time entries created by the agent

Time entries created by the agent can be modified in two ways:
1. Directly within Teams through the day-wise adaptive cards (View Day) for minor changes and
2. From the Project Operations web app (Open in Web) for more significant changes



 [!INCLUDE[footer-include](../includes/footer-banner.md)]
