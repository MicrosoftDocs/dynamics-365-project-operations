---
title: Revenue recognition for contract lines
description: This topic provides information about contract lines based revenue recognition in Project Operations.
author: mukumarm
ms.date: 03/13/2023
ms.topic: overview
ms.reviewer: johnmichalak 
ms.author: mukumarm

---
# Contract line based revenue recognition with Project operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use **Contract line-based revenue recognition with Project operations,** feature **Enable contract line-based revenue recognition with Project Operations for non-stocked/ resource-based scenarios** should be enabled. Once this feature is enabled, then it can't be disabled further. All the older projects or revenue recognition projects can be managed in an older manner.

Once this feature is enabled then **Dynamics 365 for Finance** generates the revenue recognition for each contract line which is used as a fixed price billing method only.

This feature allows us to recognize the revenue recognition for each contract line associated with the contract. It provides flexibility to define different revenue recognition methods per contract line and **Dynamics 365 for Finance** generates and posts the revenue recognition amounts accordingly.

## Fixed price revenue estimate project with contract line

When you create a project contract line with the following attributes in Dynamics 365 Project Operations on Microsoft Dataverse, the system automatically creates a fixed price revenue estimate project. The information in this project is based on the following:

- A fixed price billing method.
- An associated project.
- At least one milestone defined on the Invoice schedule tab on the Project contract line page.

When the feature **Enable contract line-based revenue recognition with Project Operations for non-stocked/resource-based scenario** is activated, **Dynamics 365 for Finance** generates a fixed-price revenue estimate project for each contract line that utilizes a fixed-price billing method and has defined milestone.

Refer below to know more about **Project contract lines** in **Dataverse** and how contract lines are linked with project tasks.

[Project contract lines overview | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/sales/manage-contract-values-project-based-sales)

This article provides an overview of project contract lines.

[Map projects and tasks to a project contract line | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/sales/mapping-projects-tasks-contract-line-sales)

This article provides an overview of mapping projects and tasks to a project contract line.
## Review project contracts for contract lines

To review the project contract lines or to update addtional details in **Dynamics 365 for finance**, complete the following:

1. In the **Dynamics 365 Finance** environment, go to **Project management and accounting**  \>  **Projects**  \>  **Project contracts**
2. Select **Show default accounting** on the **project contract** action pane.
3. Select the **contract line** from the drop down for defaulting the financial dimensions applicable for the contract line.
4. Specify the **start date** and **end date** if revenue recognition **straight line** principal is applied on the **revenue recognition project** for the selected contract line. **Start date** and **end date** is used to calculate the number of days required for **straight line revenue recognition** principal.

## Review fixed price revenue estimates projects.

To review fixed price revenue estimates projects, complete the following steps:

1. In the **Dynamics 365 Finance** environment, go to **Project management and accounting**  \>  **Projects**  \>  **Fixed price revenue estimate projects**.
2. Select the **Revenue project** that you want to view and double-click the Estimate project ID to open the record and review the details of the project.
3. Select the **Default project** on the header which is required to post the estimated revenue recognition amount. All the required financial postings happened against the default project selected at header. **Financial dimensions** selected on the **default project** is used to post revenue recognition related financial vouchers.
4. Select the **Cost template** on the header. This template is used to do the required calculations like completed percentage, completed contract or straight line.
5. Expand the  **Contract line**  tab. You will see one contract line in the Selected contract lines grid. This is the default contract line for which the revenue recognition project has been created.
6. To change the association, select additional contract lines and add them to the Selected contract lines grid. If multiple contract lines are selected in this grid, the percentage completion and revenue estimates are calculated together for of all selected contract lines.
7. For **straight line** revenue recognition principal, only one contract line is applicable for one **revenue recognition project**. It is not allowed to add multiple contract lines for one revenue recognition project with **straight line** revenue recognition principal.

Project cost, revenue profile, cost template, and the period code can be set manually. If they aren't set manually, the values default during the first estimate calculation for the project using the rules configured for project cost and revenue profiles.

### Example Scenario

Contoso systems awarded one contract to implement Business applications for one of their customers. As per the agreement, the entire implementation is divided into multiple phases as below:

1. **License Fee** – Fixed price. Contoso finance team has decided to accrue revenue based upon straight line method.
2. **Analysis** – Fixed price. Contoso finance team has decided to accrue the revenue based upon completed contract method.
3. **Implementation** – Fixed price. Contoso finance team has decided to accrue the revenue based upon completed percentage method.
4. **Post go-live support** – Fixed Price. Contoso finance team has decided to accrue the revenue based upon straight line method.

In **Dynamics 365 Project Operations** on **Dataverse** a new project and a new project contract is created for the customer.

The following screen displays the project created in **Dataverse.** This project has multiple tasks associated with.
<img width="468" alt="DataverseProject" src="https://user-images.githubusercontent.com/103096040/224676352-90ea97d6-5952-4ffc-b12d-d94c8f0401f5.png">

The following screen displays the project contract created in **Dataverse.**

<img width="468" alt="DataverserContract" src="https://user-images.githubusercontent.com/103096040/224676597-a57557d2-401f-4f2d-b80f-6169416d172f.png">
The following screen displays the project contract lines created in **Dataverse** and all the contract lines are configured as billing method **Fixed price.** 
There are four contract lines created for each phase of the project and each contract line has **Fixed price** billing method.
<img width="468" alt="Dataversecontractlines" src="https://user-images.githubusercontent.com/103096040/224676822-2d80b4b6-b986-452a-940b-65622f1b915d.png">

The following screen displays the **Fixed price revenue estimate projects** in **Dynamics 365 for finance** for each contract line. 
For each contract line as per the screenshot above, there is one **Fixed price revenue estimate project** created in Dynamics 365 for Finance.
<img width="468" alt="FinanceRevRecProjects" src="https://user-images.githubusercontent.com/103096040/224676931-42e65714-cccb-448f-9b68-8dd9db30788b.png">

The following screen displays the **Revenue project** for implementation phase. Select the **Default project** and **Project cost and revenue profile.** 
Default project is required to post the accrued revenue amount which impact the project subledger. Project cost and revenue profile are required to identify the revenue recognition accounting rule applicable for the revenue project.
<img width="468" alt="FinanceRevRecProjectdetails" src="https://user-images.githubusercontent.com/103096040/224677042-438f586c-3070-4532-a996-06c1362f14d2.png">

## Recommended content

[Project contract lines overview | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/sales/manage-contract-values-project-based-sales)

This article provides an overview for project contract lines.

[Map projects and tasks to a project contract line | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/project-operations/pro/sales/mapping-projects-tasks-contract-line-sales)

This article provides an overview of mapping projects and tasks to a project contract line.

[Manage revenue estimates | Microsoft Learn](https://learn.microsoft.com/en-us/dynamics365/project-operations/revenue-recognition/rev-rec-completed-contract-method)

This article provides an overview of managing and executing the revenue recognition estimates.
