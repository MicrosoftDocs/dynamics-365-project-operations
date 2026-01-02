---
title: Configuration of the Expense Agent (Preview)  
description: Learn about Expense Agent and its functionality
author: ajitchandran
ms.author: ajitchandran
ms.date: 01/02/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense Agent overview (Preview) 

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE[banner](../includes/preview-note.md)]

_**Applies to Dynamics 365 Project Operations Integrated with ERP and Dynamics 365 Project Operations for manufacturing**_ 

> [!NOTE]
> Community interest groups have now moved from Yammer to Microsoft Viva Engage. To join the Expense Management Viva Engage community and take part in the latest discussions, click [**here**](https://engage.cloud.microsoft/main/org/microsoft.com/groups/eyJfdHlwZSI6Ikdyb3VwIiwiaWQiOiIyMzc5MzM4OTU2ODAifQ) and request for access.

> [!IMPORTANT]
> - This is a production-ready preview feature.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520) 
 
You can configure the Expense Agent using certain parameters based on the need in the organization.

## Expense Agent Configuration
To setup the parameters for the Expense Agent, you need to go to Expense Management > Setup > General > Expense Management parameters >  (Production ready preview) Expense Agent. These parameters are legal entity specific.

<img width="1910" height="902" alt="image" src="https://github.com/user-attachments/assets/98641d39-8d59-4111-b18b-4acd731a336c" />

- **Enable Expense Agent:** This setting allows administrators to enable the Expense Agent for the selected legal entity. When enabled, the Expense Agent becomes available to users in the selected legal entity
- **Maximum days for expense match:** Enter the number of days the Expense Agent should look back when matching receipts to transactions. The value must be between 1 and 90. For example, if you set this to 7, the Expense Agent will consider only receipts (images or files) uploaded in the last 7 days for expense line creation and Auto‑Match. Any receipts older than this period will be ignored.
- **Disable expense report creation:** Enable this option to prevent the Expense Agent from creating expense reports. When enabled, expenses will not be grouped into an expense report and will remain as individual expense entries.
- **Frequency:** Specify how often the Expense Agent should run to create or update expense reports. You can choose Daily or Weekly. For weekly runs, select the day(s) of the week on which the agent should process expense reports using the Days field.
- **Group reports by:** Enter the criteria by which the Expense Agent should group the expenses. It could be based on Project or Trip.
- **Auto-match receipts:** Enable this option if you want the Expense Agent to auto-match receipts with the credit card transactions uploaded into the system.
- **Confidence score threshold:** Set the minimum confidence score required for teh expenes agent to auto-match receipts to expense lines. Value must be between 1 to 100.
- **Enable itemization:** Enable this option to allow the expense agent to automatically itemize receipts for all the supported expense categories.
- **Itemize tax separately:** Enable this option if you want to the expense agent to consolidate all tax itemizations into a single specified subcategory.
    - Once enabled, you can also set the single subcategory as part of the Expense Category setup.
    - Go to Expense Management > Setup > General > Expense Management parameters > Setup > General > Expense categories >
Select the expense category > Expense > Default tax subcategory > Choose the subcategory
- **Enable Teams Notifications:** Enable this option if you want the expense agent to send notifications to users through Microsoft Teams.
## Related Information
- [Expense Agent overview](https://learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-setup)
- Expense Agent Configuration
- [Installation and Setup of the Expense Agent](https://learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-setup)
- [Expense Agent FAQs](https://learn.microsoft.com/en-us/dynamics365/project-operations/expense/expense-agent-faq)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
