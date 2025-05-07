---
title: Approvals Agent Into (Production Ready Preview)
description: This article gives a brief introduction to the Project Operations Approvals Agent.
author: abriccetti
ms.date: 04/17/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Approvals Agent (Production Ready Preview) Overview

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

The Approvals Agent aims to streamline the approval process for time, expense, and material transactions, using a [Microsoft Copilot Studio](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio) Agent to provide an initial review of incoming time, expense, and material entries against customer uploaded policy documents for each type of entry. If the record is found to meet the criteria outlined in the policy document, it is marked as **ready for approval** and if not it is marked as **needs review**. This streamlines the approvals process for project managers while also reducing mistaken approvals which can lead to time consuming corrections.

This production ready preview is available to be installed in both sandbox and production environments, however, we recommend only using the agent in production environments after thorough testing.

## Approvals Agent Overview

### Setup

The Approvals Agent requires a few steps to be enabled and correctly setup. Please review [Approvals Agent Admin Setup](./approvals-agent-admin-setup) for the appropriate steps for admin setup. Once these have been completed the agent can be enabled by selecting **Enable Time and Expense Agent (Production Ready Preview)** in the feature control menu on the project parameters form.

Once the feature is enabled, a new tab appears in the Project Parameters form named **Time and Expense Agent (Production Ready Preview)**. Here the user can upload their policy documents for time, expense, and material submissions. For guidance on writing a policy document and examples refer to [Approvals Agent Policy Documents](./approvals-agent-policy). If a policy document isn't available for a certain type of record, then approval records of that type aren't classified by the agent.

Additionally, in this menu you can set the mode of the agent to either **Classify** or **Classify and auto approve**. In the **Classify** mode, records marked as **ready for approval** still needs to be manually approved by the PM, however, in the **Classify and auto approve** mode entries which are classified as **ready for approval** are automatically processed for approval. 

> [!NOTE]
> Rigorous testing is recommended before enabling the **Classify and auto approve** mode

### Using the Approvals Agent

When a time, material, or expense record is submitted for approval in an environment with the agent enabled and policy documents uploaded, it goes into a queue for classification by the agent. Once the agent classifies the submission, it creates a new record containing its classification decision which can be viewed by selecting the **Approvals Agent (Production Ready Preview)** view on the left area selector.

![View of records the agent has classified](media/agentviewscreenshot.png)

When a record is selected in this view the user are shown three options on the ribbon: 

1. Approve - The record ise processed for approval
1. Reject - The user is prompted for a rejection comment, then the record is rejected and sent back to the submitter
1. Reassign to Agent - The record is returned to the agent's queue and reevaluated (this is designed to be used when the policy document is updated and the record needs to be reviewed using the new document)

![Options when a record is selected](media/agentoptions.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
