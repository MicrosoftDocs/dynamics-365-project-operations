---
title: Expense Entry feature of the Time and Expense Agent overview (preview)
description: This article provides an overview of the Expense Entry feature of the Time and Expense Agent.
author: alexeiantao
ms.author: alexeiantao
ms.date: 05/09/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense Entry feature of the Time and Expense Agent overview (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

This article provides an overview of the Expense Entry feature of the Time and Expense Agent. The Expense Entry feature of the Time and Expense Agent simplifies and automates the process of managing employee or worker expenses within an organization. It reduces manual effort by processing receipts, generating expense lines, and creating expense reports with minimal user intervention.

The agent streamlines the workflow by allowing users to forward receipts to a designated mailbox. It extracts key details such as amount, merchant, and location, and groups related expenses into comprehensive reports. Users can review, edit, and submit these reports through Microsoft Teams, improving both efficiency and accuracy. The agent also processes receipts uploaded directly into the finance and operations apps.

By minimizing time spent on administrative tasks, the Expense Entry feature of the Time and Expense Agent enables users to focus on higher-value activities and improves the overall expense reporting experience.

## Functionality

The Expense Entry feature of the Time and Expense Agent automates the end-to-end expense management process by using intelligent workflows to handle receipt processing, expense line creation, and report generation. It provides the following capabilities:

- **Receipt Processing:**  
  Users can forward receipts to a shared mailbox or upload them directly into finance and operations apps. The system automatically extracts key details such as amount, merchant, and location, eliminating the need for manual data entry.

- **Expense Line Creation:**  
  Based on the extracted details, the agent periodically generates individual expense lines that are stored and tracked in the system to contribute to reliable and consistent expense management.

- **Expense Report Generation:**  
  The system groups related expense lines into reports, organizing them logically by project or trip. These reports are created on a regular schedule aligned with organizational workflows. Users can also share their work calendars with the shared mailbox, allowing the agent to use calendar data to identify relevant trips or projects.

- **User-Friendly Review and Submission:**  
  Generated reports appear in an interactive Teams interface, where users can review, modify, or update details. Actions such as attaching or detaching expense lines and updating categories can be performed seamlessly. The system also notifies users of any expenses that violate organizational policies configured in finance and operations apps. Users can submit reports for approval through Teams or choose the **Open in Expense** option to edit and submit directly in finance and operations apps.

- **Flexible Configuration:**  
  Administrators can configure report generation frequency and choose grouping logic (by trip or by project) in the Expense Management Parameters.  
  For example:  
  - If employees typically tag expenses to projects, the agent analyzes active projects and assigns expenses accordingly.  
  - If expenses are incurred on work-related trips, the agent groups them based on location data such as city or country.

- **Monitoring Agent Workflows:**  
  Administrators can track the status of individual workflows using Microsoft Power Apps. This helps monitor performance and gain insights into usage. To access the app, open **Expense Agent Workflow** in Power Apps.

## Known Limitations

While the Expense Entry feature of the Time and Expense Agent simplifies many aspects of expense management, the following limitations should be considered:

- **Manual intervention may be required:**  
  Although the agent reduces effort, users may need to verify or correct extracted data to ensure accuracy and compliance.

- **Performance depends on receipt quality:**  
  The system may struggle with poor-quality receipts. If receipts are illegible or missing key details (amount, merchant name, location, or currency), they may not be processed. In such cases, users are notified.

- **Auto-generated report titles:**  
  Report titles are created based on associated trips or projects. Users who prefer custom naming can edit titles directly within Dynamics 365 Finance and Operations. Additionally, while the agent groups expenses by location (for example, city or country), users can detach and reorganize expenses if the grouping is unsatisfactory.

- **Category suggestions may need adjustment:**  
  The agent maps expenses to predefined categories (for example, Flight, Meal, Car Rental) based on best match. If the selected category isn’t appropriate, users can update it in Teams or Finance and Operations before submission.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
