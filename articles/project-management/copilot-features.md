---
title: Project Operations Copilot overview
description: This article provides information about Microsoft Dynamics 365 Project Operations Copilot features.
ms.date: 06/13/2023
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
author: poojafandan
---

# Project Operations Copilot overview

[!INCLUDE[banner](../includes/preview-banner.md)]


Project management Copilot is an assistive capability powered by Azure Open AI's large language model. This feature is developed to help improve the efficiency of various roles within Dynamics 365 Project Operations, including the project manager, practice manager, and beyond. This capability provides a user-friendly and intuitive experience that maximizes productivity while improving visibility of project performance.

There are four capabilities within the Copilot feature:

- Task plan generation
- Risks assessments
- Project status report
- Interactive, chat-like experience

## Enable the Copilot Feature

The Copilot feature utilizes Azure Open AI to generate results by using both the Microsoft Dataverse table and the provided prompts. You can disable the Copilot feature following the same steps. To enable the Copilot feature, you are required to upgrade to the latest version.

To enable the Copilot feature, follow these steps.

1. In Project Operations, select **Settings** \> **Parameters** \> Feature Control** \> **Enable Copilot**.
1. Select **Accept** to enable the feature.
1. Select **See terms** to learn more about the AI terms.
1. Select **OK** to enable the feature.
1. Select **Save**.

> [!Important]
> In adherence to ethical guidelines and responsible AI usage, projects aimed at suggesting offensive, destructive, or abusive content isn't created using Copilot. Azure Open AI (AOAI) incorporates robust filters and safeguards to help prevent the generation of such content. Review content/output for appropriateness, accuracy and completness. 

## Task plan generation

This feature enables project managers to get realistic AI-generated task plan recommendations with suggested durations and efforts for each task to speed up the creation of projects. The feature uses machine learning algorithms, including natural language processing powered by Azure Open AI, to analyze the project name and description, and create tasks that can be modified by the Project manager.

The project manager, or any other intended user, must provide the project name to generate the suggested task plans for the project. The relevancy of the tasks increases as more specific information is added in the project details.

To use AI generated tasks to create a work breakdown structure (WBS), follow these steps.

1. On the **Projects** command bar, select **New project**.
1. Provide the name of the project. Be specific and ensure that the project name is in context of the type of project.
1. Provide the description. This field isn't a mandatory to auto generate the tasks, but it provides context to help create more relevant tasks.
1. Provide other details, such as project start and finish date. If the start date isn't provided, the Copilot takes the project creation date and time as the start date.
1. On the command bar, select the **Copilot Suggestions** dropdown, and then select **Task plan**. AI generates the task name, duration and start date. A maximum of 100 tasks can be created based on your project name.

If the task creation was successful, you see a message on top of the command bar notifying that the tasks are created using AI. If the task creation wasn't successful, you see an error message on top of the command bar.

Within the task details, there is a distinctive label **suggested by AI** for all those tasks created using AI. These tasks can be customized to align with your specific project requirements. Additionally, you have the flexibility to add manual tasks into this list. Once the tasks are created, the process for editing, removing, or appending them is the same as with [manually created tasks.](create-wbs.md). 

> [!Note]
> The AI generated tasks do NOT create assignees, dependencies or task checklist items automatically. You can add all the desired parameters once the tasks are auto generated.

## Risk Assessments

Risk assessment feature enables project managers to assess potential risks, receive suggested mitigation plans, and track ongoing issues on their projects. This Copilot feature uses a project's metadata such as project's scope, schedule, and budget, to create risks to alert stakeholders about factors that may hinder project progress. The mitigation plan provides project managers with a set of recommended steps to address and minimize the identified risks. This proactive approach equips project managers with the means to effectively manage and mitigate potential obstacles to help the project remain on track and minimize adverse impact.

To AI generated risk assessments, follow these steps.

1. Select the project for which you want AI to auto generate risks and mitigations.
1. On the command bar, select the **Risks** tab.
1. On the command bar select the **Copilot suggestions** drop down, and the select **Risks and mitigations**. If the process is successful, you receive a message on top of command bar notifying that risks and mitigations are created using AI. If the process wasn't successful, you receive an error message.
1. New or existing risks can be added manually using the **New risk** and **Add existing risk** options available on the command bar.
1. To edit, activate, deactivate, delete, or assign risks, select the risk in the grid.
1. Select the arrow button at the bottom right of the window to navigate to risks and mitigation on the next page.

## Status Report

This feature enables project managers to get AI-generated project status reports from critical KPIs, work, and financial activity that is recorded on the project and allows project managers to concentrate on crafting the narrative text utilizing AI generated summaries as a starting point. It helps the project managers refining project-specific relevance, without expending energy on monotonous and repetitive tasks such as data aggregation and summarization. The project status report provides valuable insights into the practice leads and other leadership members in tracking progress, evaluating performance, and making informed decisions.

To generate a project status report, follow these steps.

1. Select the project for which the project status report is to be created.
1. On the command bar, select **Copilot suggestions**, select **Status report**, and then select either **Internal** or **External**.
   - The internal report contains budget value and budget tracking with breakdown.
   - The external report provides insights into overall tasks metrics.
1. You can share, download, delete, print, and assign this report using the options available in the command bar.

The project status report is created using AI and the project's metadata stored in the Dataverse tables. The key components of the report are:

- **Title banner**: This section indicates whether the report is internal or external. It provides information such as the user's identity, date of creation, project name, and report status.
- **AI notification**: An icon indicating the content of the report has been generated by AI.
- **Summary**: Utilizing the project's financial, resource, effort, and schedule data, a concise AI generated overview of the current and recent project status is presented. This is the only editable section of the project status report.
- **Charts and graphs**: Visual representations, including financial, task, or effort-related graphs and charts, are derived from the project's data stored in the Dataverse tables. 

> [!Important]
> While the AI-generated summary narrative provides an initial overview, it may not always accurately represent the project's true context or health. Therefore, all parts of the summary narration are editable and should be thoroughly reviewed by the Project manager prior to finalization and distribution. Any necessary edits should be made to ensure an accurate representation of the project's status.

## Interactive, chat-like experience

There's a chat-format Copilot assistant available where you can ask questions and get assistance in creating task plans, risk assessments, and status reports. The copilot assistant generates contextual answers based on user questions within the project's scope, providing a seamless and personalized experience.

You can select the **AI icon** to hide the assistant window.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
