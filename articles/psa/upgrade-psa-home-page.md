---
title: Upgrade home page
description: This article shows where to find important information about the new and changed features in Dynamics 365 Project Service Automation, and the process for upgrading to the newest version.
 
ms.custom: 
  - dyn365-projectservice
  - evergreen
ms.date: 07/07/2025
ms.topic: upgrade-and-migration-article
author: rumant
ms.author: rumant
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Upgrade home page

[!include [banner](../includes/psa-now-project-operations.md)]

[!INCLUDE[cc-applies-to-psa-app-1x-2x](../includes/cc-applies-to-psa-app-1x-2x.md)]

## Upgrade from PSA version 2.x or 1.x to version 3.x

### New instances

As of May 17, 2019, when Project Service Automation is selected during the provisioning of a new instance, version 3.x is installed by default.

### Existing instances

Previously, customers who have an instance of PSA version 2.x and needed to upgrade to version 3.x, which is the Unified client interface-based (UCI) version of PSA, had to contact Microsoft Support and provide the details of their instance so that support could enable the instance for upgrade to version 3.x. As of March 1, 2020, customers who have an instance of PSA version 2.x and need to upgrade to version 3.x, will able to upgrade their instances directly from the Admin portal without having to contact Microsoft Support.  

> [!NOTE]
> PSA version 3.x includes significant changes. It has been built on the Unified Interface framework to help provide an improved user experience. The redesigned app delivers a consistent, uniform user interface (UI), and it follows responsive design principles for optimal viewing on any screen size or device. There have been other changes throughout the application. Some of the areas that have been changed include pricing, booking and assigning resources, time, expenses, and approvals.

Before you begin the upgrade process, we recommend that you complete the following tasks:

- Verify whether both Dynamics 365 Field Service and Project Service Automation are installed on the identified instance. If both solutions are installed, you should plan to upgrade both before you resume regular use of the instance.
- Carefully review the following articles. Awareness and understanding of the changes between versions will help you with the upgrade process. These articles provide information about the major changes in PSA, together with considerations and recommendations for planning your upgrade to version 3.x.

    - [What's new or changed in Project Service Automation version 3](whats-new-changed-v3.md)
    - [Upgrade considerations - Project Service Automation version 2.x or 1.x to version 3](upgrade-v3.md)

- Upgrade your sandbox instance to evaluate the changes in your implementation before you upgrade your production instance.

After you've reviewed the articles that were mentioned earlier and are ready to upgrade to PSA version 3.x or the UCI-based version, submit a request to Microsoft support to make the upgrade available from Admin center. In your request, provide the details of your instance.

## Older versions of PSA (PSA version 2.x) in a newly created instance

As of May 17, 2019, all new instances will have UCI as the default client. For alignment with this change, PSA version 3.x and Field Service version 8.x will be provisioned by default, because these versions are designed to work with the UCI client.

Starting March 1, 2020, customers of Dynamics PSA will no longer be able to create a new environment with older versions of PSA, for example PSA version 2.x or lower. Any new environment will be to get only version 3.x of PSA.

> [!NOTE]
> For the best experience when you use older versions of the Field Service and PSA applications, go to the **System settings** page and for the field, **Use the new Unified Interface only (recommended)** field, select **No** as these versions aren't designed to be correctly loaded in UCI. After you have turned off UCI, you can open and run these versions of Field Service and PSA by using the old web client. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
