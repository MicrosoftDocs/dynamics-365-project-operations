---
title: Expense Agent overview (Preview)
description: Get an overview of the Expense Agent.
author: ajitchandran
ms.author: ajitchandran
ms.date: 06/08/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense Agent overview (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

This article provides an overview of the Expense Agent. This feature simplifies and automates the process of managing employee or worker expenses in an organization. It reduces manual effort by processing receipts, creating expense lines, and generating expense reports with minimal user intervention.

The agent streamlines the workflow by letting users forward receipts to a designated mailbox. It then extracts key details, such as the amount, merchant, and location, and groups related expenses into comprehensive reports. Users can review, edit, and submit those reports through Microsoft Teams. As a result, the process is more efficient and accurate. The agent also processes receipts that are uploaded directly into finance and operations apps.

By minimizing the time that is spent on administrative tasks, the Expense Agent lets users focus on higher-value activities and improves the overall expense reporting experience.

## Functionality

The Expense Agent automates the end-to-end expense management process by using intelligent workflows to handle receipt processing, expense line creation, and report generation. It provides the following capabilities:

- **Receipt processing:** Users can forward receipts to a shared mailbox or upload them directly into finance and operations apps. The system automatically extracts key details, such as the amount, merchant, and location. Therefore, manual data entry isn't required.
- **Expense line creation:** Based on the extracted details, the agent periodically creates individual expense lines. The system stores and tracks those lines to facilitate reliable and consistent expense management.
- **Expense report generation:** The system groups related expense lines into reports and logically organizes them by project or trip. The reports are generated on a regular schedule that is aligned with organizational workflows. If users share their work calendar with the shared mailbox, the agent can use calendar data to identify relevant trips or projects.
- **User-friendly report review and submission:** Generated reports appear in an interactive Teams interface, where users can review or update details. Users can seamlessly perform actions such as attaching or detaching expense lines and updating categories. The system notifies users if any expenses violate organizational policies that are configured in finance and operations apps. Users can also submit reports for approval through Teams. Alternatively, they can select **Open in Expense** to edit and submit reports directly in finance and operations apps.
- **Flexible configuration:** In Expense Management parameters, administrators can configure the frequency of report generation and select the grouping logic (by trip or by project). Here are some examples:

    - If employees typically tag expenses to projects, the agent analyzes active projects and assigns expenses accordingly.
    - If expenses are incurred during work-related trips, the agent groups them based on location data, such as the city or country.

- **Monitoring of agent workflows:** Administrators can use Power Apps to track the status of individual workflows. In this way, they can monitor performance and gain insights into usage. To access the app, open **Expense Agent Workflow** in Power Apps.

## Known limitations

Although the Expense Agent simplifies many aspects of expense management, be aware of the following limitations:

- **Manual intervention might be required.** Although the agent reduces effort, users might have to verify or correct extracted data to ensure accuracy and compliance.
- **Performance depends on receipt quality.** The system might have difficulty with poor-quality receipts. Receipts that are illegible or missing important details (for example, the amount, merchant name, location, or currency) might not be processed. In these cases, users are notified.
- **Automatically generated report titles might need adjustment.** Report titles are generated based on associated trips or projects. Users who prefer custom naming can edit titles directly in finance and operations apps. In addition, although the agent groups expenses by location (for example, by city or country), users can detach and reorganize expenses if the grouping is unsatisfactory.
- **Category suggestions might need adjustment.** The agent maps expenses to predefined categories (for example, **Flight**, **Meal**, or **Car Rental**) based on the best match. If the selected category isn't appropriate, users can update it in Teams or finance and operations apps before submission.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
