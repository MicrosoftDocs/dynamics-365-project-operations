---
title: Copilot for project overview
description: This article provides information about Microsoft Dynamics 365 Copilot for project features.
ms.date: 11/15/2024
ms.update-cycle: 180-days
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
author: poojafandan
ms.collection:
  - bap-ai-copilot 
---

# Copilot for project overview


Copilot for project is an assistive capability that's powered by Microsoft Azure Open AI's large language model. The Copilot feature is designed to help improve the efficiency of different roles in Dynamics 365 Project Operations, including the project manager and practice manager. It provides a user-friendly and intuitive experience that helps maximize productivity while it also helps improve visibility into project performance.

The Copilot feature has four capabilities:

- Task plan generation
- Risk assessments
- Project status reports
- Interactive, chat-like experience


> [!IMPORTANT]
> To ensure adherence to ethical guidelines and responsible AI usage, the Copilot feature isn't used to create projects that are aimed at suggesting offensive, destructive, or abusive content. Azure Open AI incorporates robust filters and safeguards to help prevent the generation of such content. Review content/output for appropriateness, accuracy, and completeness. 

## Task plan generation

This capability lets project managers get realistic, AI-generated task plan recommendations that show suggested durations and effort for each task, to help speed up the process of creating projects. It uses machine learning algorithms, including natural language processing that's powered by Azure Open AI, to analyze the project name and description and create tasks that can be modified by the project manager.

To generate the suggested task plans for a project, the project manager or other intended user must provide the project name. The relevance of the tasks increases as more specific information is added in the project details.

To use AI-generated tasks to create a work breakdown structure (WBS), follow these steps.

1. On the **Projects** command bar, select **New project**.
1. Provide the name of the project. Be specific, and ensure that the project name is in context for the type of project.
1. Provide a description. Although this information isn't required for automatic generation of the tasks, it provides context that helps the Copilot feature generate more relevant tasks.
1. Provide other details, such as the project start and end dates. If no start date is provided, the Copilot feature uses the project creation date and time as the start date.
1. On the command bar, select **Copilot suggestions**, and then select **Task plan**. AI generates the task name, duration, and start date. A maximum of 100 tasks can be created based on the project name.

If task creation is successful, a message on top of the command bar notifies you that tasks were created by using AI. If the task creation isn't successful, an error message is shown on top of the command bar.

In the task details, all tasks that were created by using AI have a distinctive label, **suggested by AI**. You can customize these tasks to align them with your specific project requirements. Additionally, you have the flexibility to add manual tasks to the list. After the tasks are created, you can edit, remove, or append them by using the same process that's used for [manually created tasks](create-wbs.md). 

> [!NOTE]
> AI-generated tasks do **not** automatically create assignees, dependencies, or task checklist items. You can add the desired parameters after the tasks are automatically generated.

## Risk assessments

This capability lets project managers assess potential risks, receive suggested mitigation plans, and track ongoing issues with their projects. It uses a project's metadata, such as the project's scope, schedule, and budget, to assess risks and alert stakeholders about factors that might hinder project progress. The mitigation plan provides a set of recommended steps that project managers can use to address and minimize the identified risks. This proactive approach gives project managers the means to effectively manage and mitigate potential obstacles, so that they can help the project remain on track and minimize adverse impact.

> [!NOTE]
> Actuals, such as time, expense, or materials, need to be logged to generate Risk assessment and Status report through Copilot.

To use AI-generated risk assessments, follow these steps.

1. Select the project that you want AI to automatically generate risks and mitigations for.
1. On the command bar, on the **Risks** tab, select **Copilot suggestions**, and then select **Risks and mitigations**. If the process is successful, a message on top of the command bar notifies you that risks and mitigations were created by using AI. If the process isn't successful, you receive an error message.
1. To manually add new risks, select **New risk** on the command bar. To add existing risks, select **Add existing risk**.
1. To edit, activate, deactivate, delete, or assign risks, select the risk in the grid.
1. Select the arrow button in the lower right of the window to go to risks and mitigation on the next page.

## Project status reports

This capability lets project managers get AI-generated project status reports based on critical key performance indicators (KPIs), work, and financial activity that's recorded on the project. Project managers can then concentrate on crafting the narrative text by using AI-generated summaries as a starting point. Therefore, project managers can refine project-specific relevance without having to expend energy on monotonous and repetitive tasks such as data aggregation and summarization. The project status report provides valuable insights to practice leads and other leadership members, to help them track progress, evaluate performance, and make informed decisions.

To generate a project status report, follow these steps.

1. Select the project to generate the project status report for.
1. On the command bar, select **Copilot suggestions**, select **Status report**, and then select either **Internal** or **External**.

    - The internal report contains budget value and budget tracking, together with a breakdown.
    - The external report provides insights into overall tasks metrics.

1. Use the buttons on the command bar to share, download, delete, print, and assign the report.

The project status report is created by using AI and the project metadata that's stored in the Dataverse tables. The report has the following key components:

- **Title banner** – This section indicates whether the report is internal or external. It also provides information such as the user's identity, the date of creation, the project name, and the report status.
- **AI notification** – An icon indicates that the content of the report was generated by using AI.
- **Summary** – This section presents a concise, AI-generated overview of the current and recent project status, based on the project's financial, resource, effort, and schedule data. This section is the only editable section of the project status report.
- **Charts and graphs** – Visual representations, including financial-related, task-related, or effort-related charts, are derived from the project data that's stored in the Dataverse tables. 

> [!IMPORTANT]
> Although the AI-generated summary narrative provides an initial overview, it might not always accurately represent the project's true context or health. Therefore, all parts of the summary narrative are editable and should be thoroughly reviewed by the project manager before the report is finalized and distributed. Edits should be made, as necessary, to ensure an accurate representation of the project's status.

## Interactive, chat-like experience

A chat-format Copilot assistant is available, where you can ask questions and get help creating task plans, risk assessments, and status reports. The Copilot assistant generates contextual answers based on user questions in the project's scope, for a seamless and personalized experience.

To hide the Copilot assistant window, select the **AI** icon.

## Enable or disable the Copilot for project feature

For existing tenants, this feature is turned on by default. For new tenants, use the following steps to turn the feature on. Before you can enable the Copilot for project feature, you must upgrade to the latest version.

To enable Copilot for project, follow these steps.

1. In Project Operations, go to **Settings** \> **Parameters** \> **Feature Control** \> **Enable Copilot**.
1. Select **Accept** to enable the feature.
1. Select **See terms** to learn more about the AI terms.
1. Select **OK** to enable the feature.
1. Select **Save**.

   > [!NOTE]
   > To disable the Copilot for project, follow the enable steps and select **Disable Copilot** in step 1.

> [!IMPORTANT]
Depending on where your environment is hosted, you might need to allow data movement across regions to use them. If your environment is hosted in a region that requires data movement across regions to use copilots and generative AI features, tenant administrator need to consent to the terms of use on the Move data across regions checkbox in the Power Platform admin center. [Learn more](/power-platform/admin/geographical-availability-copilot#enable-data-movement-across-regions) how data movement works across regions. 

## Additional resources

- [Copilot for project responsible AI FAQ](../responsible-ai/copilot-for-project-faq.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
