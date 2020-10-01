---
title: Sign up for preview subscriptions
description: 
author: sigitac
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: sigitac
---

# Sign up for preview subscriptions for Resource/ non-stocked scenarios

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

|
 |
| --- |

This topic explains how to subscribe to the preview/partner offer and deploy Project Operations environment for resource/ non-stocked scenarios.

## Prerequisites

1. You&#39;ve received an email that invites you to participate in the preview. You can request preview in [Project Operations](https://dynamics.microsoft.com/en-us/project-operations/overview/) website.
2. User deploying the preview must have Azure tenant global administrator rights.
3. Deploying Finance environment requires a valid Azure subscription that will be billed per environment usage. You can use your organizations existing subscription or use [Azure trial](https://azure.microsoft.com/en-us/free/) to get started. Customer Engagement environment will be provided for free for a limited 30 days period.

## Subscribe

Upon [preview request](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUMkRDV1NYQU5TNjE2VjhKOVBUNVg2R0s1NC4u) approval, you will receive 2 offers from Microsoft by email, entitling you to deploy Project Operations Preview:

- Dynamics 365 Project Operations – Preview Trial
- Dynamics 365 for Finance and Operations Preview Trial.

**! Important**

Only one person (tenant administrator) in an organization must perform this task. If you aren&#39;t the person who is subscribing to this release, wait until your organization has been signed up and you&#39;ve received your user credentials.

### Dynamics 365 Project Operations – Preview Trial

Redeem the first offer, Dynamics 365 Project Operations Trial with the URL provided in your welcome email:

![First Offer](1FirstOffer.png)

Make sure you are logged in with the user belonging to the organization who will be subscribing to the service, then proceed with redeeming the offer. Select &quot;Yes, add it to my account&quot;:

![Redeem Offer](2RedeemFirstOffer.png)

![Confirm Offer](2ConfirmFirstOffer.png)

![Offer Redeemed](4OfferSuccessfulyRedeemed.png)

### Dynamics 365 Finance and Operations Preview Trial

Repeat the same steps with the second offer from the Welcome email.

## Assign Licenses

**! Important**

You will need administrative access to your organization Office 365 Portal to perform steps below.

Navigate to [https://portal.office.com](https://portal.office.com/) to assign the licenses to your users.

![Office Admin Portal](5OfficeAdminPortal.png)

Navigate to users to assign the licenses to your user(s):

![Assign Licenses](6AssignLicenses.png)

Ensure Project Operations license have been selected. Please note, the Finance and Operations Trial Offer does not need to be assigned to a user.

## Start a new project in LCS

Create a new LCS project as described in [this article](create-lcs-project.md)

## Add Azure subscription to LCS project

Add Azure subscription to LCS project as described in [this article](resource-add-azure-subscription-lcs-project.md)

## Deploy Finance and Operations demo environment with Project Operations for resource/ non-stocked scenarios

Follow the guidance in [Provision a new environment](resource-provision-new-environment.md) to complete the deployment. Use [demo environment](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment) deployment type for preview.

## Install CE Setup and Configuration Data

Install CE setup and configuration data as described in [this article](resource-apply-pro-setup-config-data.md)

1
