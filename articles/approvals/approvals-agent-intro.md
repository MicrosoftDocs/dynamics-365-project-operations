---
title: Approvals Agent overview (preview)
description: Get a brief introduction to the Approvals Agent.
author: abriccetti
ms.date: 07/21/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Approvals Agent overview (preview)

[!INCLUDE [banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The Approvals Agent streamlines the approval process for time, expense, and material transactions. The Time and Expense Agent uses a [Microsoft Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) agent to do an initial review of incoming time, expense, and material entries against policy documents that you upload for each type of entry. If a record meets the criteria outlined in the policy document, the agent marks it as **Ready for approval**. Otherwise, it marks the record as **Needs review**. This initial review makes the approval process more efficient for project managers. It also helps them avoid time-consuming corrections by reducing mistaken approvals.

## Set up the Approvals Agent

An admin must enable and set up the Approvals feature of the Time and Expense Agent by following the steps in [Set up the Approvals Agent using the Dynamics 365 Agent Deployment Tool (preview)](activate-approvals-agent-wizard.md). After the feature is correctly set up, enable the agent by selecting **Enable Time and Expense Agent** in the **Feature Control** field on the **Project Parameters** page.

After you enable the agent, a new **Time and Expense Agent** tab appears on the **Project Parameters** page. Use this tab to upload policy documents for time, expense, and material submissions. Learn more about how to write a policy document and examples of policy documents in [Set up policy documents for the Approvals Agent](approvals-agent-policy.md). In addition to these org-wide policy documents, you can attach time, expense, and material policy documents to an individual project. When a project has a policy document for an entry type, the agent uses that project's policy document to classify records of that type instead of the org-wide policy document. Learn more in [Set up project level policy documents for the Approvals Agent](approvals-agent-project-policy.md). If no policy document is available for a specific type of record, either on the project or at the org-wide level, the agent doesn't classify approval records of that type.

You can also use the menu to set the mode of the agent to either **Classify** or **Classify and auto approve**. In **Classify** mode, the project manager must manually approve records that are marked as **Ready for approval**. In **Classify and auto approve** mode, the agent automatically processes records that are marked as **Ready for approval** for approval.

> [!NOTE]
> Test the agent thoroughly before you use it in **Classify and auto approve** mode.

You can also control which projects the agent reviews. On each project, the **Use approvals agent to review entries** flag determines whether the agent receives time, expense, and material entries linked to that project for classification. To set the default for newly created projects, use the **Automatically use approvals agent for new projects** option on the **Project Parameters** page. This option sets the project-level flag to **Yes** or **No** when a project is created. This option lets you scope agent review to specific projects rather than applying it across every project in the environment.

## Use the Approvals Agent

When a user submits a time, expense, or material record for approval in an environment where the agent is enabled and policy documents are uploaded, the record goes into a queue for classification by the agent. For each record that the agent classifies, it creates a new record that contains its classification decision. To view the list of records that the agent classified, select **Approvals Agent** in the left pane to open the **Time entries reviewed by Agent** page.

:::image type="content" source="media/agentviewscreenshot.png" alt-text="Screenshot that shows the list of records that the agent classified on the Time entries reviewed by Agent page. It also highlights Approvals Agent in the left pane.":::

After you select a record in the grid, three buttons become available on the Action Pane:

- **Approve** – Process the selected record for approval.
- **Reject** – Reject the selected record, and send it back to the submitter. You're prompted to enter a rejection comment.
- **Reassign to Agent** – Return the selected record to the agent's queue for reevaluation. Use this button if the policy document is updated, and the record must be reviewed against the new document.

:::image type="content" source="media/agentoptions.png" alt-text="Screenshot that highlights the Approve, Reject, and Reassign to Agent buttons on the Action Pane for a record that is selected on the Time entries reviewed by Agent page.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
