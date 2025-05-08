---
title: Copilot in time entry responsible AI FAQ
description: This article provides answers to frequently asked questions about Copilot in time entry.
author: mohitmenon
ms.author: mohitmenon
ms.topic: faq
ms.date: 09/27/2024
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.collection:
  - bap-ai-copilot
---

# Copilot in time entry responsible AI FAQ

[!INCLUDE[banner](../includes/banner.md)]

This article provides answers to frequently asked questions about how to use Copilot in time entry in Microsoft Dynamics 365 Project Operations.

### What is Copilot in time entry?

Copilot in time entry gives project team members a new, streamlined way to complete all activities that are related to logging weekly time entries. The goal is to make the time entry process less tedious for team members.

### What can Copilot in time entry do?

Copilot in time entry has a limited set of capabilities but will receive updates over the coming months. The following scenarios are currently supported:

- Copilot in time entry can use a project team member's project assignments to suggest time entries for the current week. Those suggestions can then be used to create draft time entries without duplication. Team members have final control over what's submitted for approval. They can modify the draft entries before they submit them.
- For each time entry, Copilot in time entry can generate a first draft of external (customer-facing) comments. To generate these comments, it uses details such as the **Project**, **Project Task**, **Role**, and **Duration** values of each time entry, and takes advantage of the capabilities of large language models that are powered by Azure OpenAI. Before the generated comments are saved to each time entry, they can be edited to meet customer requirements. This feature lets project team members add comments to all the entries for a week in significantly less time than the existing, page-based experience requires.

    > [!NOTE]
    > The set of fields that are used to generate external comments (**Project**, **Project Task**, **Role**, and **Duration**) can't currently be customized.

### What are the intended uses for Copilot in time entry?

As an AI assistant for project team members, Copilot in time entry has the following intended uses:

- **Creating time entries** – Project team members use Copilot in time entry to create their time entries for the current week, based on their existing project assignments.
- **Adding comments** – Users can generate descriptions, modify the generated descriptions, link them to time entries, and submit them for approval in a more efficient manner than the existing process allows for.

This section will be updated with other intended uses over time, as Copilot in time entry receives updates in each release.

### How was Copilot in time entry evaluated? What metrics are used to measure performance?

- Copilot in time entry went through a series of functional evaluations to ensure that it can effectively respond to the user scenarios that it's intended for.
- Copilot in time entry is aimed at improving the life of project team members. Our priority is to ensure that it's developed according to [Microsoft's Responsible AI standards](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4ZPmV) before it's deployed to users.

    To ensure that this goal is met, we complete a rigorous assessment process before Copilot in time entry is deployed to customers. The areas that are assessed include privacy, security (red teaming for varied threats), and accessibility.

### What are the limitations of Copilot in time entry? How can users minimize the impact of Copilot in time entry's limitations when they use the system?

- Currently, Copilot in time entry can log time only for the current week (that is, the week when time entries are created). It can't be used for past or future weeks. To address this limitation, ensure that time entries are created before the end of the current week. In this way, you don't have to create entries for an earlier week.

    > [!NOTE]
    > When Copilot in time entry selects the week that time is being logged for, it doesn't use the user's local time zone settings. Instead, it considers the UTC date (according to the GMT+0 time zone).

- After an action that's triggered from the Copilot sidecar is completed, Copilot in time entry doesn't refresh the time entry grid in real time. To view the changes, the user must manually refresh the time entry grid.

### What operational factors and settings allow for effective and responsible use of Copilot in time entry?

- Consistently ensure that team members are assigned to project tasks before they start to work on them. In this way, you help make Copilot in time entry an effective means of creating time entries.
- Team members who use Copilot in time entry to create their time entries must ensure that they review the suggested entries before they create them. In addition, to ensure that the external comments that Copilot generates meets customer standards, team members must review them before they submit them for approval.
- Out of the box, existing customizations that are in place for Time Entry don't work with Copilot in time entry scenarios. More effort is required to integrate them into Copilot in time entry scenarios. If you need help with the integration of critical customizations, create a support ticket with Microsoft.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
