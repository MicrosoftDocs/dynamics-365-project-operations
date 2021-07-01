---
title: Sign up for Project Operations admin lead trials
description: This topic provides information about how to deploy an admin lead trial of Project Operations.
author: ruhercul
ms.date: 07/09/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Sign up for Project Operations admin lead trials 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, Project Operations for stocked/production-based scenarios_ 

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

This topic explains how to subscribe to the preview partner offer and deploy a Project Operations environment.

## Overview
With the new Project Operations admin lead trial, you can automatically deploy any of the three suported deployment scenarios by completing a questionnaire which recommends the best deployment approach. This topic reviews the process to redeem your trial offer and administer Dual-write, and provides links to supporting materials to help you get the most out of your trial experience.    

## Admin trial details
The following table lists the trial details and how they apply to each deployment type.

|        **Details**                                   | **Lite**                                                                                                                                                 | **Non-stocked materials** | **Stocked materials** |
|-----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|-----------------------|
| Offer type                                          | Admin lead (requires tenant admin to redeem)                                                                                                             |                           |                       |
| Offer use                                           | Once per tenant                                                                                                                                          |                           |                       |
| Offer duration                                      | 30 calendar days                                                                                                                                         |                           |                       |
| Redemptions per tenant                              | 1                                                                                                                                                        |                           |                       |
| Number of users                                     | 25                                                                                                                                                       |                           |                       |
| Extension                                           | 30                                                                                                                                                       |                           |                       |
| Number of trials environments                       | 3                                                                                                                                                        |                           |                       |
| Setup data provided                                 | Yes                                                                                                                                                      | Yes                       | Yes (USSI)            |
| Transactional data                                  | No                                                                                                                                                       | No                        | No                    |
| Provisioning time                                   | 15                                                                                                                                                       | 150                       | 30                    |
| Versions at launch                                  | UR11                                                                                                                                                     | 10.0.19/UR11              | 10.0.19               |
| CDS Environment Life Cycle Management Support (ELM) | N/A                                                                                                |           N/A                |             N/A          |
| CDS Application Life Cycle Support (ALM)            | Microsoft CDS apps can be upgraded. Adjacent CDS apps can be installed (e.g. Field Service).                                                                         |                           |                       |
| Finance and Operations apps ELM and ALM                                       | These environments don't have access to Life Cycle Services (LCS), therefore customers will not have access to upgrades, quality updates, or backup and restore. |                           |                       |
| Upgrade to paid                                     | Not available                                                                                                                          |              Not available              |           Not available              |



## Prerequisites

- Sign-up for the [Dynamics 365 Project Operations - Preview Trial](https://www.aka.ms/try-po).
- The user who deploys the preview must have Azure tenant global administrator rights.
- The Microsoft CDS environment will be provided free for a limited 30 day period.


> [!IMPORTANT]
> Only one person, the tenant administrator, in an organization needs to perform this task. If you aren't the subscriber to this release, wait until your organization has been signed up and you've received your user credentials.

### Dynamics 365 Project Operations - Preview Trial 

Before you begin, make sure you are logged in to a browser with the user work account in the tenant where you want the Project Operations preview.

1. Redeem the first offer code, **Dynamics 365 Project Operations - Preview Trial** by pasting it into the browser URL.

  ![Redeem Offer](./media/16RedeemFirstOfferNew.png)

2. Confirm your order.

  ![Confirm the order](./media/17ConfirmOrderNew.png)

You will see confirmation offer was successfully redeemed.

  ![Confirmation](./media/18OrderConfirmationNew.png)

You will be redirected to the [Power Platform admin center](https://admin.powerplatform.com/projectoperationstrial).

## Assign licenses

> [!IMPORTANT]
> You will need administrative access to your organization's Microsoft 365 Portal to complete the following steps.

1. Go to the [Microsoft 365 admin center](https://portal.office.com/) to assign the licenses to your users.

   ![Admin center home page](./media/14AdminPortal.png)

2. On the **Active users** page, select the users that you want to assign a license to.

   ![Assign Licenses](./media/15AssignLicenses.png)

3. Verify that the **Dynamics 365 Project Operations Preview**  license has been selected, and then select **Save changes**.

## Questionnaire and provisioning

1.	Go to the [Power Platform admin center](https://admin.powerplatform.com/projectoperationstrial) and complete the questionnaire.  
2.	Review the recommended deployment type and select **Begin Setup** to initiate provisioning.
3.	Review the terms and conditions and then select **Start**.

   After provisioning starts, you are redirected to the environment list in the Power Platform admin center. While provisioning is in progress, the state of your environment is **PreparingInstance**.
 
  After the provisioning is complete, the state of your environment is **Ready**.
 
4.	When the provisioning is complete, select the respective CDS and Finance and Operations apps URLs to validate the deployment.

## Resources
The following topics provide brief introductions to the key scenarios supported by the application.

|       Topic              | Lite/Non Stocked                                                                                                         | Stocked Materials                                                                                                        |
|---------------------|--------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Lead to Quote       | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | n/a                                                                                                                      |
| Create a Project    | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |
| Create a Contract   | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |
| Resource a project  | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |
| Time and Expense    | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |
| Invoice             | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |
| Revenue Recognition | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) | [here](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-apply-pro-setup-config-data) |

## Frequently asked questions

### What if I require ALM or ELM for my Finance and Operations environment?
For partners who require full environment lifecycle management capabilities, see [](https://experience.dynamics.com/requestlicense) to review the new partner driven offer. If you require access to a Tier 1 environment for development and testing, go to [Microsoft](microsoft.com) for more information.

### Can I extend my trial beyond 30 days?
To extend your trials, do the following:

### Can I upgrade from the Lite deployment to Project Operations for resource/non-stocked based scenarios?
Currently, there is no support to update an environment from lite to non-stocked based deployment.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
