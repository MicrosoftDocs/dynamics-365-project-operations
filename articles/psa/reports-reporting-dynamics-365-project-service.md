---
title: Reporting home page
description: This article provides information about reporting in Dynamics 365 Project Service Automation.
author: tulsij
ms.author: tulsijhaveri
ms.custom: 
  - dyn365-projectservice
  - bap-template
  - evergreen
ms.date: 07/07/2025
ms.topic: concept-article
ms.reviewer: johnmichalak
---

# Reporting home page

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-3.x](../includes/cc-applies-to-psa-app-3x.md)]

Microsoft Dynamics 365 Project Service Automation lets project-based organizations efficiently manage the operations of their business. On any project, team members must manage the opportunity, quote and plan the work, resource the projects, manage the work according to the plan, bill for the work, and then do the work to complete the project. The ability to report on operations is key to determining the health of the organization and taking any corrective action that's required. PSA uses Microsoft Dynamics 365 reporting methods and technologies for all its reporting. For more information about the options for reporting, see the [Report writing guide for Dynamics 365 Customer Engagement (on-premises), version 9](/dynamics365/customerengagement/on-premises/analytics/reporting-analytics-with-dynamics-365).

## Report Wizard

The Report Wizard lets non-developers create simple reports. Because the app is built on an existing platform, the experience is the same as the experience that is documented in [Create or edit a report using the Report Wizard](/dynamics365/customerengagement/on-premises/basics/create-edit-copy-report-wizard). However, you will use the Project Service Automation-specific entities.

## Custom SQL Server Reporting Services reports

If your business requires a specific report that can't be created by using the Report Wizard, you can create a custom report. You must have Microsoft Visual Studio installed, together with the appropriate Microsoft SQL Server Data Tools and Report Authoring Extensions. For more information about tools and versions, see [Report writing environment using SQL Server Data Tools](/dynamics365/customerengagement/on-premises/analytics/report-writing-environment-using-sql-server-data-tools). For information about how to create a custom report, see [Create a new report using SQL Server Data Tools](/dynamics365/customerengagement/on-premises/analytics/create-a-new-report-using-sql-server-data-tools).

## Power BI insights apps

Together, Microsoft Power BI and Dynamics 365 give you a powerful way to work with your data, in the form of insights apps. For information about the availability of insights apps, see the [Power BI insights apps page](https://powerbi.microsoft.com/power-bi-insights-apps/).


## Additional resources
For more information about reporting in PSA, see the following articles:

- [Working with the Project Service data model](reports-working-project-service-data-model.md)
- [Dashboards](reports-dashboards.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
