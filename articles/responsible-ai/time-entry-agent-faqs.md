---
title: Responsible AI FAQ for the Time Entry feature of the Time and Expense Agent (preview)
description: Get answers to frequently asked questions about the Time Entry feature of the Time and Expense Agent.
author: mohitmenon
ms.author: mohitmenon
ms.topic: faq 
ms.date: 05/13/2025
ms.update-cycle: 180-days
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.collection:
  - bap-ai-copilot
---

# Responsible AI FAQ for the Time Entry feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

This article provides answers to frequently asked questions about how to use the Time Entry feature of the Time and Expense Agent in Microsoft Dynamics 365 Project Operations.

### What is the Time Entry feature of the Time and Expense Agent?

The agent is an AI-based system that runs in the background to create weekly time entries for project team members in an organization, based on the projects or tasks that each team member is either assigned to or has capacity booked to. It can also use a team member's time entries from the previous week as a source for creating new entries.

The agent sends reminders about any missing time entries for a week. It communicates with team members through Microsoft Teams.

### What can the Time Entry feature of the Time and Expense Agent do?

The overall purpose of the agent is to eliminate delays during the process of submitting time entries for approval, and also during the broader invoicing process. To achieve this purpose, it provides the following capabilities:

- The Time Entry feature of the Time and Expense Agent uses information from project assignments and bookings to generate draft time entries for all team members every day. If no information about assignments or bookings is available, it uses information from the previous week's entries.
- The agent generates external comments to describe the time entries that are created. To generate these external comments, it uses the title and description of Outlook meetings that are relevant to the projects that the team member is working on.
- The agent compares the hours that a user submits with the user's working hours and sends a reminder about any missing time entries that are due for the week. It suggests draft entries that the user can submit to fill the missing hours.

> [!NOTE]
> Users can choose not to use their Outlook calendars to generate external comments. In this case, the agent generates the comments based only on information about the time entry, such as the project, task, role, and duration.

### What are the intended uses of the Time Entry feature of the Time and Expense Agent?

The agent has the following intended uses:

- **Streamline the time entry submission process** by regularly creating time entries that team members can review in Teams or the Project Operations web app.
- **Minimize situations where team members don't submit time entries**, through weekly reminders and suggested time entries for submission.

### How was the Time Entry feature of the Time and Expense Agent evaluated? What metrics are used to measure performance?

- A series of repeated **functional evaluations** reviewed the accuracy of the time entries that the system creates. These evaluations compared the created entries to the desired outcomes.
- In addition, a **rigorous compliance evaluation** process reviewed all system-generated content to test for groundedness and various kinds of harm.
- Our priority is to ensure that the agent is developed according to [Microsoft's Responsible AI standards](https://aka.ms/RAIStandardPDF). To meet this goal, we complete a rigorous assessment process before the system is deployed to users. This process spans a range of areas, including security, privacy, and legal.

### What are the limitations of the Time Entry feature of the Time and Expense Agent? How can users minimize the impact of those limitations when they use the system?

- To generate time entries, this system currently relies on the presence of **project assignments** or **bookings** (at least one of the two) or the **previous week's entries**. For teams that don't use project assignments or bookings for project planning in Project Operations, the agent can only replicate the previous week's entries.

    > [!NOTE]
    > Teams that don't use project assignments or bookings can still get the benefits of external comments that the agent generates, but only after team members manually create time entries.

- Users can't configure when and how often they receive alerts from the agent. Alerts are currently set up as a weekly process that runs for all team members and is triggered at the beginning of their working week.
- The Teams adaptive cards that are used to communicate with users are **static** in nature. They aren't updated in real time. In addition, they can't be updated without triggering the generation of a new adaptive card that contains the latest information. However, the time entries in all newly generated adaptive cards are up to date with the web app.
- Users can't respond to the system in Teams for ad-hoc requests (for example, "Submit all time entries for Monday"). They can interact with the agent only by using predefined Teams response buttons on an adaptive card.

### What operational factors and settings allow for effective and responsible use of the Time Entry feature of the Time and Expense Agent?

- Admins can enable the feature by sharing the Teams app with users. Team members can then automate the creation of their time entries, and can they receive alerts or reminders for rejections and missed time entries.

    > [!NOTE]
    > At any time, users can stop the agent from creating time entries for them by using **Agent preferences** command and selecting **No** when they are asked whether they want the agent to create time entries on their behalf.

- Project managers must ensure that team members are either assigned to project tasks or have capacity booked before they begin their work. In this way, the agent has enough inputs to accurately create time entries.
- Team members can set several preferences to control the agent's behavior.

    - Opt in to or out of automated time entry creation.
    - Specify whether generate external comments are generated for each time entry.
    - Specify whether external comments use relevant Outlook meetings for refinement.

- Team members who opt in to automated time entry creation must review Teams alerts that the agent sends every week. In this way, they can take timely action when it's required.

### How do I provide feedback about the Time Entry feature of the Time and Expense Agent?

- During the public preview stage of this feature's release, users can provide feedback by using the thumbs-up and thumbs-down buttons on the Teams adaptive cards. The product team uses this information to learn which parts of the experience are challenging for users and require improvement.
- In future releases, this feedback mechanism will be enhanced so that users can provide more subjective feedback instead of just a positive or negative sentiment.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
