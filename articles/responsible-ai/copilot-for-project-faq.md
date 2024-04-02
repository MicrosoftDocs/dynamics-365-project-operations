---
title: Copilot for project responsible AI FAQ
description: This article provides answers to frequently asked questions about Copilot for project.
author: poojafandan
ms.author: poojafandan
ms.topic: conceptual 
ms.date: 04/02/2024
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.collection:
  - bap-ai-copilot
---

# Copilot for project responsible AI FAQ

[!INCLUDE[banner](../includes/banner.md)]

This article provides answers to frequently asked questions about Copilot for project.

## AI-driven features

Copilot offers AI-driven experiences that revolutionize how Project Managers perform essential and time-consuming tasks with a simple command or button click. AI-assisted tools and insights enhance their capabilities to achieve successful project outcomes. These features facilitate seamless project structuring, risk assessment with suggested mitigations, and concise status reports that integrate scheduling and financial data. They offer valuable insights into overall project progress, financial performance, and schedule adherence. With Copilot, Project Managers can save time and allocate their focus more efficiently to strategic work, thanks to the ease of creating task, risk, and project summaries.

### What is Copilot for project?

Copilot for project is a suite of features to streamline project management tasks the system in plain English. With an input of the project name and description, Copilot generates a preliminary work breakdown structure, simplifying the task planning process. For ongoing projects, Copilot for project facilitates risk assessment by analyzing the risk register and providing suggested mitigations along with probabilities of occurrence for each risk identified. Moreover, Project Managers can effortlessly generate detailed status reports through Copilot, integrating concise summaries of scheduling and financial data while also delivering insightful content on overall project progress, financial performance, and schedule adherence. These reports are conveniently saved and can be easily recalled with all prior edits preserved. Additionally, Copilot offers a Sidecar chat feature, allowing users to initiate these actions through typed command, enhancing accessibility and efficiency in project management.

### What can Copilot for project do?

Copilot for project helps the customers to improve project planning and execution processes, and ultimately deliver projects more efficiently. By leveraging the power of advanced machine learning techniques, including natural language processing powered by Azure Open AI, they can save time, reduce the risk of underestimating or overestimating task durations, and continuously improve project planning and execution processes. This can help the customers' business to improve project delivery times, reduce costs, increase customer satisfaction, and ultimately drive growth and profitability.

Project Managers in professional services organizations commonly agree that one of most repetitive and time intensive tasks in their job is production of project status reports. Project Managers first gather and summarize data from multiple sources. They provide commentary on each dimension of project health: scope, schedule, or budget. And to provide transparency regarding threats to the project, the Project Manager also summarizes risks.

With Copilot for Project's project status report, Project Managers are able to get a jump start on automatically generating the key components of the report, allowing them to focus on the narrative text, refining what is relevant for the specific project without expanding energy on the mundane repetitive tasks such as data aggregation and summarization. When the project status report is accurate, it results in significant time savings on a project basis, especially in instances when Project Managers are stretched between multiple projects in an organization.

### What are Copilot for project's intended uses?

As an AI assistant to Project Managers, Copilot for project provides a set of intended uses: 

- **Task Plan / Work Breakdown Structure:** Autogeneration of a work breakdown structure (WBS) intends to provide a Project Manager a head start with building a project delivery plan. It fulfills a similar purpose as a project template where related activities in the structure are contextually based on the scope and timeline of the project. Like a project template, there's an expectation the activities are modified to meet the detailed needs of the project, these changes could include deletion, addition, changes in duration, effort, dependencies, and assignees.

- **Risks and Mitigation Plan:** The autogeneration of risks is intended to aid a Project Manager in identifying and documenting potential threats to the health of a project. Given the disposition of the project's scope, schedule, and budget, risk registers give a Project Manager a way to warn all relevant stakeholders about what can prevent the project from staying green. Each risk includes corresponding mitigation.

- **Project Status Report:** The goal of the system is to provide an editable Project Status Report as a head start to the Project Manager as they fulfill a core part of their job function. All narrative sections can and should be reviewed by the Project Manager before finalization and distribution. In most organizations, the project status reports are shared both to customers and internal service organization leadership.

### How was Copilot for project evaluated? What metrics are used to measure performance?

We evaluate the features both qualitatively and quantitatively. To assess the quality of the feature, we conducted user studies with Project Managers to gather their feedback on their experiences, thoughts about the feature's quality, and suggestions for improvement.

Additionally, we're monitoring telemetry data to track the number of customers who tried the feature, the success rate of the feature, and the ratio of positive to negative feedback. Before releasing the Copilot feature in multiple geographies, we conducted extensive testing to ensure its functionality. If you encounter any issues with the content generated or any of listed use cases, provide feedback. Your feedback is used to enhance Microsoft's products and services. Your organization's IT admins may have access to your feedback data for management purposes. For more information, see the [<u>Privacy Statement</u>](https://go.microsoft.com/fwlink/?LinkId=521839). 

Copilot for project was assessed for various languages. For more informationb about the language availability, see [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external). The system may not work as well in languages that weren't assessed and may impact the accuracy and the user experience.

### What are the limitations of Copilot for project? How can users minimize the impact of Copilot for project's limitations when using the system?

-   AI-generated tasks do **not** automatically create assignees, dependencies, or task checklist items. You can add the desired parameters after the tasks are automatically generated.

-   Actuals, such as time, expense, or materials, need to be logged to generate Risk assessment and Status report through Copilot.

-   Although the AI-generated summary narrative provides an initial overview, it might not always accurately represent the project's true context or health. All parts of the summary narrative are editable and should be reviewed thoroughly by the Project Manager before the report is finalized and distributed. Edits should be made, as necessary, to ensure an accurate representation of the project's status.

### What operational factors and settings allow for effective and responsible use of Copilot for project?

-   As an administrator, you can enable and disable the feature 'Copilot for project' through feature control settings.

-   As a feature user, provide short and accurate commands in the sidecar to trigger the desired action. The triggers pertaining to above mentioned scenarios produce the desired output, such as "generate tasks, create risk plan, create project status report." Triggers that don't mean to invoke these three capabilities display an error.

-   The output is based on the project name and description for the tasks and project financial data for the risks assessment and project status report.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
