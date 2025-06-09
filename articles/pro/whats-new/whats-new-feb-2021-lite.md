---
title: What's new February 2021 - Project Operations lite deployment
description: This article provides information about the quality updates available in the February 2021 release of Project Operations lite deployment.
author: sigitac
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak
ms.author: sigitac
---

# What's new February 2021 - Project Operations lite deployment

This article applies to the following Dynamics 365 Project Operations components and versions:

  - Project Operations on Dataverse environment version 4.7.0.95

## Quality updates

| **Feature Area** | **Reference number** | **Quality update** |
| --- | --- | --- |
| **Billing and Pricing** | 2053736 | Invoice line details are now accessible by going to **Invoice** > **Related information**. |
| **Billing and Pricing** | 2122613 | The **Activate** and **Deactivate** actions were removed from the **Price List** association entities. |
| **Billing and Pricing** | 2128606 | Resolved the issue with **ullReferenceException** in the **GetEstimatesForProject** plug-in. |
| **Deployment and configuration** | 2140569 | Project solution must not be installed in the Dataverse Teams environments. |
| **Deployment and configuration** | 2086991 | Restricted customizing localization of web resources. |
| **Opportunity Management** | 2136794 | Display correct error message when **Confirm invoice** or **Mark invoice as paid** process fails, |
| **Opportunity Management** | 2146376 | Corrected tax amount in a non-chargeable actual is created from invoice confirmation. |
| **Project Planning and Tracking** | 2099879 | The Dataverse environment deployment must create a default transaction category with a static ID and not randomly generate one per environment. |
| **Project Planning and Tracking** | 2128577 | Fixed the Project service user privileges to update the transaction category on a resource assignment. |
| **Project Planning and Tracking** | 2164035 | Fixed issues with the **Copy Project** function. |
| **Time entry** | 2129161 | Tighter restrictions are applied to ensure users can't change and update a time entry that has been submitted or approved. |
| **Time entry** | 2103572 | Time approval for non-project time entries must not be looking for project approver role. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
