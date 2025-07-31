---
title: Enable revenue recognition based on contract standalone selling price (preview)
description: Learn about revenue recognition for fixed-price projects in Microsoft Dynamics 365 Project Operations, using the standalone selling price assigned to each contract line.
author: mukumarm
ms.date: 8/1/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak 
ms.author: mukumarm

---

# Enable revenue recognition based on contract standalone selling price (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

In revenue recognition, fixed-price billing arrangements are typically defined using billing milestones to establish the contract value. However, customers may require a separate calculation for contract value that's independent of billing milestones. This requirement is particularly true in scenarios where additional effort or resources are needed to complete a fixed-price project or when a contract line is subject to a discount.

This feature enables you to track the **Standalone selling price** for each contract line item. It's utilized in the revenue allocation process, where revenue is distributed proportionally based on the ratio of each line item's **Standalone selling price** to the **Total contract standalone selling price**.

To use this feature, activate **Contract line based revenue recognition**, **Separate contract value from billing milestones**, and provide a **Contract variance account** in **Project management and accounting parameters** on the **Revenue recognition** tab.

When this feature is enabled, **Dynamics 365 Finance** generates revenue recognition based upon standalone selling price and proportioned revenue considering the project contract value. All older projects or revenue recognition projects can be managed.

> [!NOTE]
> This feature is dependent on **Contract line-based revenue recognition** and is applicable only when revenue recognition is calculated exclusively in the **Accounting currency**.

## Prerequisites

To use revenue recognition based on contract standalone selling price, the following prerequisites must me met.

### Minimum versions required

To use the feature for Dynamics 365 Project Operations integrated deployments, you must have the following versions:

- **Dynamics 365 Finance version** - 10.0.45 update 69, Application suite version 10.36.2771 or later
- **Project Operations Dataverse version** - 4.145.0.X or later

### Run dual-write maps

This section provides information about the specific maps that are required.

| Dual-write map        | Version  |
|-----------------------|-------------------|
| Project contract lines (salesorderdetails) | 1.0.0.2 |


## Project contract lines

In this section, you will learn how to:

- Add a standalone selling price on contract lines.
- Review project contracts for contract lines.
- Review fixed price revenue estimate projects.
- Review revenue recognition projects.
- Calculate revenue recognition
- Eliminate the completed project

### Add a standalone selling price on contract lines

To generate the revenue recognition with standalone selling price for each contract line, enter the standalone selling price for each contract line in Project Operations.

To generate the revenue recognition with standalone selling price, follow these steps.

1. In **Project Operations**, go to the **Sales** area.
1. Open **Project contracts** form.
1. Select **New** to create a new project contract.
1. Enter the **Name**, **Customer**, **Product price list**, and other required details.
1. Select **Save**.
1. Go to the **Contract lines** tab.
1. Select **New** and create a new contract line.
1. Select the **Fixed price** billing method and enter a **standalone selling price** for the contract line.
1. To save the contract line, select **Save**.
1. Go to the **Invoice schedule** tab and create milestones.

### Review project contracts for contract lines

To review the project contract lines or update other details in Finance, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Projects** \> **Project contracts**.
1. On the Action pane, select **Show default accounting**.
1. Select the contract line in the drop-down list view the **standalone selling price** and enter the **default financial dimensions** that are applicable to the contract line.
1. If the **Straight line revenue recognition** principal is applied on the revenue recognition project for the selected contract line, specify the start date and end date. The start date and end date are used to calculate the number of days that are required for the **Straight line revenue recognition** principal.

## Review fixed price revenue estimate projects

When you create a project contract line that has the following attributes in Project Operations on Dataverse, the system automatically creates a fixed price revenue estimate project. 

The information in the project is based on these attributes.

- A fixed price billing method
- An associated project
- At least one milestone is defined on the **Invoice schedule** tab of the **Project contract line** page.

### Review revenue recognition projects

To review fixed price revenue estimate projects, follow these steps.

1. In Finance, go to **Project management and accounting** \> **Projects** \> **Fixed price revenue estimate projects**.
1. Select the revenue project you want to view, and then double-tap (or double-click) the **Estimate project ID** value.
1. Validate that the **Separate Contract Value from billing milestone** option is **enabled** by default. Revenue recognition is calculated using the **separate contract value allocation method**. You may choose to disable this option; however, you must ensure the option is consistently disabled across all contract lines.
1. In the header, select the **Default project** used to post the estimated revenue recognition amount. All required financial postings are generated for the project defined in the revenue recognition project header. Finance retrieves the financial dimensions from the project and uses them to record the financial transactions to revenue recognition.
1. In the header, select the cost template. This template is used to do the required calculations, such as completed percentage, completed contract, or straight line.
1. Select the **Contract line** tab. There should be one contract line in the **Selected contract lines** grid. This line serves as the default contract line for which the revenue recognition project is created.
1. To change the association, select other contract lines, and add them to the Selected contract lines grid. If multiple contract lines are selected in this grid, the percentage completion and revenue estimates are calculated together for all selected **contract lines**.

    > [!NOTE]
    > For the **Straight line revenue recognition** principal, only one contract line is applicable to each revenue recognition project. Therefore, when you use the **Straight line revenue recognition** principal, you can't add multiple contract lines for a single revenue recognition project.

The **Project cost**, **Revenue profile**, **Cost template**, and **Period code** fields can be set manually. If they aren't set manually, the default values are entered during the first estimate calculation for the project using the rules that are configured for the project cost and revenue profiles.

### Calculate revenue recognition

To calculate the revenue recognition based upon standalone selling price for contract lines, new fields **Contract standalone selling price** and **Total contract standalone selling price** are added.

