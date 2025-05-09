---
title: Reviewing time entries created by the Time Entry feature of the Time and Expense Agent (preview)
description: This article explains how team members can review and submit time entries created by the Time Entry feature of the Time and Expense Agent.
author: mohitmenon
ms.date: 05/09/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Reviewing time entries created by the Time Entry feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing._

After a team member sets up their agent preferences as detailed in the previous section, from then on the experience of logging time entries looks like this:

- **Agent creates Draft time entries** for the user at the start of a week.
- **User receives an alert on Teams** from the agent summarizing entries created.
- **User reviews created time entries** either in Teams or on the Project Operations web app.
- **Modify** entries if required and **submit** for approval.
- Agent sends **reminder to submit any "missing" hours** on the last working day of a week.

These steps and the behavior of the Time Entry feature of the Time and Expense Agent are explained in the following sections.

## Agent's behavior for creation of time entries

The Time Entry feature of the Time and Expense Agent creates time entries based on a user's preferences. 

### Selecting sources for time entries

Choices provided for source of time entries include **Project task assignments**, **Booked Capacity**, and **Previous week's entries**. 
- For users who have **selected only one** of these 3 choices, the agent only refers to number of hours that come as a result of that source on each day of a working week.
- For users who have **selected more than one** of these sources, the agent prioritizes information from **Project task assignments** first (since task level details are available), then **Booked capacity**, and finally, uses **Previous week's entries** as the fallback source only if there isn't available information for assignments or bookings in that week.

### Frequency of creating time entries

- **When the entries are created:** The current behavior of the agent is to **create all time entries for a week together**, at the beginning of the week as defined by a user's organization.
- **Beginning of the week**: This is defined at an organization level. For example, if an organization defines the **start of the week** as Sunday (Sunday to Saturday week) then the time entries are created on Sunday for the entire upcoming week.
  > [!NOTE]
  > The "start of the week" isn't the same as the "first working day of a week". The working days are decided based on a resource's working hours calendar._

### External comments for time entries

If a user asks the agent to create external comments for all time entries, this behavior differs based on:
- **If Outlook calendar isn't used to enhance comments:** In this case, external comments are generated along with the creation of time entries (at the beginning of the week). The agent uses time entry details like Project, Task, Role, etc.
- **If Outlook calendar must be used to enhance comments**: In this case, the time entries created at the beginning of the week are created without external comments. This step is done because there may be Outlook meetings that get created later in the week. The external comments are then later created on the **last working day of the week**.
  > [!NOTE]
  > Last working day is based on the resource's working hours calendar. For example, if the organization's week is from Sunday to Saturday and the user has Monday to Friday as working days, then external comments  generate on Friday morning.
 
  > [!IMPORTANT]
  > Since the agent creates time entries for a week at the "start" of that week, the agent must have its preferences set up and been given consent by the user **before this day**, for the entries to be created. If the agent was enabled after the start of a week, the user only gets entries from the agent starting from the next week.

## Getting alerts from the agent 

The agent sends an alert for the following activities:
- As soon as it creates time entries for the week _(at the Start of a week)_.
- When it generates external comments for the week _(last working day of the week)_.
- To remind the user to submit any "missing" hours _(last working day of the week)_.

### Reviewing time entries created by the agent

For alerts related to created time entries or external comments, the user receives an adaptive card showing a summary of their current work week's time entries (see image).

:::image type="content" source="../media/reviewentries.png" alt-text="Screenshot showing the summary of entries created by the agent in Teams.":::  

Elements of this card that the user must be aware of:
- **Day-wise summary**: Total hours for that day and number of hours that need review (since they're created by the agent) are highlighted.
  - Days that have entries created by the agent is **highlighted with an asterisk** on the left.
- **Submit all**: Selecting this button submits **all Draft hours** for this week.
- **Open in Web**: Selecting this link navigates the user to a new browser window or tab with the Project Operations time entry module filtered on the current week.
- **View Day**: Users can view details of the individual time entries created for a day by selecting the _View Day_ button, next to each day of the week.
  - Doing so loads a new adaptive card that contains the individual time entries for that date (see image).
  - Users also get to see information for the **Source** and **Creator** (Copilot/Agent or User).
  - Date pickers visible at the bottom of this card can be used to **navigate to other days** in the week and review those entries as well.

:::image type="content" source="../media/daywiseentries.png" alt-text="Screenshot showing the day-wise time entries card in Teams.":::

### Modifying time entries created by the agent

Time entries created by the agent can be modified in two ways:
1. Directly within Teams through the day-wise adaptive cards (View Day)
  - The only 2 fields that can be modified in this manner are **Duration** and **External Comments**. 
Users can either **Save changes** or **Submit all** (submits all entries for that day only) after making the necessary changes.

1. From the Project Operations web app (Open in Web) for more significant changes
  - If the changes to time entry involve deletion or changing fields like Task, Project, etc. then users can select **Open in Web** link.
  - This navigates them to the Time Entry module within Project Operations web app.
    > [!NOTE]
    > Time entries created by the agent or having external comments generated by the agent appear with a "sparkle" icon.

## Missing time entries alert

The Time Entry feature of the Time and Expense Agent sends users an alert at the end of the work week, if they have any "missing hours" identified.
- **Missing hours definition**: A day is said to have missing hours for a user if the total hours in _Submitted _or _Approved_ or _Recall Requested_ state (non-Draft hours) is **less than their working hours** for that day.
- **The alert**: The alert consists of a summary of all days in the current week that have missing hours, along with: 
  - The number of hours missing and
  - Any Draft hours for those days that can be submitted
- **Submitting missing hours**: Users can either choose to Submit all suggested hours the agent has shared in the previous alert OR use the Project Operations web app to create and submit new time entries.

> [!IMPORTANT]
> The Duration field only takes numerical values greater than zero. 
> Save or Submit All operations don't update any time entry records if edits to the Duration field cause the total project related hours for that day to exceed 24 hours.

 [!INCLUDE[footer-include](../includes/footer-banner.md)]
