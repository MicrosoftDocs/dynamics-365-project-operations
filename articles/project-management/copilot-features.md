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

Project Management Copilot is an assistive capability powered by Azure Open AI's large language model. This feature has been developed to improve the efficiency of various roles within the product, including the Project Manager, Practice Manager and beyond. The goal of this capability is to provide you with a user-friendly and intuitive experience that maximizes productivity while significantly improving the visibility of project performance.

There are four capabilities within the Copilot feature:

- Auto task generation
- Risks and mitigation
- Project summary report
- Copilot's interactive, chat-like experience

**Enabling Copilot Feature**

_Navigation Path: Settings \> Parameters \> Feature Control \> Enable Copilot_

The Copilot feature utilizes Azure Open AI to generate results by using both the Dataverse table and the provided prompts. Follow the above mentioned navigation path to ebable the Copilot feature. Once you click on 'Enable Copilot' are presented with an option to choose or decline to turn on the feature. Click the "see terms" link to learn more about the AI terms. Click 'OK' to enable the feature or 'cancel' to opt out. Click save if you have enabled the Copilot feature.
You can disable the copilot feature following the same navigation path. 

In adherence to ethical guidelines and responsible AI usage, projects aimed at suggesting offensive, destructive, or abusive content is created using Copilot. Azure Open AI (AOAI) incorporates robust filters and safeguards to help prevent the generation of such content.

**Auto task generation**

The Auto-Generated Tasks with Suggested Duration and Efforts feature, powered by copilot, enables project managers to create a list of tasks quickly and easily for a project, along with suggested durations and efforts for each task. The tool uses machine learning algorithms, including natural language processing that are powered by Azure Open AI. It analyzes the project name and description, and creates tasks that can be further tailored to match your project needs.

Project manager, or any other intended user is required to provide the project name, at minimum, to generate the suggested tasks for a project. The relevancy of the tasks increases as more specific information is added in the project details.

**Process to auto generate tasks**

_Navigation path: Projects \> New Project \> Copilot suggestions \> Task plans_

  1. Select 'new project' in the Projects command bar.
  2. Provide the name of the project. Be specific and ensure that the project name is in context of the type of project.
  3. Provide the description. It isn't a mandatory field to auto generate the tasks, but it provides context to create more relevant tasks.
  4. Provide other details such as project start and finish date. If the start date isn't provided, the Copilot takes the project creation date and time as the start date.
  5. Click 'Copilot Suggestions' dropdown in the command bar and select Task Plan.
  6. Tasks are created based on your project name. AI generates task name, duration and start date. Note, a maximum of 100 tasks are created.
  7. If the task creation was successful, you see a message on top of the command bar notifying that the tasks are created using AI. If the task creation wasn't successful, you see an error message on top of the command bar.
  8. If you select Copilot - \> 'task plan' on an existing project that has manually created tasks, the auto generated tasks are appended to the existing task list.

Within the task details, a distinctive label, 'suggested by AI', is created for all the tasks created using AI. These tasks can be customized to align with your specific project requirements. Additionally, you have the flexibility to add manual tasks into this list. Once the tasks are created, the process for editing, removing, or appending them is the same as with [manually created tasks.](https://learn.microsoft.com/en-us/dynamics365/project-operations/project-management/create-wbs) 

Note: The auto generated tasks do NOT create assignees, dependencies or task checklist items automatically. You can add all the desired parameters once the tasks are auto generated.


**Risk Assesments**

The automated generation of risks and mitigation aims to assist project managers in identifying and documenting potential threats that could impact the project's well-being. The Copilot feature uses Project's metadata such as project's scope, schedule, and budget, to create risk assessment. It can be helpful in alerting stakeholders about factors that may hinder project progress. The mitigation plan provides project managers with a set of recommended steps to address and minimize the identified risks. This proactive approach equips project managers with the means to effectively manage and mitigate potential obstacles, ensuring the project remains on track and minimizing any adverse impact.

**Process to auto generate risk assesments:**

_Navigation path: Projects \> New Project \> Copilot suggestions \> Risks and Mitigation_

Prerequisite: Tasks within the schedule must be defined.

Auto Generate Risks and Mitigations:

1. Select the project for which you want to auto generate risks and mitigations.
2. Select Risks tab in the command bar.
3. Click Copilot Suggestions drop down in the command bar and select Risks and Mitigations
4. If the process is successful, you receive a message on top of command bar notifying that Risks and Mitigations are created using Copilot. If the process wasn't successful, you receive an error message.
5. New or existing risks can be manually added using the 'new risk' and 'Add existing risk' options available under the command bar.
6. Select the risk in the grid to Edit, activate, deactivate, delete, or assign risks.
7. Select the arrow button at the bottom right of the window to navigate to risks and mitigation on next page.

**Status Report**

The Copilot project summary report empowers project managers by providing a head start in automatically generating the essential components of the report. Summary report aggregates and summarize relevant data in easy to understand format.  It provides intuitive experience to the project managers in crafting the narrative text and refining project-specific relevance, without expending energy on monotonous and repetitive tasks. The summary report provides valuable insights into the practice leads and other leadership members in tracking progress, evaluating performance, and making informed decisions.

**Process to generate summary report:**

_Navigation path: Projects \> New Project \> Copilot suggestions \> Status report \>Internal/External_

  1. Select the project for which the summary report is to be created.
  2. From the command bar, select Copilot suggestions option, select status report and then choose from the options Internal or External.

- The internal report contains budget value, budget tracking with breakdown,
- The external report provides insights into overall tasks metrics.

  1. You can share, download, delete, print, and assign this report using the options available in the command bar.

The report is created using AI and the project metadata stored in the Dataverse tables. The key components of the report are:

- Title banner: This section indicates whether the report is internal or external. It provides information such as the user's identity, date of creation, project name, and report status.
- AI notification: A clear indication that the content of the report has been generated by AI.
- Summary: Utilizing the project's financial, resource, effort, and schedule data, a concise overview of the current and recent project status is presented. This section of the summary report is editable.
- Charts and graphs: Visual representations, including financial, task, or effort-related graphs and charts, are derived from the project's data stored in the Dataverse tables. This section of the summary report isn't editable.

It's important to note that while the AI-generated summary narrative provides an initial overview, it may not always accurately represent the project's true context or health. Therefore, all parts of the summary narration are editable and should be thoroughly reviewed by the Project Manager prior to finalization and distribution. Any necessary edits should be made to ensure an accurate representation of the project's status.

**Copilot interactive experience**

There's an interactive, chat-like experience available where you can ask questions and get assistance in creating tasks, risks, and summary reports. Copilot assistant generates contextual answers based on user questions within the project's scope, providing a seamless and personalized experience.

Click the copilot icon to hide the Copilot chat window.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
