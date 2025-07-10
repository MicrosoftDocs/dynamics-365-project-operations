---
title: Responsible AI FAQ for the Approvals feature of the Time and Expense Agent (preview)
description: Get answers to frequently asked questions about the Approvals feature of the Time and Expense Agent.
author: abriccetti
ms.author: abriccetti
ms.topic: conceptual 
ms.date: 05/13/2025
ms.update-cycle: 180-days
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.collection:
  - bap-ai-copilot
---


# Responsible AI FAQ for the Approvals feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

### What is the Approvals feature of the Time and Expense Agent?

The Approvals feature of the Time and Expense Agent in Microsoft Dynamics 365 Project Operations helps project managers by doing an initial review of all time, expense, and material entries that are submitted. To do this review, the agent uses a combination of business logic and large language models (LLMs) to evaluate each entry against the organization's policy documents.

If the agent finds no policy violations, based on its interpretation of the relevant policy document and review outcomes, it determines that the entry has low risk and classifies it as ready for approval. If the agent finds one or more policy violations, it determines that the entry has high risk, classifies it as needing human review, and provides a reason why review is needed.

The Approvals feature of the Time and Expense Agent helps reduce the project manager's workload at the close of the invoice period. Without this feature, the project manager might have to manually review hundreds of approvals and send them for invoicing. At the same time, they might have to help proactively identify issues that will require invoice corrections later.

### What can the Approvals feature of the Time and Expense Agent do?

The Approvals feature of the Time and Expense Agent uses Microsoft Copilot Studio to offer the following capabilities:

- Provide an initial review of all submitted time and expense approvals, and suggest which ones required further review.
- Allow for automatic approval of low-risk transactions.
- Provides insight to help approvers make accurate decisions, and offer recommendations for addressing high-risk transactions.

### What are the intended uses of the Approvals feature of the Time and Expense Agent?

The Approvals feature of the Time and Expense Agent has the following intended uses:

- Help classify transactions as high-risk or low-risk. Assign a status of **Ready for approval** to transactions that have no policy violations or a status of **Needs review** to transactions that have one or more policy violations.
- Evaluate each transaction against the relevant time, expense, or material policy document that is uploaded, and generate a justification when transactions are classified as requiring review.
- Enable tracking of the agent's impact on business metrics and user productivity.

### How was the Approvals feature of the Time and Expense Agent evaluated? What metrics are used to measure performance?

- The system was evaluated multiple times through both automated tests and manual reviews that measured the accuracy of the system-generated review status and justification for each approval record. Accuracy was measured through comparison against the policy document that was used for evaluation.
- In addition, the content that the system generated was evaluated through a red-teaming process that tested for groundedness and various kinds of harm.
- Our priority is to ensure that the agent is developed according to [Microsoft's Responsible AI standards](https://aka.ms/RAIStandardPDF). Therefore, the system is deployed to users only after we complete a rigorous assessment process. This process spans a range of areas, such as security, privacy, and legal.

### What are the limitations of Approvals feature of the Time and Expense Agent? How can users minimize the impact of those limitations when they use the system?

- The accuracy of the output varies widely, depending on the quality of the input (that is, the policy documents). Therefore, the policy documents must be carefully crafted. The system might not perform well if the policy documents include ambiguous approval criteria or conflicting policies.
- The classification and justification that the agent generates can vary, depending on the quality of data in the submitted time, expense, or material entries, and the specific use case.

The following steps can help mitigate the preceding issues:

- Admins should run preliminary tests in Copilot Studio. For those tests, they should use the policy document that they intend to use in their environment and gauge whether the results meet their expectations.
- In some cases, users might have to adjust the language that is used in the policy documents to improve the accuracy of the output (that is, the review status and justification that the agent generates).
- Users should avoid creating conflicting policies in the documents. Otherwise, the agent can become "confused."
- Although two modes of classification are supported, we recommend that you use **Classify** mode only during configuration, to prevent automatic approval of **Ready for approval** transactions.

### What operational factors and settings allow for effective and responsible use of the Approvals feature of the Time and Expense Agent?

- Admins can enable the feature by using feature control settings. The feature allows for automatic submission of time entries on behalf of team members. It also provides insights into submitted time, expense, and material entries, so that project managers can make informed approval decisions.
- If any issues with the system output are ever noticed, admins can disable the feature by using feature control settings.
- If the feature is enabled, only record types that a policy document is uploaded for are reviewed. For example, if only a time policy document is uploaded, the agent reviews only time entries.
- If no policy documents are uploaded, no records are reviewed.
- The functioning of the agent was reviewed in accordance with Responsible AI policies. If the inputs that the agent receives (submitted entries and policy documents) are evaluated as being outside the boundaries of Responsible AI, the agent is likely to flag them for further human review.

### How do I provide feedback about the Approvals feature of the Time and Expense Agent?

- During the production ready preview of the Approvals feature, users can provide thumbs-up or thumbs-down feedback about any reviewed record.
- This feedback mechanism might be enhanced later through an option that lets users provide more detailed feedback directly in the product.
- General feedback about the feature can be shared through the existing Teams channel for Dynamics 365 Project Operations channel or via support requests.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
