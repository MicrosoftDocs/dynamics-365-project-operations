---
title: Approvals feature of the Time and Expense Agent overview (preview)
description: Get a brief introduction to the Approvals feature of the Time and Expense Agent.
author: abriccetti
ms.date: 05/13/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Approvals feature of the Time and Expense Agent overview (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

The purpose of the Approvals feature of the Time and Expense Agent is to streamline the approval process for time, expense, and material transactions. The Time and Expense Agent uses a [Microsoft Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) agent to do an initial review of incoming time, expense, and material entries against policy documents that the customer uploaded for each type of entry. If a record meets the criteria that are outlined in the policy document, it's marked as **Ready for approval**. Otherwise, it's marked as **Needs review**. This initial review makes the approval process more efficient for project managers. It also helps them avoid time-consuming corrections by reducing mistaken approvals.

## Set up the Approvals feature of the Time and Expense Agent

An admin must enable and set up the Approvals feature of the Time and Expense Agent by following the steps in [Set up the Approvals feature of the Time and Expense Agent as an admin](approvals-agent-admin-setup.md). After the feature is correctly set up, enable the agent by selecting **Enable Time and Expense Agent** in the **Feature Control** field on the **Project Parameters** page.

After the agent is enabled, a new **Time and Expense Agent** tab appears on the **Project Parameters** page. Use this tab to upload policy documents for time, expense, and material submissions. Learn more about how to write a policy document, and get some examples of policy documents, in [Set up policy documents for the Approvals feature of the Time and Expense Agent](approvals-agent-policy.md). If a policy document isn't available for a specific type of record, the agent doesn't classify approval records of that type.

Additionally, you can use the menu to set the mode of the agent to either **Classify** or **Classify and auto approve**. In **Classify** mode, records that are marked as **Ready for approval** must be manually approved by the project manager. In **Classify and auto approve** mode, records that are marked as **Ready for approval** are automatically processed for approval.

> [!NOTE]
> We recommend that you do rigorous testing before you use the agent in **Classify and auto approve** mode.

## Use the Approvals feature of the Time and Expense Agent

When a user submits a time, expense, or material record for approval in an environment where the agent is enabled and policy documents were uploaded, the record goes into a queue for classification by the agent. For each record that the agent classifies, it creates a new record that contains its classification decision. To view the list of records that the agent classified, select **Approvals Agent** in the left pane to open the **Time entries reviewed by Agent** page.

![Screenshot that shows the list of records that the agent classified on the Time entries reviewed by Agent page. It also highlights Approvals Agent in the left pane.](media/agentviewscreenshot.png)

After you select a record in the grid, three buttons become available on the Action Pane:

- **Approve** – Process the selected record for approval.
- **Reject** – Reject the selected record, and send it back to the submitter. You're prompted to enter a rejection comment.
- **Reassign to Agent** – Return the selected record to the agent's queue for reevaluation. Use this button if the policy document is updated, and the record must be reviewed against the new document.

![Screenshot that highlights the Approve, Reject, and Reassign to Agent buttons on the Action Pane for a record that is selected on the Time entries reviewed by Agent page.](media/agentoptions.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