- **Contract standalone selling price** is automatically derived from the contract lines. If multiple contract lines are associated with the revenue recognition project, the system aggregates the standalone selling prices from all lines and displays the total on the form.
- **Total contract standalone selling price** represents the sum of the standalone selling prices for all contract lines linked to the project contract.
- **Accrued revenue** is calculated by using the following formula:
  - **Allocated revenue** = (Contract Standalone Selling Price/Total Contract Standalone Selling Price) * Total contract value where **Total contract value** is the sum of milestones for the entire project contract.
  - **Accrued revenue** = Allocated revenue * percentage complete.
    
For project contracts in **foreign currency**, the **Contract standalone selling price** and **Total contract standalone selling price** are calculated using the exchange rate applicable on the revenue calculation date. In contrast, if it isn't billed yet, the **Total Contract Value** (milestone amount) is determined using the exchange rate for each milestone, and the invoice exchange rate if it was billed.

### Eliminate the completed project

Once the project contract or contract line work is **complete**, then revenue recognition project needs to be **eliminated**. During the **Elimination** process, if there's a variance between the posted accrued revenue and the invoiced revenue the differential is posted to the **contract variance account**. Financial dimensions are fetched from the project or the contract line based upon the financial dimension configurations.

## Example scenario

Contoso systems awarded one contract to implement business applications for one of its customers. Per the agreement, the whole implementation is divided into the following phases. For each phase, the Project Manager has completed the estimation.


| Contract line         | Milestone amount  | Standalone selling price  | Allocated revenue (Standalone selling price/Total standalone selling price for contract)*Total contract amount| Estimated cost
|-----------------------|-------------------|---------------------------| ------------------| ------------------|
| License Fee           | $ 50,000.00       | $ 100,000.00               | $ 90,000.00 (100,000/500,000)*450,000| $ 60,000 |
| Implementation Fee    | $ 400,000.00      | $ 400,000.00               | $ 360,000.00 (400,000/500,000)*450,000|$ 240,000 |

As revenue recognition is configured for each contract line, two revenue recognition projects are created in Finance, one revenue recognition project for each line. The project accountant configures the financial dimension for each project or for each contract line based upon organization policies.

In the subsequent months, consultants record timesheets and other project-related expenses in Project Operations. These entries are then financially posted in Finance. The project accountant executes the revenue recognition process to assess project progress, calculate accrued revenue, and post the corresponding financial transactions.

### Revenue recognition for period 1

| Revenue Recognition project | Contract amount   | Standalone selling price  | Total standalone selling price| Total contract value (Milestone) | Allocated revenue | Cost for the period | Percentage complete (Total cost/Estimated cost) | Accrued revenue for the month (% complete * Allocated revenue) |
|-----------------------|-------------------|---------------------------| ------------------| ------------------|-------------------|---------------------------| ------------------| ------------------|
| License Fee           | $ 50,000.00       | $ 100,000.00               | $ 500,000 | $ 450,000 | $90,000 |  $ 45,000   | 75.00% | $67,500 |
| Implementation Fee    | $ 400,000.00      | $ 400,000.00               | $ 500,000 | $ 450,000 | $360,000 | $ 120,000  | 50.00% | $180,000|

### Revenue recognition for period 2

| Revenue Recognition project | Contract amount   | Standalone selling price  | Total standalone selling price| Total contract value (Milestone) | Allocated revenue | Cost for the period | Percentage complete (Total cost/Estimated cost) | Accrued revenue for the month (% complete * Allocated revenue) |
|-----------------------|-------------------|---------------------------| ------------------| ------------------|-------------------|---------------------------| ------------------| ------------------|
| License Fee           | $ 50,000.00       | $ 100,000.00               | $ 500,000 | $ 450,000 | $90,000 |  $ 15,000   | 100.00% | $22,500 |
| Implementation Fee    | $ 400,000.00      | $ 400,000.00               | $ 500,000 | $ 450,000 | $360,000 | $ 60,000  | 75.00% | $90,000|

### Revenue recognition for period 3 

| Revenue Recognition project | Contract amount   | Standalone selling price  | Total standalone selling price| Total contract value (Milestone) | Allocated revenue | Cost for the period | Percentage complete (Total cost/Estimated cost) | Accrued revenue for the month (% complete * Allocated revenue) |
|-----------------------|-------------------|---------------------------| ------------------| ------------------|-------------------|---------------------------| ------------------| ------------------|
| License Fee           | $ 50,000.00       | $ 100,000.00               | $ 500,000 | $ 450,000 | $90,000 |  $ 0   | 100.00% | $0 |
| Implementation Fee    | $ 400,000.00      | $ 400,000.00               | $ 500,000 | $ 450,000 | $360,000 | $ 60,000  | 100.00% | $90,000|

At the **end of Period 3**, after all deliverables are completed and accepted by the customer, the project accountant initiates the elimination of the revenue recognition project. During the elimination posting process, if a variance exists between the milestone or invoice amount and the accrued revenue posted for each contract line, the system posts the difference to the contract variance account configured in the Project Management and Accounting parameters.

In the previous example, for the license fee, - $40,000—representing the difference between the total accrued amount posted and the milestone amount—is posted to the contract variance account. 

Similarly, for the implementation fee, $40,000—representing the same type of variance—is also posted to the contract variance account.

## Related information

- [Project contract lines overview](../pro/sales/manage-contract-values-project-based-sales.md) – This article provides an overview of project contract lines.
- [Map projects and tasks to a project contract line](../pro/sales/mapping-projects-tasks-contract-line-sales.md) – This article provides an overview of mapping projects and tasks to a project contract line.
- [Manage revenue estimates](rev-rec-completed-contract-method.md) – This article provides an overview of managing and running the revenue recognition estimates.
- [Manage revenue recognition for contract lines](Revenuerecogntionforcontractlines.md) – This article provides an overview of revenue recognition for contract lines.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
