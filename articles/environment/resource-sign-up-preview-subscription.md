---
title: Sign up for Project Operations preview subscriptions for resource/ non-stocked scenarios
description: This article provides information about how to subscribe to and deploy Project Operations Integrated with ERP.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Sign up for Project Operations preview subscriptions for resource/ non-stocked scenarios

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_



This article explains how to subscribe to the trial offer and deploy Project Operations environment for resource/non-stocked based scenarios.

## Prerequisites
- The user who deploys the preview must have tenant administrator rights. You can create a tenant during the first offer redemption. 
- Deploying a Finance environment requires a valid Azure subscription that will be billed per environment. You can use your organizations existing subscription or use an [Azure trial](https://azure.microsoft.com/free/) to get started. The CDS environment will be provided free for a limited 30 day period.

> [!IMPORTANT]
> Only one person, the tenant administrator, in an organization needs to perform this task. If you aren't the subscriber to this release, wait until your organization has been signed up and you've received your user credentials.
> 
> Trials are single use in the tenant. You can only run a trial one time. We recommend that you create a new tenant for the purpose of the trial.


### Dynamics 365 Project Operations (CE) - Preview Trial 

Before you begin, make sure you are logged in to a browser with the user work account in the tenant where you want the Project Operations preview.

1. Redeem the first offer code, **Dynamics 365 Project Operations** here [Project Operations Trial](https://aka.ms/try-po).
2. Confirm your order.

  You will see confirmation offer was successfully redeemed.

### Dynamics 365 Finance preview trial

Go to [Dynamics 365 for Finance Preview Trial](https://aka.ms/trypoche) and repeat the steps from the previous section with the offer, Sign up for the Cloud Hosted Environment.  

## Assign licenses

> [!IMPORTANT]
> You will need administrative access to your organization's Microsoft 365 Portal to complete the following steps.

1. Go to [Microsoft 365 admin center](https://portal.office.com/) to assign the licenses to your users.

2. On the **Active users** page, select the users that you want to assign a license to.

3. Verify that the **Dynamics 365 Project Operations** license has been selected and select **Save changes**.

> [!NOTE]
> The Finance trial offer does not need to be assigned to a user.

## Start a new project in LCS

Create a new LCS project as described in the article, [Start a new project in LCS](create-lcs-project.md)

## Add an Azure subscription to an LCS project

To complete this task, follow the steps in the article, [Add an Azure subscription to LCS project](resource-add-azure-subscription-lcs-project.md).

## Deploy Finance demo environment with Project Operations for resource/non-stocked scenarios

Follow the guidance in the article, [Provision a new environment](resource-provision-new-environment.md) to complete the deployment. Use the [demo environment](/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment) deployment type for preview. 

## Install CDS setup and configuration data

Install CDS setup and configuration data as described in the article, [Set up and apply configuration data in the Common Data Service](resource-apply-pro-setup-config-data.md).
Complete this step only after Finance demo environment is deployed and demo data is ready.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
