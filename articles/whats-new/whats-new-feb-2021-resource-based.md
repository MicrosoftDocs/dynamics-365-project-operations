---
title: What's new February 2021 - Project Operations Integrated with ERP
description: This article provides information about the quality updates available in the February 2021 release of Project Operations Integrated with ERP.
author: sigitac
ms.custom:
  - evergreen
ms.date: 07/07/2025
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new February 2021 - Project Operations Integrated with ERP

_**Applies To:** Project Operations Integrated with ERP_

This article applies to the following Dynamics 365 Project Operations components and versions:

- Project Operations on Dataverse environment 4.7.0.95
- Project management and accounting in Dynamics 365 Finance environment version 10.0.16 

## Quality updates

### Project Operations on Dataverse

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Billing and Pricing** | 2053736 | Invoice line details are now accessible by going to **Invoice** > **Related information**. |
| **Billing and Pricing** | 2122613 | The **Activate** and **Deactivate** actions were removed from the **Price List** association entities. |
| **Billing and Pricing** | 2128606 | Resolved the issue with **ullReferenceException** in the **GetEstimatesForProject** plug-in. |
| **Deployment and configuration** | 2139346 | Resolved the issue with importing unmanaged **Dynamics365ProjectOperationsDualWrite** solution. |
| **Deployment and configuration** | 2140569 | Project solution must not be installed in the Dataverse Teams environments. |
| **Deployment and configuration** | 2086991 | Restricted customizing localization of web resources. |
| **Opportunity Management** | 2136794 | Display the correct error message when the **Confirm invoice** or **Mark invoice as paid** processes fail. |
| **Opportunity Management** | 2139330 | Changing the Project manager on a project must not reset the owning company back to the default value. |
| **Opportunity Management** | 2146376 | Corrected tax amount in a non-chargeable actual is created from invoice confirmation. |
| **Project Planning and Tracking** | 2099879 | The Dataverse environment deployment must create a default transaction category with a static ID and not randomly generate one per environment. |
| **Project Planning and Tracking** | 2128577 | Fixed the Project service user privileges to update the transaction category on a resource assignment. |
| **Project Planning and Tracking** | 2164035 | Fixed issues with the **Copy Project** function. |
| **Time entry** | 2129161 | Tighter restrictions are applied to ensure users can't change and update a time entry that has been submitted or approved. |
| **Time entry** | 2103572 | Time approval for non-project time entries must not be looking for project approver role. |

### Project management and accounting in Dynamics 365 Finance 

For more information about Project management and accounting in Dynamics 365 Finance, see [What's new January 2021 - Project Operations Integrated with ERP](whats-new-jan-2021-resource-based.md).


## Regulatory updates

For information about regulatory updates for finance and operations apps, see [Regulatory updates](/dynamics365/finance/localizations/regulatory-updates). Another way to learn about regulatory updates is to sign in to Lifecycle Services (LCS) and view the planned regulatory updates using the issue search tool. Issue search lets you search by country/region, type of feature, and release.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
