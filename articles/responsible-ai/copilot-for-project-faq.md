---
title: Copilot for project responsible AI FAQ
description: This article provides answers to frequently asked questions about Microsoft Copilot for project.
author: poojafandan
ms.author: poojafandan
ms.topic: faq
ms.date: 11/15/2024
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.collection:
  - bap-ai-copilot
---

# Copilot for project responsible AI FAQ

[!INCLUDE[banner](../includes/banner.md)]

This article provides answers to frequently asked questions about Microsoft Copilot for project.

## AI-driven features

Copilot offers AI-driven experiences that revolutionize how project managers perform essential and time-consuming tasks through a simple command or button click. AI-assisted tools and insights enhance the ability of project managers to achieve successful project outcomes. These features facilitate seamless project structuring, risk assessment together with suggested mitigations, and concise status reports that integrate scheduling and financial data. They offer valuable insights into overall project progress, financial performance, and schedule adherence. Because task, risk, and project summaries can easily be created, Copilot helps project managers save time and more efficiently allocate their focus to strategic work.

### What is Copilot for project?

Copilot for project is a suite of features that streamline project management tasks in the system through plain English. Based on a project name and description that are provided as input, Copilot for project can generate a preliminary work breakdown structure (WBS) and therefore simplify the task planning process. For ongoing projects, Copilot for project facilitates risk assessment by analyzing the risk register and providing suggested mitigations together with the probability that each identified risk might occur.

In addition, project managers can effortlessly generate detailed status reports through Copilot. They can integrate concise summaries of scheduling and financial data while they also deliver insightful content about overall project progress, financial performance, and schedule adherence. These reports are conveniently saved and can easily be recalled with all prior edits preserved.

Copilot also offers a sidecar chat feature that enhances accessibility and efficiency in project management by letting users initiate all these actions through typed commands.

### What can Copilot for project do?

Copilot for project helps customers improve project planning and execution processes, and ultimately deliver projects more efficiently. By harnessing the power of advanced machine learning techniques, including natural language processing that's powered by Azure Open AI, customers can save time, reduce the risk of underestimating or overestimating task durations, and continuously improve project planning and execution processes. Therefore, Copilot for project can help their business improve project delivery times, reduce costs, increase customer satisfaction, and ultimately drive growth and profitability.

Project managers in professional services organizations commonly agree that one of most repetitive and time-intensive tasks in their job is the production of project status reports. Project managers first gather and summarize data from multiple sources. They then provide commentary about each dimension of project health: scope, schedule, or budget. Finally, to provide transparency about threats to the project, they also summarize risks.

Copilot for project's project status report gives project managers a head start by automatically generating the key components of the report. Therefore, project managers can focus on the narrative text. They can refine what's relevant to the specific project without having to expend energy on mundane, repetitive tasks such as data aggregation and summarization. An accurate project status report yields significant time savings per project. These savings can be especially significant in cases where project managers divide their time among multiple projects in an organization.

### What are Copilot for project's intended uses?

As an AI assistant to project managers, Copilot for project provides a set of intended uses: 

- **Task plan/WBS** – Automatic generation of a WBS is intended to give the project manager a head start in the process of building a project delivery plan. It serves a similar purpose to a project template where related activities in the structure are contextually based on the scope and timeline of the project. As for a project template, the expectation is that the activities are modified to meet the detailed needs of the project. These modifications might include deletions, additions, and changes in duration, effort, dependencies, and assignees.
- **Risks and mitigation plan** – Automatic generation of risks is intended to help the project manager identify and document potential threats to the health of a project. Given the disposition of the project's scope, schedule, and budget, risk registers give the project manager a way to warn all relevant stakeholders about factors that can prevent the project from remaining green. Each risk includes corresponding mitigation.
- **Project status report** – The purpose of the system is to provide an editable project status report to give the project manager a head start as they perform a core part of their job function. All narrative sections can and should be reviewed by the project manager before the report is finalized and distributed. In most organizations, project status reports are shared with both customers and internal service organization leadership.

### How was Copilot for project evaluated? What metrics are used to measure performance?

We evaluate the features both qualitatively and quantitatively. To assess the quality of the feature, we conducted user studies with project managers to gather their feedback about their experiences, thoughts about the feature's quality, and suggestions for improvement.

Additionally, we're monitoring telemetry data to track the number of customers who tried the feature, the success rate of the feature, and the ratio of positive to negative feedback. Before we released the Copilot feature in multiple geographies, we conducted extensive testing to ensure its functionality. If you encounter any issues with the generated content or any of the listed use cases, provide feedback. Your feedback is used to enhance Microsoft's products and services. Your organization's IT admins might have access to your feedback data for management purposes. For more information, see the [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839). 

Copilot for project was assessed for various languages. For more information about language availability, see [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external). The system might not work as well in languages that weren't assessed, and the accuracy and user experience might be affected.

### What are the limitations of Copilot for project? How can users minimize the impact of Copilot for project's limitations when using the system?

- AI-generated tasks do **not** automatically create assignees, dependencies, or task checklist items. You can add the desired parameters after the tasks are automatically generated.
- Actuals, such as time, expenses, or materials, must be logged before the risk assessment and project status report can be generated through Copilot.
- Although the AI-generated summary narrative provides an initial overview, it might not always accurately represent the project's true context or health. All parts of the summary narrative are editable and should be thoroughly reviewed by the project manager before the report is finalized and distributed. Edits should be made, as necessary, to ensure an accurate representation of the project's status.

### What operational factors and settings allow for effective and responsible use of Copilot for project?

- As an administrator, you can enable and disable the **Copilot for project** feature through feature control settings.
- As a feature user, you can provide short and accurate commands in the sidecar to trigger the desired action. The triggers that are related to the previously described scenarios produce the desired output, such as "generate tasks, create risk plan, create project status report." Triggers that aren't intended to invoke these three capabilities show an error.
- The output is based on the project name and description for the tasks, and on project financial data for the risk assessment and project status report.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
