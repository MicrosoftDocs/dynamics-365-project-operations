---
title: Contract line-based revenue recognition with Project operations
description: This article provides information about contract lines based revenue recognition in Project Operations.
author: mukumarm
ms.date: 10/27/2023
ms.topic: overview
ms.reviewer: johnmichalak 
ms.author: mukumarm

---
# Contract line-based revenue recognition with Project operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios_
 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

The **Contract line-based revenue recognition with Project operations** feature lets you recognize the revenue for each contract line that's associated with a contract. Contract line–based revenue recognition gives you the flexibility to define a different revenue recognition method for each contract line. Microsoft Dynamics 365 Finance then generates and posts the revenue recognition amounts accordingly.

To use this feature, activate **Enable contract line-based revenue recognition with Project Operations for non-stocked/resource-based scenarios**.

> [!NOTE]
> After this feature is enabled, it can't be disabled.

When this feature is enabled, Dynamics 365 Finance generates the revenue recognition only for each contract line that's used as a fixed price billing method. All older projects or revenue recognition projects can be managed.

## Fixed price revenue estimate project with a contract line

When you create a project contract line that has the following attributes in Dynamics 365 Project Operations on Dataverse, the system automatically creates a fixed price revenue estimate project. The information in the project is based on these attributes.

- A fixed price billing method
- An associated project
- At least one milestone that's defined on the **Invoice schedule** tab of the **Project contract line** page

When **Enable contract line-based revenue recognition with Project Operations for non-stocked/resource-based scenario** is activated, Dynamics 365 Finance generates a fixed-price revenue estimate project for each contract line that uses a fixed-price billing method and has a defined milestone.

For more information about project contract lines in Dataverse and how contract lines are linked with project tasks, see [Project contract lines overview](../pro/sales/manage-contract-values-project-based-sales.md).

For more information about how to map projects and tasks to a project contract line, see [Map projects and tasks to a project contract line](../pro/sales/mapping-projects-tasks-contract-line-sales.md).

## Review project contracts for contract lines

To review the project contract lines or update additional details in Dynamics 365 Finance, follow these steps.

1. In the Dynamics 365 Finance environment, go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. On the Action Pane, select **Show default accounting**.
1. Select the contract line in the drop-down list to enter the default financial dimensions that are applicable to the contract line.
1. If the **Straight line revenue recognition** principal is applied on the revenue recognition project for the selected contract line, specify the start date and end date. The start date and end date are used to calculate the number of days that are required for the **Straight line revenue recognition** principal.

## Review fixed price revenue estimate projects

To review fixed price revenue estimate projects, follow these steps.

1. In the Dynamics 365 Finance environment, go to **Project management and accounting** \> **Projects** \> **Fixed price revenue estimate projects**.
1. Select the revenue project that you want to view, and then double-tap (or double-click) the **Estimate project ID** value to open the record and review the details of the project.
1. On the header, select the default project that's required to post the estimated revenue recognition amount. All the required financial postings are generated for the project that's defined on the revenue recognition project header. Dynamics 365 Finance retrieves the financial dimensions from the project and uses them to record the financial transactions to revenue recognition.
1. On the header, select the cost template. This template is used to do the required calculations, such as completed percentage, completed contract, or straight line.
1. Select the **Contract line** tab. There should be one contract line in the **Selected contract lines** grid. This line is the default contract line that the revenue recognition project has been created for.
1. To change the association, select additional contract lines, and add them to the **Selected contract lines** grid. If multiple contract lines are selected in this grid, the percentage completion and revenue estimates are calculated together for all selected contract lines.

    > [!NOTE]
    > For the **Straight line revenue recognition** principal, only one contract line is applicable to each revenue recognition project. Therefore, when you use the **Straight line revenue recognition** principal, you can't add multiple contract lines for a single revenue recognition project.

The **Project cost**, **Revenue profile**, **Cost template**, and **Period code** fields can be set manually. If they aren't set manually, default values are entered during the first estimate calculation for the project by using the rules that are configured for project cost and revenue profiles.

### Example scenario

Contoso systems awarded one contract to implement business applications for one of its customers. Per the agreement, the whole implementation is divided into the following phases:

1. **License Fee** – Fixed price. The Contoso Finance team decided to accrue the revenue based on the straight line method.
1. **Analysis** – Fixed price. The Contoso Finance team decided to accrue the revenue based on the completed contract method.
1. **Implementation** – Fixed price. The Contoso Finance team decided to accrue the revenue based on the completed percentage method.
1. **Post go-live support** – Fixed Price. The Contoso Finance team decided to accrue the revenue based on the straight line method.

In Project Operations on Dataverse, a new project and a new project contract are created for the customer.

The following illustration shows the project that's created in Dataverse. Multiple tasks are associated with this project.

![Summary tab of the project page for the Business Software Implementation example project, showing the different project stages.](../media/DataverseProject.png)

The following illustration shows the project contract that's created in Dataverse.

![Summary tab of the project contract page for the example project.](../media/DataverserContract.png)

The following illustration shows the project contract lines that are created in Dataverse. Four contract lines are created, one for each phase of the project. Each contract line uses the **Fixed price** billing method.

![Lines on the Contract Lines tab of the project contract page for the example project.](../media/Dataversecontractlines.png)

The following illustration shows the fixed price revenue estimate projects in Dynamics 365 Finance. For each project contract line that was created in Dataverse (as shown in the previous illustration), one fixed price revenue estimate project is created in Dynamics 365 Finance.

![Projects on the Fixed price revenue estimate projects page in Dynamics 365 Finance.](../media/FinanceRevRecProjects.png)

The following illustration show the **Revenue projects** page for the project's **Implementation** phase. On this page, set the **Default project** and **Project cost and revenue profile** fields. A default project is required to post the accrued revenue amounts that affect the project subledger. A project cost and revenue profile is required to identify the revenue recognition accounting rule that's applicable to the revenue project.

![Revenue projects page for the Implementation phase of the example project.](../media/FinanceRevRecProjectdetails.png)

## Recommended content

- [Project contract lines overview](../pro/sales/manage-contract-values-project-based-sales.md) – This article provides an overview of project contract lines.
- [Map projects and tasks to a project contract line](../pro/sales/mapping-projects-tasks-contract-line-sales.md) – This article provides an overview of mapping projects and tasks to a project contract line.
- [Manage revenue estimates](rev-rec-completed-contract-method.md) – This article provides an overview of managing and running the revenue recognition estimates.
