---
title: Synchronize project contracts and projects directly from Project Service Automation to Finance
description: This article describes the template and underlying tasks that are used to synchronize project contracts and projects directly from Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Finance.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: article
ms.custom: 
  - bap-template
audience: Application User
ms.reviewer: johnmichalak
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0

---

# Synchronize project contracts and projects directly from Project Service Automation to Finance 

[!include[banner](../includes/banner.md)]



This article describes the template and underlying tasks that are used to synchronize project contracts and projects directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.

> [!NOTE] 
> If you're using Enterprise edition 7.3.0, you must install KB 4074835.

## Data flow for Project Service Automation to Finance

> [!NOTE]
> Before you can use the Project Service Automation to Finance integration solution, you should be familiar with the Dynamics 365 Data integration feature.

The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance. The integration template that is available with the Data integration feature enables the flow of data about project contracts, projects, project contract lines, and project contract line milestones from Project Service Automation to Finance.

The following illustration shows how the data is synchronized between Project Service Automation and Finance.

[![Data flow for Project Service Automation integration with Finance.](./media/ProjectsAndContractsFlow_upd.JPG)](./media/ProjectsAndContractsFlow.JPG)

## Templates and tasks

To access the available templates, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.

The following templates and underlying tasks are used to synchronize project contracts and projects from Project Service Automation to Finance:

### Integrating with Dynamics 365 Project Service Automation v2.x
- **Name of the template in Data integration:** Projects and contracts (Project Service Automation to Finance)
- **Name of the tasks in the project:**

    - Project contracts Project Service Automation to Finance
    - Projects Project Service Automation to Finance
    - Project contract lines Project Service Automation to Finance
    - Project contract line milestones Project Service Automation to Finance
  
### Integrating with Dynamics 365 Project Service Automation v3.x
There is a schema change in Project Service Automation that impacts the Project contract line milestone template and use of the v2 version of the template is required to integrate Project Service Automation v3.x with Dynamics 365.

- **Name of the template in Data integration:** Projects and Contracts (Project Service Automation 3.x to Finance) - v2
- **Name of the tasks in the project:**

    - Project contracts Project Service Automation to Finance
    - Projects Project Service Automation to Finance
    - Project contract lines Project Service Automation to Finance
    - Project contract line milestones Project Service Automation to Finance

Before synchronization of project contracts and projects can occur, you must synchronize accounts.

## Entity set

| Project Service Automation       | Finance                                                |
|----------------------------------|--------------------------------------------------------|
| Orders                           | Integration entity for project contract                |
| Projects                         | Integration entity for project                         |
| Order lines                      | Integration entity for project contract line           |
| Project contract line milestones | Integration entity for project contract line milestone |

## Entity flow

Project contracts are managed in Project Service Automation, and they are synchronized to Finance as project contracts. As part of the integration template, you can set the integration source in Finance for the project contract.

Time and material and fixed-price projects are managed in Project Service Automation and synchronized to Finance as projects. As part of the template integration, you can set the integration source for the project in Finance. Currently, only time and material and fixed-price projects are supported.


Project contract lines are managed in Project Service Automation, and they are synchronized to Finance as project contract billing rules. If the billing method differs from the default project type, the synchronization updates the project type for the contract line project and project group.

Project contract line milestones are managed in Project Service Automation, and they are synchronized to Finance as project contract billing rule milestones.

## Project Service Automation to Finance integration solution

The **Project contract ID** field is available on the **Project contracts** page. This field has been made a natural and unique key to support the integration.

When a new project contract is created, if a **Project contract ID** value doesn't already exist, it's automatically generated by using a number sequence. The value consists of **ORD** followed by an incrementing number sequence and then a suffix of six characters. Here is an example: **ORD-01022-Z4M9Q0**.

The **Project Number** field is available on the **Projects** page. This field has been made a natural and unique key to support the integration.

When a new project is created, if a **Project Number** value doesn't already exist, it's automatically generated by using a number sequence. The value consists of **PRJ** followed by an incrementing number sequence and then a suffix of six characters. Here is an example: **PRJ-01049-CCNID0**.

When the Project Service Automation to Finance integration solution is applied, an upgrade script sets the **Project contract ID** field for existing project contracts and the **Project Number** field for existing projects in Project Service Automation.

## Prerequisites and mapping setup

- Before synchronization of project contracts and projects can occur, you must synchronize accounts.
- In your connection set, add an integration key field mapping for **msdyn\_organizationalunits** to **msdyn\_name \[Name\]**. You might first need to add a project to the connection set. For more information, see [Integrate data into Common Data Service for Apps](/powerapps/administrator/data-integrator).
- In your connection set, add an integration key field mapping for **msdyn\_projects** to **msdynce\_projectnumber \[Project Number\]**. You might first need to add a project to the connection set. For more information, see [Integrate data into Common Data Service for Apps](/powerapps/administrator/data-integrator).
- **SourceDataID** for project contracts and projects can be updated to a different value or removed from the mapping. The default template value is **Project Service Automation**.
- The **PaymentTerms** mapping must be updated so that it reflects valid terms of payment in Finance. You can also remove the mapping from the project task. The default value map has default values for demo data. The following table shows the values in Project Service Automation.

    | Value | Description   |
    |-------|---------------|
    | 1     | Net 30        |
    | 2     | 2% 10, Net 30 |
    | 3     | Net 45        |
    | 4     | Net 60        |

## Power Query

Use Microsoft Power Query for Excel to filter data if the following conditions are met:

- You have sales orders in Dynamics 365 Sales.
- You have multiple organizational units in Project Service Automation, and these organizational units will be mapped to multiple legal entities in Finance.

If you must use Power Query, follow these guidelines:

- The Projects and contracts (PSA to Fin and Ops) template has a default filter that includes only sales orders of the **Work item (msdyn\_ordertype = 192350001)** type. This filter helps guarantee that project contracts aren't created for sales orders in Finance. If you create your own template, you must add this filter.
- Create a Power Query filter that includes only the contract organizations that should be synchronized to the legal entity of the integration connection set. For example, project contracts that you have with the contract organizational unit of Contoso US should be synchronized to the USSI legal entity, but project contracts that you have with the contract organizational unit of Contoso Global should be synchronized to the USMF legal entity. If you don't add this filter to your task mapping, all project contracts will be synchronized to the legal entity that is defined for the connection set, regardless of the contract organizational unit.

## Template mapping in Data integration

> [!NOTE] 
> The **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState**, and **AddressZipCode** fields aren't included in the default mapping for project contracts. You can add the mappings if you require that this data be synchronized for project contracts.
>
> The **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, and **ProjectType** fields aren't included in the default mapping for projects. You can add the mappings if you require that this data be synchronized for projects.

The following illustrations show examples of the template task mappings in Data integration. The mapping shows the field information that will be synchronized from Project Service Automation to Finance.

[![Project contract template mapping.](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Project template mapping.](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Project contract lines template mapping.](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Project contract line milestone template mapping.](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### Project contract line milestone mapping in the Projects and Contracts (PSA 3.x to Dynamics) - v2 template:

[![Project contract line milestone mapping with version two template.](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
