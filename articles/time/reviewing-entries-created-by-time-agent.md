---
title: Review time entries created by the Time Entry feature of the Time and Expense Agent (preview)
description: Learn how team members can review and submit time entries created by the Time Entry feature of the Time and Expense Agent.
author: mohitmenon
ms.date: 05/13/2025
ms.topic: how-to
ms.custom: 
  - bap-ai-copilot 
ms.reviewer: johnmichalak
ms.author: mohitmenon
---

# Review time entries created by the Time Entry feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

After a team member sets up their agent preferences as described in [Start using the Time Entry feature of the Time and Expense Agent as a team member](use-time-entry-agent-in-teams.md), the experience of logging time entries is as follows:

1. At the beginning of a week, the agent creates draft time entries for the user.
1. The user receives an alert from the agent in Microsoft Teams. This alert summarizes the time entries that were created.
1. The user reviews the time entries in either Teams or the Dynamics 365 Project Operations web app.
1. The user modifies the time entries as required and submits them for approval.
1. On the last working day of the week, the agent sends the user a reminder to submit any missing hours.

The following sections explain these steps and the behavior of the Time Entry feature of the Time and Expense Agent.

## Agent behavior during time entry creation

The Time Entry feature of the Time and Expense Agent creates time entries based on the user's preferences.

### Sources of time entries

Options for the sources of time entries include **Project task assignments**, **Booked Capacity**, and **Previous week's entries**.

- If a user selects **only one source**, the agent considers only the hours that come from that source on each day of a working week.
- If a user selects **more than one source**, the agent prioritizes information from **project task assignments** first, because task-level details are available. It then considers information from **booked capacity**. It considers the **previous week's entries** only as a fallback source, in cases where no information is available for assignments or bookings during that week.

### Frequency of time entry creation

Currently, the agent creates all time entries for a week together, at the beginning of the week. The beginning of the week is defined at the organization level. For example, if an organization defines it as Sunday (that is, the week is from Sunday through Saturday), the agent creates time entries for the entire upcoming week on Sunday.

> [!NOTE]
> The beginning of the week isn't the same as the first working day of the week. Working days are based on a resource's working hours calendar.

### External comments for time entries

If a user asks the agent to create external comments for all time entries, the behavior varies, depending on whether the Outlook calendar must be used to enhance comments:

- **If the Outlook calendar doesn't have to be used:** The agent generates external comments when it creates time entries at the beginning of the week. It uses time entry details such as the project, task, and role.
- **If the Outlook calendar must be used:** Because Outlook meetings might be created later in the week, the agent doesn't generate external comments when it creates time entries at the beginning of the week. Instead, it generates them on the last working day of the week.

    > [!NOTE]
    > The last working day of the week is based on the resource's working hours calendar. For example, if the organization's week is from Sunday through Saturday, and the user's working days are Monday through Friday, external comments are generated Friday morning.

> [!IMPORTANT]
> Because the agent creates time entries for a week at the beginning of that week, the user must set the preferences for the agent and give consent to it before that day. Otherwise, the agent can't create time entries. If the agent is enabled after the beginning of a week, the agent starts to create time entries for the user at the beginning of the next week.

## Get alerts from the agent

The agent sends an alert at the following times:

- As soon as it creates time entries for the week (at the beginning of a week).
- When it generates external comments for the week (on the last working day of the week).
- If it must remind the user to submit missing hours (on the last working day of the week).

### Review time entries created by the agent

For alerts that are related to created time entries or external comments, the user receives an adaptive card in Teams. The adaptive card provides a summary of the user's time entries for the current working week. The following illustration shows an example

:::image type="content" source="../media/reviewentries.png" alt-text="Screenshot of an adaptive card that shows the weekly summary of time entries created by the agent.":::

Here is an explanation of key elements of the adaptive card:

- **Daily summary** – The card highlights the total hours for each day of the current week and the number of those hours that need review because they were created by the agent.

    An asterisk (\*) to the left of a day indicates that the agent created time entries for that day.

- **Submit all** – Select this button to submit all draft hours for the current week.
- **Open in Web** – Select this link to open a new browser window or tab where the **Time Entry** module in Project Operations is filtered to the current week.
- **View Day** – Select this button next to each day of the current week to load a new adaptive card that shows details of the individual time entries that were created for that day.

    - For each entry, the card shows the source and the creator. The creator can be either **Copilot** (=&nbsp;the agent) or **User**.
    - Use the date selector at the bottom of the card to view the entries for other days in the week.

    :::image type="content" source="../media/daywiseentries.png" alt-text="Screenshot of the adaptive card that shows details of a day's time entries. The creator and source information and the date selector are highlighted.":::

### Modify time entries created by the agent

Time entries that the agent created can be modified in two ways:

- **Directly in Teams** – Use the **View Day** buttons on the weekly summary adaptive card to open the time entry details adaptive card for specific days.

    In this case, the only two fields that can be modified are **Duration** and **External Comments**. After you make the required changes, you can select either **Save changes** or **Submit all**. The **Submit all** button submits all entries for that day only.

- **In the Project Operations web app** – Use the **Open in Web** link on an adaptive card to go to the **Time Entry** module in the Project Operations web app.

    Use this method to make more significant changes to time entries. For example, the changes might involve deleting or changing fields such as **Task** and **Project**.

    > [!NOTE]
    > A sparkle symbol indicates time entries that the agent created, or that the agent generated external comments for.

## Missing time entry alert

The Time Entry feature of the Time and Expense Agent sends users an alert at the end of each work week if it determines that they have any missing hours.

A day is said to have missing hours for a user if the total number of hours in a **Submitted**, **Approved**, or **Recall Requested** state (that is, non-draft hours) is less than the user's working hours for that day.

The alert shows a summary of all days in the current week that have missing hours. It also includes the following details:

- The number of hours that are missing
- Draft hours that can be submitted for those days

Users can either submit all suggested draft hours that the agent shared in the alert or use the Project Operations web app to create and submit new time entries.

> [!IMPORTANT]
> The **Duration** field accepts only numerical values that are above 0 (zero).
>
> If modifications to the **Duration** field cause the total project-related hours for a day to exceed 24, no time entry records are updated when the user selects **Save changes** or **Submit all**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
