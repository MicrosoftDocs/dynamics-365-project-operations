---
title: Determine your deployment type
description: This article provides information to help you determine the correct deployment type of Project operations for your company.
author: stsporen
ms.date: 03/03/2025
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Determine your deployment type

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

> [!IMPORTANT]
> After you purchase the license, start here to determine the best deployment model of Dynamics 365 Project Operations using the [Guided installation flow](https://aka.ms/provisionprojectoperations).
> After you have finished the Guided installation flow, you will be directed to the correct management portal to complete your installation. See the deployment details to complete the installation.

## Existing customers of Dynamics using Dynamics 365 Project Service Automation
Project Operations includes the capabilities that shipped with Project Service Automation. An upgrade path will be released for these customers in the 2021 release wave 1.

## Existing customers of Dynamics 365 Finance using Project management and accounting 

Existing customers of Finance who use the Project management and accounting functionality can continue to use it as is. See [Project Operations for manufacturing](#pma).

> [!NOTE]
> If you're currently using a Project Operations for manufacturing order deployment type, you can now to move to the modern architecture of Project Operations. For more details, see [Move to the modern architecture](../prod-pma/move-to-modern-architecture.md).

## Deployment regions
To determine which regions support Project Operations deployment, see [Geographical availability for Dynamics 365 and Power Platform report](https://dynamics.microsoft.com/en-us/geographic-availability/). Select **View Report**, and expand **Dynamics 365 > Operations Apps > Dynamics 365 Project Operations** to view the supported regions.

## Deployment types
Project Operations supports multiple deployment options to match your requirements. Whether you're a new or existing Dynamics 365 customer, Project Operations can support your needs.

Our [Deployment questionnaire](https://aka.ms/provisionprojectoperations) will help you determine the right deployment. The results will guide you toward one of the following deployment types:

- [Project Operations Core – deal to proforma invoicing](#lite)
- [Project Operations Integrated with ERP scenarios](#integrated)
- [Project Operations for manufacturing](#pma)

Project Operations support stocked/production order scenarios and non-stocked/resource-based scenarios on the same environment through legal entity-level configurations. For example, Contoso can use the stocked/production order capabilities in their US manufacturing facility (Legal entity = Contoso Manufacturing United States). Contoso can use the non-stocked/resource-based capabilities in their Contoso Robotics Arms servicing facility in UK (Legal entity = Contoso Robotics United Kingdom).

### <a  name="lite"></a>Project Operations Core

The Project Operations Core includes the following capabilities:

- Sales process for projects that extends Dynamics 365 Sales application experiences
- Project planning using Microsoft Project for the Web
- Multi-dimensional pricing
- Unified resource management
- Time tracking
- Basic expense
- Material usage
- Project Budgeting and Time-Phased forecasting
- Subcontracting
- Proforma invoicing for Project manager's review and edits 

#### Deployment steps
Determine the best deployment model of Project Operations using the [Deployment questionnaire](https://aka.ms/provisionprojectoperations).

For this deployment, see [Sign-up for preview subscriptions](lite-preview-subscription-sign-up.md) and [Provision new environment](lite-deployment.md). 


### <a name="integrated"></a>Project Operations Integrated with ERP scenarios
The Project Operations Integrated with ERP scenarios includes the following capabilities:
 
- Sales process for projects that extends the Dynamics 365 Sales application
- Project planning using Microsoft Project for the Web
- Multi-dimensional pricing
- Unified resource management
- Time tracking
- Basic expense
- Full expense with Receipt OCR
- Material usage
- Project Budgeting and Time-Phased forecasting
- Subcontracting
- Proforma and customer-facing invoicing 
- Revenue recognition for projects

#### Deployment steps
Determine the best deployment model of Project Operations using the [Deployment questionnaire](https://aka.ms/provisionprojectoperations).

For this deployment, see [Sign-up for preview subscriptions](resource-sign-up-preview-subscription.md) and [Provision new environment](resource-provision-new-environment.md). 


### <a name="pma"></a>Project Operations for manufacturing

- Project planning using WBS
- Resource management
- Time tracking
- Full expense
- Receipt OCR
- Full invoicing
- Revenue recognition
- Production orders
- Stocked materials support with inventory

#### Deployment steps
Determine the best deployment model of Project Operations using the [Deployment questionnaire](https://aka.ms/provisionprojectoperations).

For this deployment, see [Sign-up for preview subscriptions](/dynamics365/fin-ops-core/dev-itpro/dev-tools/sign-up-preview-subscription?toc=%2fdynamics365%2ffinance%2ftoc.json) and [Provision new environment](/dynamics365/fin-ops-core/dev-itpro/deployment/deploy-demo-environment?toc=%2fdynamics365%2ffinance%2ftoc.json). 

> [!Note]
> There isn't an out-of-box supported migration of data betweeen deployments types. If you would like to move data from one deployment type to another, this will require the creation of custom scripts, custom mapping of concepts, and potentially manual intervention to boot strap data to move it to the desired deployment type.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
