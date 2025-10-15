---
title: Use billing schedules with projects using Fee transactions
description: Learn about the Billing schedules with projects feature using fee transactions, which lets you set up a billing schedule that has a project ID and invoice it through a project invoice proposal.
author: mukumarm
ms.author: mukumarm
ms.topic: how-to
ms.date: 10/15/2025
ms.reviewer: johnmichalak
audience: Application User
ms.search.region: Global
ms.search.validFrom: 2025-10-15
ms.search.form:  
ms.dyn365.ops.version: 10.0.46
---

# Use billing schedules with projects by using fee transactions

Subscription billing enables organizations to manage recurring billing through billing schedules. 
Projects help you plan, create, manage, control, and complete customer-focused work for your organization. On some time-and-material projects, a customer might need to be billed on a recurring basis for all or part of the project.

This feature lets you create billing schedules for **projects** by using **fee transactions**, extending the existing functionality that supports **sales order** generation for projects. By using fee transactions, 
the system can generate **work-in-progress (WIP)** and **accrual-based** financial entries, particularly in scenarios where **project customer invoices** are issued at a later stage—after the billing processes run to produce the necessary source documents.

> [!NOTE]
> Billing schedules with projects are available only in Microsoft Dynamics 365 Project Operations for manufacturing based deployments.
>
## Prerequisites

### Minimum version required
To use the feature for Project Operations for manufacturing deployments, you need the following versions:

**Dynamics 365 Finance** version 10.0.46 or later

### Enable features
**Activate** the following features by using the **Feature management** workspace:
* Subscription billing
* Recurring contract billing
* Billing schedules and deferrals with projects
* Enable project fee journals to support subscription billing for Project Operations for manufacturing

### Enable project stage rules
1. Go to **Project management and accounting \> Setup \> Project management and accounting parameters**.
1. On the **Project stage** tab, select a stage, and then select a value in the **Project stage rules** field. Project stage rules for creating a billing schedule on a time-and-material project are added.
1. Set the **Create billing schedule** option to **Yes** to create a billing schedule that's linked to a project in the selected project stage.

## Set up default parameters for fee transactions

To automatically generate billing schedules for project fee transactions, configure the relevant parameters in the **Project Management and Accounting Parameters** settings.

1. Go to **Subscription billing** > **Setup** > **Project Management and Accounting Parameters**.
1. In the **General** tab, set **Invoice transaction type** as **Project fee journal**.
1. In **Posting options**, configure the following settings based on your billing and invoicing requirements:

* **Create project fee journal**: Automatically generates fee transactions. You manually create project invoices later.
* **Show posting invoice or Create invoice proposal page**: Generates both fee transactions and project invoice proposals. You can defer posting invoices and complete them later.
* **Post invoice automatically**: Generates fee transactions and posts the invoice proposals immediately, completing both actions in a single step.
   
## Create a billing schedule from a project

To create a billing schedule directly from a time-and-material project, follow these steps.

1. Go to **Project management and accounting** > **Projects** > **All projects**.
1. On the **All projects** page, select a project.
1. On the Action Pane, on the **Manage** tab, select **New**, then select **Subscription billing \> Billing schedule**. The **Create billing schedule** page opens and includes the standard options for creating a billing schedule.
1. Select the **Billing schedule** group. By default, the customer account, customer name, project, and funding source are entered from the project. If there's more than one funding source (customer or grant) on the project contract, select the funding source for the billing schedule. This funding source is set as the invoice account.
1. Optional: Set the **End user account** and **End user name** fields.
1. Set the **Billing start date** and **Number of periods** fields. The **Billing end date** value is automatically calculated, but you can also enter a value.
1. Select **OK** to create the billing schedule.

The **All billing schedules** page displays the newly created billing schedule. By default, the **Project ID**, **Project name**, **Project contract ID**, and **Funding source** values on the billing schedule header are entered from the project. 
By default, the payment terms, payment schedule, and currency come from the funding source. You can change the project fields until you add billing schedule lines. **Invoice transaction type** comes from **Project management and accounting parameters** by default.
When you use a project on a billing schedule, the **Invoice transaction type** field is set to **Project fee journal** or **Sales order**.

## Billing schedule lines

If you set the **Invoice Transaction Type** to **Project Fee Journal**, the grid includes fields such as Fee Category and other related fee-specific attributes. If you select **Sales order**, the grid displays item-related order line details instead.

You can modify the **Invoice Transaction Type** until you create billing schedule lines, providing flexibility during the setup phase. When you invoice a billing schedule line that has a project by using the **Generate invoice** process, the system creates a **Project fee journal** that includes all the billing schedule lines.

The **Billing schedule lines** grid displays details based on the value you select in the **Invoice Transaction Type** field on the billing schedule header:

If you add a project to a billing schedule header, the system enters it by default on the billing schedule line on the **Project** tab. By default, the system enters the **Project ID**, **Category**, **Line property**, and **Sales tax** values from the project. 
When a billing schedule line has a project, you can only add service items and non-stock items to it. You can add billing schedule lines without the project ID.

To create billing schedule lines of type **Fee**, follow these steps.
1. Go to **Subscription billing** > **Recurring contract billing** > **Billing schedules** > **All billing schedules**.
1. Select the existing billing schedule related to the project or create a new billing schedule by selecting **+ New**.
1. On the Billing schedule header, select **Project fee journal** in the **Invoice transaction type**.
1. On the Billing schedule lines, select **+ New** to create a new billing line.
1. Select the **Fee** type category in the category field, enter the **unit price** and other details.
1. On the project tab for the lines, select the tax and item tax group.
1. On the financial dimensions tab, review the financial dimensions.

> [!NOTE]
> If the **Generate invoice** process doesn't show billing schedule lines, verify that the following requirements are met:
>
> - If you mark unbilled revenue for the billing schedule line, you must complete the **Create journal entry** process.
> - On the **Billing schedule** header, on the **Address** tab, you must define a bill-to address for the customer.
> - The billing schedule or billing schedule line must not have an **On hold** status.
> - On the **Project management and accounting parameters** page, you must set the project stage to one that can be invoiced.

## Viewing a billing schedule from a project or a project contract

To view a billing schedule, follow these steps.

1. On the **All projects** page, select a project.
1. Select **Manage**, select **Related information**, then select **Subscription billing \> Billing schedules**. The **All billing schedules** page shows billing schedules that you created for the selected project.
1. On the **Project contracts** page, select **Maintain**, then, under **Related information**, select **Subscription billing \> Billing schedules**. The **All billing schedules** page shows any billing schedules that you created for the project contract.

Learn more about **Billing schedule with projects** [Billing schedule with projects](/dynamics365/finance/accounts-receivable/sb-bill-sched-project).

Learn more about **Generate invoices from billing schedules** [Generate invoices from billing schedules](/dynamics365/finance/accounts-receivable/sb-generate-invoice).
