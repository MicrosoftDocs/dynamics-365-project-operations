---
title: Project operations copilot overview
description: This article provides information about project operations copilot features.
author: poojafandan
ms.date: 06/13/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# **Project operations copilot overview**

Project Management Copilot is an assistive capability powered by Azure Open AI's large language model. This feature has been developed to improve the efficiency of various roles within the product, including the Project Manager and beyond. The goal of this capability is to provide you with a user-friendly and intuitive experience that maximizes productivity while significantly improving the visibility of project performance.

There are three capabilities within the Copilot feature:

- Auto task generation
- Risks and mitigation
- Project summary report
- Copilot assistant

**Configuring Copilot Feature**

_Navigation Path: Settings \> Parameters \> Feature Control \> Enable Copilot_

The Copilot feature utilizes Azure Open AI to generate results by using both the Dataverse table and the provided prompts. Follow the above navigation path to opt to turn on the Copilot feature. Once you click on 'Enable Copilot' are presented with an option to choose or decline to turn the feature on. You can click the "see terms" link to learn more about the AI terms. You can click 'OK' to enable the feature or 'cancel' to opt out. Save your choice if you have enabled the Copilot feature.

**Auto task generation**

The Auto-Generated Tasks with Suggested Duration and Efforts feature, powered by copilot, enables project managers to create a list of tasks quickly and easily for a project, along with suggested durations and efforts for each task. The tool uses machine learning algorithms, including natural language processing powered by Azure Open AI, to analyze the project name and description, and create tasks that can be further tailored by the Project Manager as needed.

Project manager, or any other intended user is required to provide the project name, at minimum, to generate the suggested tasks for a project. The relevancy of the tasks increases as more specific information is added in the project details.

**Process to auto generated tasks / work breakdown structure (WBS):**

_Navigation path: Projects \< New Project \< Copilot suggestions \< Task plans_

  1. Select 'new project' in the Projects command bar.
  2. Provide the name of the project. Be specific and ensure that the project name is in context of the type of project.
  3. Provide the description. It is not a mandatory field to auto generate the tasks, but it provides context to create more relevant tasks.
  4. Provide other details such as project start and finish date. If the start date is not provided, the Copilot takes the project creation date and time as the start date.
  5. Click 'Copilot Suggestions' dropdown in the command bar and select Task Plan.
  6. Tasks are created based on your project name. AI generates task name, duration and start date. Note, a maximum of 100 tasks are created.
  7. If the task creation was successful, you'll see a message on top of the command bar notifying that the tasks are created using AI. If the task creation was not successful, you'll see an error message on top of the command bar.
  8. If you select Copilot - \> 'task plan' on an existing project that has manually created tasks, the auto generated tasks are appended to the existing task list.

Within the task details, you'll notice a distinctive label of 'suggested by AI' for all tasks created using AI. These tasks can be customized to align with your specific project requirements. Additionally, you have the flexibility to add manual tasks into this list. Once the tasks are created, the process for editing, removing, or appending them is the same as with[manually created tasks.](https://learn.microsoft.com/en-us/dynamics365/project-operations/project-management/create-wbs)It is to be noted that the auto generated tasks do NOT create assignees, dependencies or task checklist items automatically. You can add all the desired parameters once the tasks are auto generated.

In adherence to ethical guidelines and responsible AI usage, projects aimed at suggesting offensive, destructive, or abusive content is created using Copilot. Azure Open AI (AOAI) incorporates robust filters and safeguards to help prevent the generation of such content.

**Risks and Mitigations**

The automated generation of risks and mitigation aims to assist project managers in identifying and documenting potential threats that could impact the project's well-being. The Copilot feature uses Project's metadata such as project's scope, schedule, and budget, to create risks to alert stakeholders about factors that may hinder project progress. The mitigation plan provides project managers with a set of recommended steps to address and minimize the identified risks. This proactive approach equips project managers with the means to effectively manage and mitigate potential obstacles, ensuring the project remains on track and minimizing any adverse impact.

**Process to auto generate risks and mitigations:**

_Navigation path: Projects \< New Project \< Copilot suggestions \< Risks and Mitigation_

Prerequisites:

- Tasks within the schedule must be defined.

Auto Generate Risks and Mitigations:

1. Select the project for which you want to auto generate risks and mitigations.
2. Select Risks tab in the command bar.
3. Click Copilot Suggestions drop down in the command bar and select Risks and Mitigations
4. If the process is successful, you receive a message on top of command bar notifying that Risks and Mitigations are created using Copilot. If the process was not successful, you'll receive an error message.
5. New or existing risks can be manually added using the 'new risk' and 'Add existing risk' options available in the under the command bar.
6. Select the risk in the grid to Edit, activate, deactivate, delete, or assign risks.
7. Select the arrow button at the bottom right of the window to navigate to risks and mitigation on next page.
8. The following fields are available to depict the Risks and Mitigation plan:

| Subject | Specifies the title of the risk |
| --- | --- |
| Description  | Specifies the details of the risk |
| Risk Probability  | Specifies the probability of the risk to occur |
| Mitigation Plan | A mitigation plan is suggested |

**Status Report**

The Copilot project summary report empowers project managers by providing a head start in automatically generating the essential components of the report. It allows them to concentrate on crafting the narrative text utilizing auto-generated narration and refining project-specific relevance, without expending energy on monotonous and repetitive tasks such as data aggregation and summarization. The summary report provides valuable insights into the practice leads and other leadership members in tracking progress, evaluating performance, and making informed decisions.

**Process to generate summary report:**

_Navigation path: Projects \< New Project \< Copilot suggestions \< Status report \<Internal/External_

  1. Select the project for which the summary report is to be created.
  2. From the command bar, select Copilot suggestions option, select status report and then choose from the options Internal or External.

- The internal report contains budget value, budget tracking with breakdown,
- The external report provides insights into overall tasks metrics.

  1. You can share, download, delete, print, and assign this report using the options available in the command bar.

The report is created using AI and the project metadata stored in the Dataverse tables. The key components of the report are:

- Title banner: This section indicates whether the report is internal or external. It provides information such as the user's identity, date of creation, project name, and report status.
- AI notification: A clear indication that the content of the report has been generated by AI.
- Summary: Utilizing the project's financial, resource, effort, and schedule data, a concise overview of the current and recent project status is presented. This section of the summary report is editable.
- Charts and graphs: Visual representations, including financial, task, or effort-related graphs and charts, are derived from the project's data stored in the Dataverse tables. This section of the summary report is not editable.

It is important to note that while the AI-generated summary narrative provides an initial overview, it may not always accurately represent the project's true context or health. Therefore, all parts of the summary narration are editable and should be thoroughly reviewed by the Project Manager prior to finalization and distribution. Any necessary edits should be made to ensure an accurate representation of the project's status.

**Copilot Assistant**

There is a chat-format copilot assistant available where you can ask questions and get assistance in creating tasks, risks, and summary reports. Copilot assistant generates contextual answers based on user questions within the project's scope, providing a seamless and personalized experience.

You can click the copilot icon to hide the assistant window.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
