---
title: Billing schedules with projects
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
Subscription billing enables organizations to manage recurring billing through billing schedules. 
Projects help you plan, create, manage, control, and complete customer-focused work for your organization. On some time-and-material projects, a customer might have to be billed on a recurring basis for all or part of the project.

This feature enables the creation of billing schedules for **projects** using **fee transactions**, extending the existing functionality that supports **sales order** generation for projects. By leveraging fee transactions, 
the system can generate **work-in-progress (WIP)** and **accrual-based** financial entries, particularly in scenarios where **project customer invoices** are issued at a later stage—after the billing processes have been executed to produce the necessary source documents.

> [!NOTE]
> Billing schedules with projects are available only in Microsoft Dynamics 365 Project Operations for manufacturing based deployments.
>
## Prerequisite

### Minimum version required
To use the feature for Project Operations for manufacturing deployments, you must have the following versions:

**Dynamics 365 Finance** version 10.0.46 or later

### Enable features
**Activate** the following features using **Feature management** workspace:
* Subscription billing
* Recurring contract billing
* Billing schedules and deferrals with projects
* Enable project fee journals to support subscription billing for Project Operations for manufacturing

### Enable project stage rules
1. Go to **Project management and accounting \> Setup \> Project management and accounting parameters**.
2. On the **Project stage** tab, select a stage, and then select a value in the **Project stage rules** field. Project stage rules for creating a billing schedule on a time-and-material project are added.
3. You must set the **Create billing schedule** option to **Yes** to create a billing schedule that's linked to a project in the selected project stage.

## Setup default parameters for fee transactions

To enable the automatic generation of billing schedules for project fee transactions, configure the relevant parameters within the **Project Management and Accounting Parameters** settings.

1. Goto **Subscription billing** > **Setup** > **Project Management and Accounting Parameters**.
2. In the **General** tab, set **Invoice transaction type** as **Project fee journal**.
3. In the **Posting options**, configure the following settings based on your billing and invoicing requirements:

* **Create project fee journal**: Generates fee transactions automatically, while project invoices are created manually at a later stage.
* **Show posting invoice or Create invoice proposal page**: Generates both fee transactions and project invoice proposals. Posting of invoices can be deferred and completed later.
* **Post invoice automatically**: Generates fee transactions and posts the invoice proposals immediately, completing both actions in a single step.
   
## Create a billing schedule from a project

To create a billing schedule directly from a time-and-material project, follow these steps.

1. Goto **Project management and accounting** > **Projects** > **All projects**.
2. On the **All projects** page, select a project.
3. On the Action Pane, on the **Manage** tab, select **New**, and then select **Subscription billing \> Billing schedule**. The **Create billing schedule** page is opened and includes the standard options for creating a billing schedule.
4. Select the **Billing schedule** group. By default, the customer account, customer name, project, and funding source are entered from the project. If there's more than one funding source (customer or grant) on the project contract, select the funding source for the billing schedule. This funding source will be set as the invoice account.
5. Optional: Set the **End user account** and **End user name** fields.
6. Set the **Billing start date** and **Number of periods** fields. The **Billing end date** value is automatically calculated, but you can also enter a value.
7. Select **OK** to create the billing schedule.

The **All billing schedules** page shows the newly created billing schedule. By default, the **Project ID**, **Project name**, **Project contract ID**, and **Funding source** values on the billing schedule header are entered from the project. 
By default, the payment terms, payment schedule, and currency are entered from the funding source. The project fields can be changed until billing schedule lines are added. **Invoice transaction type** is defaulted from **Project management and accounting parameters**.
When a project is used on a billing schedule, the **Invoice transaction type** field is set to **Project fee journal** or **Sales order**.

## Billing schedule lines

If the **Invoice Transaction Type** is set to **Project Fee Journal**, the grid includes fields such as Fee Category and other related fee-specific attributes. If **Sales order** is selected, the grid displays item-related order line details instead.

Users can modify the **Invoice Transaction Type** until billing schedule lines are created, providing flexibility during the setup phase. When a billing schedule line that has a project is invoiced by using the **Generate invoice** process, a **Project fee journal** is created considering all the billing schedule lines.

The **Billing Schedule Lines grid** displays details based on the value selected in the **Invoice Transaction Type** field on the billing schedule header:

If a project is added to a billing schedule header, it will be entered by default on the billing schedule line on the **Project** tab. By default, the **Project ID**, **Category**, **Line property** and **Sales tax** values are entered from the project. 
When a billing schedule line has a project, only service items and non-stock items can be added to it. Billing schedule lines can be added without the project ID.

To create a billing schedule lines of type **Fee**, follow these steps.
1.  Goto **Subscription billing** > **Recurring contract billing** > **Billing schedules** > **All billng schedules**.
2.  Select the existing billing schedule related to project or create a new billing schedule using **+ New**.
3.  On the Billing schedule header, select **Project fee journal** in the **Invoice transaction type**.
4.  On the Billing schedule lines, Ciick **+ New** to create a new billing line.
5.  Select the **Fee** type category in the category field, enter **unit price** and other details.
6.  On the project tab at the lines, select the tax and item tax group.
7.  On the financial dimensions tab, validate the financial dimensions.

> [!NOTE]
> If the **Generate invoice** process doesn't show billing schedule lines, verify that the following requirements are met:
>
> - If unbilled revenue is marked for the billing schedule line, the **Create journal entry** process must be completed.
> - On the **Billing schedule** header, on the **Address** tab, a bill-to address must be defined for the customer.
> - The billing schedule or billing schedule line must not have an **On hold** status.
> - On the **Project management and accounting parameters** page, the project stage must be set to one that can be invoiced.

## Viewing a billing schedule from a project or a project contract

To view a billing schedule, follow these steps.

1. On the **All projects** page, select a project.
2. Select **Manage**, select **Related information**, and then select **Subscription billing \> Billing schedules**. The **All billing schedules** page shows billing schedules that have been created for the selected project.
3. On the **Project contracts** page, select **Maintain**, and then, under **Related information**, select **Subscription billing \> Billing schedules**. The **All billing schedules** page shows any billing schedules that have been created for the project contract.

Learn more about **Billing schedule with projects** [Billing schedule with projects](/dynamics365/finance/accounts-receivable/sb-bill-sched-project).

Learn more about **Generate invoices from billing schedules** [Generate invoices from billing schedules](/dynamics365/finance/accounts-receivable/sb-generate-invoice).
