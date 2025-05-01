---
title: Responsible AI FAQ for Expense Agent
description: This FAQ provides answers to frequently asked questions about the AI technology that's used in the Expense Agent. It includes key considerations and details about how the AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 04/30/2025
ms.collection:
  - bap-ai-copilot
ms.custom:
  - responsible-ai-faqs
  - copilot-learning-hub
ms.topic: faq
author: alexeiantao
ms.author: alexeiantao
ms.reviewer: johnmichalak
---

# Responsible AI FAQ for Expense Agent

[!INCLUDE[banner](../includes/banner.md)]

This FAQ provides answers to frequently asked questions about the AI technology that's used in the Expense Agent feature. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.

## What is the Expense Entry Agent?

The Dynamics 365 Expense Entry Agent automates expense management by processing receipts, creating expense lines, and generating reports with minimal user input. It reduces manual effort and accelerates reporting by allowing users to forward receipts to a shared mailbox or upload them directly to Dynamics 365 Project Operations.

The agent extracts key details—such as amount, merchant, and location—and groups related expenses into reports. Users can review and submit these reports via Microsoft Teams, making the process faster and more accurate.

By reducing time spent on administrative tasks, the agent helps employees focus on higher-value work.


## What can the Expense Entry Agent do?

The Expense Entry Agent automates the full expense management lifecycle using intelligent workflows. Its core capabilities include:

- **Receipt Processing:**  
  Users can forward receipts to a shared mailbox or upload them into Dynamics 365 Project Operations. The agent automatically extracts key details such as amount, merchant, and location—eliminating manual data entry.

- **Expense Line Creation:**  
  Based on the extracted data, the agent periodically generates individual expense lines, which are saved and tracked within the system.

- **Expense Report Generation:**  
  Related expense lines are grouped into cohesive reports, organized by project or trip. These reports follow a scheduled cadence aligned with organizational workflows.

- **User-Friendly Review and Submission:**  
  Reports are displayed in an interactive Teams interface, where users can review, edit, attach or detach lines, and update categories. The system highlights any violations of configured expense policies. If required, users can provide justifications directly in Teams. Once reviewed, reports can be submitted for approval, helping reduce the overall cycle time.

This comprehensive functionality helps organizations improve expense efficiency, reduce manual input, and support compliance.

## What are the intended uses of the Expense Entry Agent?

The Expense Entry Agent is designed to:

- **Automate expense data entry:**  
  Automatically process receipts and invoices to reduce manual input and improve speed and accuracy.

- **Facilitate report creation:**  
  Logically group related expenses into project- or trip-based reports, simplifying submission.

- **Enhance productivity:**  
  Free up employee time by streamlining repetitive tasks, enabling greater focus on strategic responsibilities.

## How was the Expense Entry Agent evaluated? What metrics are used to measure performance?

- The system was evaluated through repeated automated and manual testing to compare generated outputs with expected results for accuracy.

- A red-teaming process was conducted to assess risks and potential harms, ensuring that responses are grounded and reliable.

- The system underwent rigorous internal assessments aligned with Microsoft’s Responsible AI standards. These assessments cover areas such as security, privacy, legal compliance, and responsible deployment.


## What are the limitations of the Expense Entry Agent? How can users minimize their impact?

- **Language support:**  
  The agent currently supports receipts in English only.

- **Need for user intervention:**  
  Users may occasionally need to review or correct extracted data to maintain accuracy and compliance.

- **Dependence on receipt quality:**  
  The system may not perform well with unclear or incomplete receipts. If key information—such as amount, merchant name, location, or currency—is missing or illegible, the receipt won't process, and the user is notified.

- **Auto-generated report titles and grouping:**  
  Reports are named based on projects or trips. Users who prefer custom titles must edit them in Project Operations. The system attempts to group expenses based on location; however, users can manually detach and regroup expenses as needed.

- **Category mismatches:**  
  The system suggests categories based on best-fit logic. Users can adjust categories in Teams or directly within Project Operations before submitting.


## What operational settings enable effective and responsible use of the Expense Entry Agent?

- Admins can enable or disable the feature via feature control settings. They can also configure whether expenses are grouped by project or trip and set the notification frequency for unsubmitted reports.

- If issues arise with the system output, admins can immediately disable the feature using the same control settings.

- The system flags any expenses that violate configured organizational policies. If a policy prohibits submission of non-compliant expenses, users are required to detach those expenses before submitting.

- The agent’s functionality was reviewed in accordance with Microsoft’s Responsible AI principles. If submitted inputs fall outside acceptable boundaries, the agent may skip processing and notify the user accordingly.

---

## How do I provide feedback on the Expense Entry Agent?

- Users can provide quick feedback using the thumbs-up/thumbs-down option within Teams.

- General feedback can also be shared through the Project Operations Teams channel or by submitting a support request.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
