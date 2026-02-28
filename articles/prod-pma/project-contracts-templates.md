---
title: Synchronize project contracts and projects directly from Project Service Automation to Finance
description: This article describes the template and underlying tasks that are used to synchronize project contracts and projects directly from Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Finance.
author: poojafandan
ms.author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
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



This article describes the template and underlying tasks that synchronize project contracts and projects directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.

> [!NOTE] 
> If you're using Enterprise edition 7.3.0, you must install KB 4074835.

## Data flow for Project Service Automation to Finance

> [!NOTE]
> Before you use the Project Service Automation to Finance integration solution, familiarize yourself with the Dynamics 365 Data integration feature.

The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance. The integration template that is available with the Data integration feature enables the flow of data about project contracts, projects, project contract lines, and project contract line milestones from Project Service Automation to Finance.

The following illustration shows how the data synchronizes between Project Service Automation and Finance.

:::image type="content" source="./media/ProjectsAndContractsFlow_upd.JPG" alt-text="Screenshot of data flow for Project Service Automation integration with Finance." lightbox="./media/ProjectsAndContractsFlow.JPG":::

## Templates and tasks

To access the available templates, in the Microsoft Power Apps admin center, select **Projects**. Then, in the upper-right corner, select **New project** to select public templates.

Use the following templates and underlying tasks to synchronize project contracts and projects from Project Service Automation to Finance:

### Integrating with Dynamics 365 Project Service Automation v2.x
- **Name of the template in Data integration:** Projects and contracts (Project Service Automation to Finance)
- **Name of the tasks in the project:**

    - Project contracts Project Service Automation to Finance
    - Projects Project Service Automation to Finance
    - Project contract lines Project Service Automation to Finance
    - Project contract line milestones Project Service Automation to Finance
  
### Integrating with Dynamics 365 Project Service Automation v3.x
A schema change in Project Service Automation affects the Project contract line milestone template. To integrate Dynamics 365 Project Service Automation v3.x with Dynamics 365, use version 2 of the template.

- **Name of the template in Data integration:** Projects and Contracts (Project Service Automation 3.x to Finance) - v2
- **Name of the tasks in the project:**

    - Project contracts Project Service Automation to Finance
    - Projects Project Service Automation to Finance
    - Project contract lines Project Service Automation to Finance
    - Project contract line milestones Project Service Automation to Finance

Before you can synchronize project contracts and projects, you must synchronize accounts.

## Entity set

| Project Service Automation       | Finance                                                |
|----------------------------------|--------------------------------------------------------|
| Orders                           | Integration entity for project contract                |
| Projects                         | Integration entity for project                         |
| Order lines                      | Integration entity for project contract line           |
| Project contract line milestones | Integration entity for project contract line milestone |

## Entity flow

Project contracts are managed in Project Service Automation, and you synchronize them to Finance as project contracts. As part of the integration template, you can set the integration source in Finance for the project contract.

You manage time and material and fixed-price projects in Project Service Automation and synchronize them to Finance as projects. As part of the template integration, you can set the integration source for the project in Finance. Currently, only time and material and fixed-price projects are supported.


You manage project contract lines in Project Service Automation, and you synchronize them to Finance as project contract billing rules. If the billing method differs from the default project type, the synchronization updates the project type for the contract line project and project group.

You manage project contract line milestones in Project Service Automation, and you synchronize them to Finance as project contract billing rule milestones.

## Project Service Automation to Finance integration solution

The **Project contract ID** field is available on the **Project contracts** page. This field is a natural and unique key that supports the integration.

When you create a new project contract, if a **Project contract ID** value doesn't already exist, the system automatically generates one by using a number sequence. The value consists of **ORD** followed by an incrementing number sequence and then a suffix of six characters. Here's an example: **ORD-01022-Z4M9Q0**.

The **Project Number** field is available on the **Projects** page. This field is a natural and unique key that supports the integration.

When you create a new project, if a **Project Number** value doesn't already exist, the system automatically generates one by using a number sequence. The value consists of **PRJ** followed by an incrementing number sequence and then a suffix of six characters. Here's an example: **PRJ-01049-CCNID0**.

