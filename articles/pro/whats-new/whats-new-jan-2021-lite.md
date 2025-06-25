---
title: What's new January 2021 - Project Operations lite deployment
description: This article provides information about the quality updates available in the January 2021 release of Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new January 2021 - Project Operations lite deployment


_Applies To: Core deployment - deal to proforma invoicing_

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.6.0.154.
  
## Quality updates

| **Feature area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Deployment and Configuration** | 2106818 | Fixed the webresource rename that was causing issues related to customizing a page. |
| **Billing and Pricing** | 2091908 | Fixed the visibility of the **Lock pricing** and **Use Current Pricing** options on the **Invoice** page when Project Operations is installed together with Dynamics 365 Field Service. |
| **Billing and Pricing** | 2103058 | Refreshed **Project Totals** to handle null values for the actual cost on a task. |
| **Billing and Pricing** | 2116100 | Improved error messages used with the functionality, **Correct Entries on Actuals**. |
| **Billing and Pricing** | 2116129 | Improved expense estimates visibility on the **Estimates** tab on the **Projects** page. |
| **Billing and Pricing** | 2119112 | Fixed aggregation of actual sales and actual cost when different exchange rates are used. |
| **Billing and Pricing** | 2134705 | Fixed the error, "Cannot read property **getResourceString** of undefined" when the **Invoice** page is opened and Field Service is installed. |
| **Opportunity Management** | 2022195 | The task-based billing grid on the **Project** page includes an icon indicating that there is a contract or quote line linked to that task. |
| **Opportunity Management** | 2029135 | Fixed the business process error that occurs when a user tries to open an invoice line on a confirmed invoice that has an advance amount invoiced. |
| **Opportunity Management** | 2040713 | Fixed the script error that occurs when creating an invoice from a contract and Field Service is installed. |
| **Project Planning and Tracking** | 2090202 | Marked business rules that are no longer used as **Deprecated**. |
| **Time and Expense** | 2091249 | Tightened controls so that users can't change the task on a submitted or approved time entry. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
