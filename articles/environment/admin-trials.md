---
title: Sign up for Project Operations trials
description: Learn how to deploy a Dynamics 365 Project Operations trial, redeem offers, configure dual-write, and provision environments in just a few steps.
author: abriccetti
ms.author: abriccetti
ms.date: 02/05/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.custom:
  - bap-template
  - sfi-image-nochange

---

# Sign up for Project Operations trials

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core, Project Operations for manufacturing-based scenarios_

This article explains how to subscribe to the preview partner offer and deploy a Dynamics 365 Project Operations environment.

By using the new Project Operations trial, you can automatically deploy any of the three supported deployment scenarios. Complete a questionnaire that recommends the best deployment approach. This article provides information about how to:

- Redeem your trial offer.
- Initiate provisioning.
- Configure dual-write.
- Learn more about Project Operations.

The following table outlines the details of the new trial offer.

| **Offer item**               | **Details**                                  |
|------------------------------|----------------------------------------------|
| Offer type                   | This offer type is Admin lead so a tenant admin is required in order to redeem. |
| Offer use                    | One time per tenant                          |
| Offer duration               | 30 calendar days                             |
| Redemptions per tenant       | 1                                            |
| Extension                    | 1 extension, 30 calendars days               |
| Number of trial environments | 3                                            |

## Admin trial details

The following table lists the trial details and how they apply to each deployment type.

| **Item**                      | **Project Operations Core**                                     | **Non-stocked materials** | **Stocked materials** |
|-------------------------------|----------------------------------------------|---------------------------|-----------------------|
| Setup data provided           | Yes                                          | Yes                       | Yes (USSI)            |
| Transactional data            | No                                           | No                        | No                    |
| Provisioning time in minutes  | 15                                           | 90                        | 30                    |

## Prerequisites

To deploy a trial of Dynamics 365 Project Operations, you need the following prerequisites.

- Sign up for the [Dynamics 365 Project Operations - Preview Trial](https://www.aka.ms/try-po).
- Tenant administrator rights for the user who deploys the preview.

> [!IMPORTANT]
> Only one person in an organization, the tenant administrator, needs to perform this task. If you're not the subscriber to this release, wait until your organization is signed up and you receive your user credentials.

### Dynamics 365 Project Operations - Preview trial

Before you begin, sign in to a browser by using the user work account in the tenant where you want the Project Operations preview.

1. Redeem the first offer code, **Dynamics 365 Project Operations - Preview Trial** by pasting it into the browser URL.

    :::image type="content" source="./media/16RedeemFirstOfferNew.png" alt-text="Screenshot of the redeem offer page.":::

1. Confirm your order.

    :::image type="content" source="./media/17ConfirmOrderNew.png" alt-text="Screenshot of the confirm order page.":::

  You see a message that the confirmation offer was successfully redeemed.

   :::image type="content" source="./media/18OrderConfirmationNew.png" alt-text="Screenshot of the order confirmation page.":::

  You're redirected to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/projectoperationstrial).

## Questionnaire and provisioning

1. Go to the [Power Platform admin center](https://admin.powerplatform.com/projectoperationstrial) and complete the questionnaire.  
1. Review the recommended deployment type, and select **Begin Setup** to initiate provisioning.
1. Review the terms and conditions and then select **Start**.

   After provisioning starts, you're redirected to the environment list in the Power Platform admin center. While provisioning is in progress, the state of your environment is **PreparingInstance**.

  When provisioning is complete, the state of your environment is **Ready**. Provisioning the environment includes deploying demo data.

1. Select the respective Microsoft Dataverse URL and the finance and operations apps URLs to validate the deployment.

## Configuring dual-write

- To configure security roles for dual-write, see [Update security settings on Project Operations in Dataverse](resource-provision-new-environment.md#update-security-settings-on-project-operations-on-dataverse).
- To access dual-write configuration, go to finance and operations instance, and then go to **Data Management** > **Dual Write**.
- To configure dual-write maps, see [Run Project Operations dual-write maps](resource-provision-new-environment.md#run-project-operations-dual-write-maps).

## Assign licenses

You need administrative access to your organization's Microsoft 365 Portal to complete the following steps.

1. Go to the [Microsoft 365 admin center](https://portal.office.com/) to assign the licenses to your users.

1. On the **Active users** page, select the users that you want to assign a license to.

1. Verify that the **Dynamics 365 Project Operations Preview**  license is selected, and then select **Save changes**.

## Additional resources

The following resources provide helpful guidance as you begin your journey with Project Operations:

- [Video Series -Project Operations Overview, feature deep dives and roadmap](https://youtube.com/playlist?list=PLcakwueIHoT_LJ3Fr1tHnkPk5lioqE6uH)
- [Dynamics 365 Project Operations](/training/modules/examine-dynamics-365-project-operations/)
- [Determine your deployment type](determine-deployment-type.md)

## Frequently asked questions

### What if I need ALM or ELM for my finance and operations apps environment?

- For partners who need full environment lifecycle management capabilities, see the [Partner Sandbox License Request](https://experience.dynamics.com/requestlicense) to review the new partner offer.
- For partners who want more information about Internal Use Rights, see [Internal Use Rights cloud and software benefit (microsoft.com)](https://partner.microsoft.com/membership/internal-use-software).

### Can I extend my trial beyond 30 days?

To extend your trial, complete the following steps:

1. In the **Microsoft 365 Admin Center**, go to **Billing** > **Your products**.
1. Select **Dynamics 365 Project Operations (CE) - Preview Trial**.
1. Under **Expiration Date**, select **Extend Date**.

### Can I upgrade from the Project Operations Core to the Project Operations Integrated with ERP based scenario deployment?

Currently, no support exists to upgrade an environment from a Project Operations Core to a non-stocked based deployment.

### Can I access Lifecycle Services for my Finance environments?  

No. For these trials, deployment is handled through the Power Platform Admin Center. Access to the Finance environment is restricted.

### Can I install my trial on an existing environment?

If you have an existing environment, you can install the Project Operations Core on an existing sales Dataverse environment from the Power Platform Admin center.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