When you apply the Project Service Automation to Finance integration solution, an upgrade script sets the **Project contract ID** field for existing project contracts and the **Project Number** field for existing projects in Project Service Automation.

## Prerequisites and mapping setup

- Before project contracts and projects can synchronize, you must synchronize accounts.
- In your connection set, add an integration key field mapping for **msdyn\_organizationalunits** to **msdyn\_name \[Name\]**. You might first need to add a project to the connection set. For more information, see [Integrate data into Common Data Service for Apps](/powerapps/administrator/data-integrator).
- In your connection set, add an integration key field mapping for **msdyn\_projects** to **msdynce\_projectnumber \[Project Number\]**. You might first need to add a project to the connection set. For more information, see [Integrate data into Common Data Service for Apps](/powerapps/administrator/data-integrator).
- You can update or remove **SourceDataID** for project contracts and projects from the mapping. The default template value is **Project Service Automation**.
- You must update the **PaymentTerms** mapping so that it reflects valid terms of payment in Finance. You can also remove the mapping from the project task. The default value map has default values for demo data. The following table shows the values in Project Service Automation.

    | Value | Description   |
    |-------|---------------|
    | 1     | Net 30        |
    | 2     | 2% 10, Net 30 |
    | 3     | Net 45        |
    | 4     | Net 60        |

## Power Query

Use Microsoft Power Query for Excel to filter data if the following conditions are true:

- You have sales orders in Dynamics 365 Sales.
- You have multiple organizational units in Project Service Automation, and these organizational units map to multiple legal entities in Finance.

If you must use Power Query, follow these guidelines:

- The **Projects and contracts (PSA to Fin and Ops)** template includes a default filter that includes only sales orders of the **Work item (msdyn_ordertype = 192350001)** type. This filter helps guarantee that project contracts aren't created for sales orders in Finance. If you create your own template, you must add this filter.
- Create a Power Query filter that includes only the contract organizations that you synchronize to the legal entity of the integration connection set. For example, project contracts that you have with the contract organizational unit of Contoso US synchronize to the USSI legal entity, but project contracts that you have with the contract organizational unit of Contoso Global synchronize to the USMF legal entity. If you don't add this filter to your task mapping, all project contracts synchronize to the legal entity that you define for the connection set, regardless of the contract organizational unit.

## Template mapping in Data integration

> [!NOTE] 
> The **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState**, and **AddressZipCode** fields aren't part of the default mapping for project contracts. Add these mappings if you need to synchronize this data for project contracts.
>
> The **Description**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, and **ProjectType** fields aren't part of the default mapping for projects. Add these mappings if you need to synchronize this data for projects.

The following illustrations show examples of the template task mappings in Data integration. The mapping shows the field information that synchronizes from Project Service Automation to Finance.

:::image type="content" source="./media/ProjectContractTemplateMapping.JPG" alt-text="Screenshot of project contract template mapping." lightbox="./media/ProjectContractTemplateMapping.JPG":::

:::image type="content" source="./media/ProjectTemplateMapping.JPG" alt-text="Screenshot of project template mapping." lightbox="./media/ProjectTemplateMapping.JPG":::

:::image type="content" source="./media/ProjectContractLinesMapping.JPG" alt-text="Screenshot of project contract lines template mapping." lightbox="./media/ProjectContractLinesMapping.JPG":::

:::image type="content" source="./media/ProjectContractLineMilestonesMapping.JPG" alt-text="Screenshot of project contract line milestone template mapping." lightbox="./media/ProjectContractLineMilestonesMapping.JPG":::

#### Project contract line milestone mapping in the Projects and Contracts (PSA 3.x to Dynamics) - v2 template:

:::image type="content" source="./media/ProjectContractLineMilestoneMapping_v2.jpg" alt-text="Screenshot of project contract line milestone mapping with version two template." lightbox="./media/ProjectContractLineMilestoneMapping_v2.jpg":::


[!INCLUDE[footer-include](../includes/footer-banner.md)]
