---
title: Expense Agent overview (Preview)
description: Get an overview of the Expense Agent.
author: ajitchandran
ms.author: ajitchandran
ms.date: 01/05/2026
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense Agent overview (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_

> [!NOTE]
> Community interest groups have now moved from Yammer to Microsoft Viva Engage. To join the Expense Management Viva Engage community and take part in the latest discussions, visit [https://engage.cloud.microsoft/main/org/microsoft.com/groups/eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiIyMzc5MzM4OTU2ODAifQ](https://engage.cloud.microsoft/main/org/microsoft.com/groups/eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiIyMzc5MzM4OTU2ODAifQ) and request for access.

> [!IMPORTANT]
>
> - This feature is a production-ready preview.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

Expense reporting is one of the most frequent – and often most frustrating – tasks for employees and finance teams. Despite its importance, the process remains largely manual and error‑prone, relying on users to correctly interpret receipts, enter data, and understand policies. The result is lost productivity, delays, rework, and low adoption of expense systems.
At the same time, employees have grown accustomed to AI‑assisted experiences in their daily work. Tools for search, collaboration, and productivity already anticipate intent and minimize manual effort. Expense management should be no different.

Traditional expense processes place a heavy burden on users – manually extracting details from receipts, completing multiple fields, choosing the right categories and descriptions, and navigating policies without context. Too often, employees spend more time correcting expenses than submitting them.
Expense Agent changes this experience. By understanding receipts, inferring key details, and guiding users through expense creation, Expense Agent helps ensure expenses are completed accurately the first time.
Powered by AI, Expense Agent brings intuitive, guided assistance into expense reporting – reducing effort, improving accuracy, and simplifying the end‑to‑end experience. It allows employees to focus on their work while finance teams benefit from cleaner, more compliant expense data.

## Functionality

The Expense Agent automates the end-to-end expense management process by using intelligent workflows to handle receipt processing, expense line creation, and report generation. It provides the following capabilities:

### 1. Receipt Processing

Expense Agent supports multiple ways to upload receipts, allowing users to capture expenses from wherever they work. Once receipts are uploaded, the agent processes them and creates expense lines automatically.

#### 1. Outlook (Shared Mailbox)

Employees can simply forward receipts to a designated shared mailbox. The Expense Agent monitors the inbox, extracts key details such as merchant name, date, amount, and currency, and creates expense lines that are later grouped into expense reports for review and submission.

#### 2. Expense Mobile App

Employees can capture or upload receipts using the Expense Mobile app. The agent processes these receipts by extracting relevant details and creating expense entries automatically. This entry point is ideal for on‑the‑go employees who want to submit expenses without waiting to access a laptop.

#### 3. Dynamics 365 Finance & Operations

For users working directly in Dynamics 365 Finance and Operations, Expense Agent also processes receipts uploaded within the application. When receipts are uploaded in‑app, the agent does monitor unattached receipts and convert them into expense lines, helping users complete expenses faster with minimal manual effort.

### 2. Create Expense lines from receipts

Creating expense lines from receipts is one of the most time‑consuming and error‑prone steps in expense reporting. Employees often need to manually read receipts, interpret merchant information, select the right categories, and populate multiple fields correctly. Expense Agent simplifies this process by using AI to automatically create accurate expense lines directly from receipts.

When a receipt is uploaded, Expense Agent intelligently analyzes the content of the receipt—whether it’s an image or pdf. It identifies key information such as merchant name, date, currency, total amount. Based on this understanding, Expense Agent automatically creates an expense line with the relevant fields prepopulated.

Beyond basic extraction, Expense Agent applies contextual intelligence. It infers the most appropriate expense category and also suggests descriptions.
This guided, AI‑driven approach reduces manual data entry and guesswork for employees. Expense lines are created faster, with higher accuracy, and with fewer policy violations. Employees can focus on reviewing and confirming the expense instead of building it from scratch.

### 3. Automatch expenses with receipts

Matching receipts to the correct expense entries is often a time‑consuming and error‑prone step in expense reporting. Expense Agent’s Auto‑Match functionality uses AI to intelligently associate receipts with the appropriate expense lines, reducing manual effort and improving accuracy from the start. When credit card transactions already exist in the system and employees have submitted receipts for processing, Expense Agent automatically analyzes and matches those receipts to the corresponding credit card transactions—streamlining the experience and minimizing the need for manual corrections.

### 4. Itemize expenses automatically

Itemizing expenses is one of the most time-consuming and error-prone steps in expense reporting. This step is especially challenging for receipts that include multiple line items, such as meals, hotel room costs, hotel taxes, and mixed-category purchases. Expense Agent simplifies itemization by using AI to automatically understand receipts and break them into accurate, compliant expense lines.

When you upload a receipt, Expense Agent analyzes the receipt content to identify individual items, amounts, taxes, tips, and totals. The agent intelligently creates itemized expense lines and suggests appropriate subcategories and descriptions based on company-defined categories and subcategories.

### 5. Expense report generation

The system groups related expense lines into reports and logically organizes them by project or trip. The system generates the reports on a regular schedule that aligns with organizational workflows. If users share their work calendar with the shared mailbox, the agent can use calendar data to identify relevant trips or projects.

### 6. User-friendly report review and submission

Generated reports appear in an interactive Teams interface, where users can review or update details. Users can seamlessly perform actions such as attaching or detaching expense lines and updating categories. The system notifies users if any expenses violate organizational policies that are configured in finance and operations apps. Users can also submit reports for approval through Teams. Alternatively, they can select **Open in Expense** to edit and submit reports directly in finance and operations apps.

## Known limitations

Although the Expense Agent simplifies many aspects of expense management, be aware of the following limitations:

- **Manual intervention might be required.** Although the agent reduces effort, users might need to verify or correct extracted data to ensure accuracy and compliance.
- **Performance depends on receipt quality.** The system might have difficulty with poor-quality receipts. Receipts that are illegible or missing important details (such as the amount, merchant name, location, or currency) can't be processed. In these cases, users are notified.
- **Automatically generated report titles might need adjustment.** The system generates report titles based on associated trips or projects. Users who prefer custom naming can edit titles directly in finance and operations apps. In addition, although the agent groups expenses by location (such as by city or country/region), users can detach and reorganize expenses if the grouping is unsatisfactory.
- **Category suggestions might need adjustment.** The agent maps expenses to predefined categories (such as **Flight**, **Meal**, or **Car Rental**) based on the best match. If the selected category isn't appropriate, users can update it in Teams or finance and operations apps before submission.

## Related information

- [Expense Agent overview](/dynamics365/project-operations/expense/expense-agent-setup)
- Expense Agent Configuration
- [Installation and Setup of the Expense Agent](/dynamics365/project-operations/expense/expense-agent-setup)
- [Expense Agent FAQs](/dynamics365/project-operations/expense/expense-agent-faq)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
