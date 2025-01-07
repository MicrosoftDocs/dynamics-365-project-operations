---
title: Create invoice schedules on a project-based contract line
description: This article provides information about how to create invoice schedules and milestones on contract lines. 
author: mukumarm
ms.date: 12/27/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Create invoice schedules on a project-based contract line

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

You can add an invoice schedule to a project-based contract line. Invoicing is allowed only after the contract is won and you're creating a project contract. An invoice schedule enables draft invoices for a project-based contract line to be automatically created. However, if you only manually create invoices, you can skip the creation of invoice schedules on contract lines.

## Create a time and material invoice schedule for a contract line

When a project-based contract line has a time and material billing method, you can create a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **Invoice frequencies** and set up an invoice frequence.
1. Go to the project contract record, and then, on the **Summary** tab, in the **Requested Delivery Date** field, select a date.
1. Open the **Time and Material** contract line that you're making the date-based invoice schedule for. 
1. On the **Invoice Schedule** tab, select the billing start date and the invoice frequency.
1. On the subgrid, select **Generate Invoice Schedule**. The invoice schedule is generated, and the **Invoice Run Date**, **Transaction Cutoff Date** and **Run Status** fields are set in the following way:

    - **Invoice Run Date**: This date is dictated by the invoice frequency.
    - **Transaction Cutoff Date**: The day before the invoice run date.
    - **Run Status**: Automatically set to **Not Run**. When the automatic invoice creation job runs for a certain invoice run date, this field is updated to **Run Successful** or **Run Failed**.

## Create a fixed price invoice schedule for a contract line

When the contract line has a fixed billing method, you can create a milestone-based invoice schedule. 

> [!NOTE]
> Milestones can be created only on contract lines that a project is mapped to.

Complete the following steps to generate a milestone-based invoice schedule for a fixed set of equally distributed milestones for the calendar period.

1. Go to **Settings** > **Invoice frequencies** and set up an invoice frequence.
1. Go to the project contract record, and then, on the **Summary** tab, in the **Requested Delivery Date** field, select a date.
1. Open the **Fixed Price** contract line that you're creating the milestone schedule for. On the **Billing Milestones** tab, select the billing start date and the invoice frequency. 
1. On the subgrid, select **Generate Periodic Milestones**. The invoice schedule is generated, and the **Milestone Name**, **Milestone Date**, and **Milestone Amount** fields are set in the following way:

    - **Milestone Name**: This name is dictated by the invoice frequency.
    - **Milestone Date**: This date is dictated by the invoice frequency.
    - **Milestone Amount**: This amount is calculated by dividing the contract amount on the contract line by the number of milestones as dictated by the frequency, billing start, and requested delivery dates.

    If the contract line has a value in the **Estimated Tax amount** field, then this field is also apportioned to each milestone equally when generating periodic milestones.

Billing milestones must equal the contracted value of the contract line. Otherwise, you receive an error on the **Contract Line** page. You can fix the error by creating, editing, or deleting milestones to ensure that the total billing milestones equal the contracted value of the line. After the changes are made, refresh the page to remove the error.

### Manually create milestones

You can manually generate fixed price milestones when they aren't periodically split. Follow these steps to manually create a milestone.

1. Open the fixed price contract line that you're creating a milestone for, and then, on the **Invoice Schedule** tab, on the subgrid, select **Create new Contract line milestone**. 
1. On the **Milestone Creation** page, enter the required information, based on the following table.

    | Field | Location | Description | Downstream impact |
    | --- | --- | --- | --- |
    | Milestone Name | Quick Create | A text field for the name of the milestone. | This field is carried over to the project contract line milestone and the invoice. |
    | Project Task | Quick Create | If the milestone is tied to a project task, use this reference to add custom logic that sets the milestone status based on the task status. | This reference to a task has no downstream impact in the application. |
    | Milestone Date | Quick Create | Set the date when the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This field is carried over to the project contract line milestone and the invoice. |
    | Invoice Status | Quick Create | When a milestone is created, this status is always set to **Not Ready for Invoicing** or **Not Started**. | This field is carried over to the project contract line milestone and the invoice. |
    | Line Amount | Quick Create | The milestone amount or value that is invoiced to the customer. | This field is carried over to the project contract line milestone and the invoice. |
    | Tax | Quick Create | The tax amount that is applied on the milestone. | This field is carried over to the project contract line milestone and the invoice. |

1. Select **Save and Close**.

## Create a progress billing invoice schedule for a contract line

*Progress billing* lets you invoice customers based on the percentage of work that is completed instead of fixed milestones or time and materials. Progress billing is useful in long-term projects or contracts where the work spans months or years.

To use this feature for Microsoft Dynamics 365 Project Operations non-stocked/resource-based scenarios, ensure that the following requirements are met:

1. You're using Project Operations Dataverse version 4.123.0.x or later.
1. You're using Dynamics 365 Finance version 10.0.43 or later.
1. Activate the **Enable Progress billing on Project Operations for resource based/non-stocked scenarios** feature in the **Feature Management** workspace in Finance, and enable **Progress based billing** in Dataverse.
1. Run the dual-write map for **Progress billing milestone header**, version 1.0.0.0 or later. 

When the contract line uses a fixed billing method, you can select **Progress-based** in the **Invoice schedule type** field. This field enables the creation of milestone headers on the **Invoice schedule** tab. For each header, a default milestone is automatically generated. During the invoicing process, you can specify the **Next invoice percentage** or **Next invoice amount** value and update the milestone header's invoice status to **Ready for Invoice**.

To generate a progress-based invoice schedule, follow these steps.

1. In Dataverse, go to **Sales** \> **Project contracts**, and select **New**.
1. On the **Project contract lines** tab, select **New project contract line**.
1. In the **Name** field, enter the name of the contract line.
1. In the **Billing method** field, select **Fixed price**.
1. In the **Invoice schedule type** field, select **Progress based**.
1. On the **Invoice schedule** tab, on the subgrid, select **New milestone header**. 
1. On the **Milestone header** page, enter the required information, based on the following table.

    | Field | Location | Description | Downstream impact |
    | --- | --- | --- | --- |
    | Name | Quick Create | A text field for the name of the milestone. | This field is carried over to the project contract line milestone and the invoice. |
    | Task | Quick Create | If the milestone is tied to a project task, use this reference to add custom logic that sets the milestone status based on the task status. | This reference to a task has no downstream impact in the application. |
    | Date | Quick Create | Set the date when the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This field is carried over to the project contract line milestone and the invoice. |
    | Billing Status | Quick Create | When a milestone is created, this status is always set to **Not Ready for Invoicing** or **Not Started**. | This field is carried over to the project contract line milestone and the invoice. |
    | Line Amount | Quick Create | The milestone amount or value that is invoiced to the customer. | This field is carried over to the project contract line milestone and the invoice. |
    | Tax | Quick Create | The tax amount that is applied on the milestone. | This field is carried over to the project contract line milestone and the invoice. |

1. Select **Save and Close**.

To monitor the milestone header and related milestones in Finance, follow these steps.

1. In Finance, go to **Project management and accounting**.
1. Go to **Projects** \> **Project contracts**.
1. On the Action Pane, on the **Maintain** tab, select **Progress billing details**. The page that appears shows the milestone headers together with their associated milestone status.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
