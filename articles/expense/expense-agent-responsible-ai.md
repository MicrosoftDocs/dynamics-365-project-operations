---
title: Responsible AI FAQ for the Expense Entry feature of the Time and Expense Agent (preview)
description: Get answers to frequently asked questions about the AI technology used in the Expense Entry feature of the Time and Expense Agent. This FAQ includes key considerations and details about how the AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 05/13/2025
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
ms.custom:
  - responsible-ai-faqs
  - copilot-learning-hub
ms.topic: faq
author: alexeiantao
ms.author: ajitchandran
ms.reviewer: johnmichalak
---

# Responsible AI FAQ for the Expense Entry feature of the Time and Expense Agent (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

This article provides answers to frequently asked questions about the AI technology that is used in the Expense Entry feature of the Time and Expense Agent. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.

## What is the Expense Entry feature of the Time and Expense Agent?

The Expense Entry feature of the Time and Expense Agent automates expense management by processing receipts, creating expense lines, and generating reports with minimal user input. It reduces manual effort and accelerates reporting by letting users forward receipts to a shared mailbox or upload them directly into Microsoft Dynamics 365 Project Operations.

The agent extracts key details, such as the amount, merchant, and location, and groups related expenses into reports. Users can review and submit these reports via Microsoft Teams. As a result, the process is faster and more accurate.

By reducing the time that is spent on administrative tasks, the agent helps employees focus on higher-value work.

## What can the Expense Entry feature of the Time and Expense Agent do?

The Expense Entry feature of the Time and Expense Agent automates the full expense management lifecycle through intelligent workflows. It provides the following core capabilities, among others:
 
- **Receipt processing:** Users can forward receipts to a shared mailbox or upload them directly into Project Operations. The agent automatically extracts key details, such as the amount, merchant, and location. Therefore, manual data entry isn't required.
- **Expense line creation:** Based on the extracted data, the agent periodically generates individual expense lines, which are saved and tracked in the system.
- **Expense report generation:** Related expense lines are grouped into cohesive reports that are organized by project or trip. These reports follow a regular schedule that is aligned with organizational workflows.
- **User-friendly report review and submission:** Reports appear in an interactive Teams interface. There, users can review and edit the reports, attach or detach lines, and update categories. The system highlights any violations of configured expense policies. As required, users can provide justifications directly in Teams. After reports are reviewed, they can be submitted for approval. As a result, the overall cycle time is reduced.

This comprehensive functionality helps organizations improve expense efficiency, reduce manual input, and support compliance.

## What are the intended uses of the Expense Entry feature of the Time and Expense Agent?

The Expense Entry feature of the Time and Expense Agent is designed for the following uses:

- **Automate expense data entry:** Automatically process receipts and invoices to reduce manual input and improve speed and accuracy.
- **Facilitate report creation:** Logically group related expenses into project-based or trip-based reports to simplify submission.
- **Enhance productivity:** Streamline repetitive tasks to free up employee time and enable greater focus on strategic responsibilities.

## How was the Expense Entry feature of the Time and Expense Agent evaluated? What metrics are used to measure performance?

- The system was evaluated through repeated automated and manual testing. The tests measured the accuracy of generated outputs by comparing them to expected results.
- A red-teaming process assessed risks and potential harms to ensure that responses are grounded and reliable.
- The system underwent rigorous internal assessments that were aligned with Microsoft's Responsible AI standards. These assessments covered areas such as security, privacy, legal compliance, and responsible deployment.

## What are the limitations of the Expense Entry feature of the Time and Expense Agent? How can users minimize their impact?

- **Language support:** The agent currently supports receipts in English only.
- **Need for user intervention:** Users might occasionally have to review or correct extracted data to maintain accuracy and compliance.
- **Dependence on receipt quality:** The system might not perform well if receipts are unclear or incomplete. If key information (such as the amount, merchant name, location, or currency) is missing or illegible, the receipt isn't processed, and the user is notified.
- **Automatically generated report titles and grouping:** Reports are named based on projects or trips. Users who prefer custom titles must edit them in Project Operations. The system tries to group expenses based on location. However, users can manually detach and regroup expenses as required.
- **Category mismatches:** The system suggests categories based on best-fit logic. Users can adjust categories in Teams or directly in Project Operations before submission.

## What operational settings enable effective and responsible use of the Expense Entry feature of the Time and Expense Agent?

- Admins can enable or disable the feature via feature control settings. They can also configure whether expenses are grouped by project or trip, and set the notification frequency for unsubmitted reports.
- If issues arise with the system output, admins can immediately disable the feature by using the same feature control settings.
- The system flags any expenses that violate configured organizational policies. If a policy prohibits submission of noncompliant expenses, users must detach those expenses before submission.
- The agent's functionality was reviewed in accordance with Microsoft's Responsible AI principles. If submitted inputs fall outside acceptable boundaries, the agent might skip processing and notify the user accordingly.

## How do I provide feedback about the Expense Entry feature of the Time and Expense Agent?

- Users can provide quick feedback by using the thumbs-up and thumbs-down options in Teams.
- General feedback can also be shared through the Teams channel for Project Operations or by submitting a support request.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
