---
title: Sign up for Project Operations admin lead trials
description: This topic provides information about how to deploy a trial of Project Operations.
author: ruhercul
ms.date: 08/09/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Sign up for Project Operations Trials 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing, Project Operations for stocked/production-based scenarios_ 

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

This topic explains how to subscribe to the preview partner offer and deploy a Project Operations environment.

## Overview
With the new Project Operations admin lead trial, you can automatically deploy any of the three suported deployment scenarios by completing a questionnaire which recommends the best deployment approach. This topic reviews the process to:

- Redeem your trial offer
- Initiate provisioning
- Configure Dual-write
- learn more about Project Operations 


| **Offer Item**                    | **Details**                                  |
|------------------------------|----------------------------------------------|
| Offer type                   | Admin Lead (requires tenant admin to redeem) |
| Offer use                    | Once per tenant                              |
| Offer duration               | 30 calendar days                             |
| Redemptions per tenant       | 1                                            |
| Number of users              | 25                                           |
| Extension                    | 1 extension, 30 calendars days               |
| Number of trial environments | 3                                            |


## Admin trial details
The following table lists the trial details and how they apply to each deployment type.
| **Item**                   | **Lite**                                     | **Non-stocked materials** | **Stocked materials** |
|-------------------------------|----------------------------------------------|---------------------------|-----------------------|
|     |
| Setup data provided           | Yes                                          | Yes                       | Yes (USSI)            |
| Transactional data            | No                                           | No                        | No                    |
| Provisioning time (minutes)   | 15                                           | 90                        | 30                    |

## Prerequisites

- Sign-up for the [Dynamics 365 Project Operations - Preview Trial](https://www.aka.ms/try-po).
- The user who deploys the preview must have Azure tenant global administrator rights.

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

## Questionnaire and provisioning

1.	Go to the [Power Platform admin center](https://admin.powerplatform.com/projectoperationstrial) and complete the questionnaire.  
2.	Review the recommended deployment type and select **Begin Setup** to initiate provisioning.
3.	Review the terms and conditions and then select **Start**.

   After provisioning starts, you are redirected to the environment list in the Power Platform admin center. While provisioning is in progress, the state of your environment is **PreparingInstance**.
 
  After the provisioning is complete, the state of your environment is **Ready**.
 
4.	When the provisioning is complete, select the respective CDS and Finance and Operations apps URLs to validate the deployment.

## Configuring Dual Write
For Non-stocked materials deployments only, configure your dual write mappings per the public documentation provided [here](https:/docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps).

## Assign licenses

> [!IMPORTANT]
> You will need administrative access to your organization's Microsoft 365 Portal to complete the following steps.

1. Go to the [Microsoft 365 admin center](https://portal.office.com/) to assign the licenses to your users.

   ![Admin center home page](./media/14AdminPortal.png)

2. On the **Active users** page, select the users that you want to assign a license to.

   ![Assign Licenses](./media/15AssignLicenses.png)

3. Verify that the **Dynamics 365 Project Operations Preview**  license has been selected, and then select **Save changes**.

## Resources
The following resources provide helpful guidance as you begin your journey with Project Operations:

-   [Video Series -Project Operations Overview, feature deep dives and
    roadmap](https://youtube.com/playlist?list=PLcakwueIHoT_LJ3Fr1tHnkPk5lioqE6uH)

-   [Dynamics 365 Project Operations \|Microsoft
    Learn](https://docs.microsoft.com/en-us/learn/modules/examine-dynamics-365-project-operations/)

-   [Determine your deployment type \|Microsoft
    Docs](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/determine-deployment-type)

## Frequently asked questions

### What if I require ALM or ELM for my Finance and Operations environment?
- For partners who require full environment lifecycle management capabilities, see [](https://experience.dynamics.com/requestlicense) to review the new partner driven offer. If you require access to a Tier 1 environment for development and testing, go to [Microsoft](microsoft.com) for more information.
- For Partners seeking more information on Internal Use Rights, the following link provides additional information: [Internal Use Rights cloud and software benefit (microsoft.com)] (https://partner.microsoft.com/en-us/membership/internal-use-software)

### Can I extend my trial beyond 30 days?
To extend your trials, do the following:
 - Navigate to Microsoft 365 Admin Center > Billing > Your products
 - Select **Dynamics 365 Project Operations (CE) - Preview Trial**
 - Under Expiration Date, Select **Extend Date**

### Can I upgrade from the Lite deployment to Project Operations for resource/non-stocked based scenarios?
Currently, there is no support to upgrade an environment from lite to non-stocked based deployment.

### Can I access Life Cycle Services (LCS) for my D365 Finance environments?  
No, for the admin lead trials, deployment is handled through the Power Platform Admin Center and access to the D365 Finance environment is restricted.

### Can I install my trial on an existing org?
If you have an existing environment, from the Power Platform Admin center you will be allowed to intall the lite deployment on an existing sales dataverse environment.
[!INCLUDE[footer-include](../includes/footer-banner.md)]
