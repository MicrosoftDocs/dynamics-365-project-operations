---
title: Create an invoice schedule on a project-based contract line
description: This article provides information about how to create invoice schedules and milestones on contract lines. 
author: rumant
ms.date: 10/17/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Create an invoice schedule on a project-based contract line 

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

You can an invoice schedule to a  project-based contract line. Invoicing is only allowed after the contract is won to and you are creating a project contract. An invoice schedule allows draft invoices for a project-based contract line to be automatically created. If however, you only manually create invoices, you can skip creating invoice schedules on contract lines.

## Create a time and material invoice schedule for a contract line

When a project-based contract line has a time and material billing method, you can create a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **Invoice frequencies** and set up an invoice frequence.
2. Go to the project contract record, and on the **Summary** tab, in the **Requested Delivery Date** field, select a date.
3. Open the **Time and Material** contract line that you are making the date-based invoice schedule for. 
4. On the **Invoice Schedule** tab, select the billing start date and the invoice frequency.
5. On the subgrid, select **Generate Invoice Schedule**. The invoice schedule is generated with the **Invoice Run Date**, **Transaction Cutoff Date** and **Run Status** fields set as follows:

    - **Invoice Run Date**: This date is dictated by the invoice frequency.
    - **Transaction Cutoff Date**: The day before the invoice run date.
    - **Run Status**: Automatically set to **Not Run**. When the automatic invoice creation job runs for a certain invoice run date, this field is updated to **Run Successful** or **Run Failed**.

## Create a fixed price invoice schedule for a contract line

When the contract line has a fixed billing method, you can create a milestone-based invoice schedule. 

> [!NOTE]
> Milestones can't be created on a contract line if there is no project mapped to the contract line.

Complete the following steps to generate a milestone-based invoice schedule for a fixed set of equally distributed milestones for the calendar period.

1. Go to **Settings** > **Invoice frequencies** and set up an invoice frequence.
2. Go to the project contract record, and on the **Summary** tab, in the **Requested Delivery Date** field, select a date.
3. Open the **Fixed Price** contract line that you are creating the milestone schedule for. On the **Billing Milestones** tab, select the billing start date and the invoice frequency. 
4. On the subgrid, select **Generate Periodic Milestones**. The  invoice schedule is generated with the **Milestone Name**, **Milestone Date**, and **Milestone Amount** fields set as follows:

    - **Milestone Name**: This name is dictated by the invoice frequency.
    - **Milestone Date**: This date is dictated by the invoice frequency.
    - **Milestone Amount**: This amount is calculated by dividing the contract amount on the contract line by the number of milestones as dictated by the frequency, billing start, and requested delivery dates.

    If the contract line has a value in the **Estimated Tax amount** field, then this field is also apportioned to each milestone equally when generating periodic milestones.

Billing milestones should equal the contracted value of the contract line. If they don't, you will receive an  error on the **Contract Line** page. You can fix the error by verifying that the billing milestones total the contracted value of the line by creating, editing, or deleting milestones. After the changes are made, refresh the page to remove the error.

### Manually create milestones

You can generate fixed price milestones manually when they are not periodically split. Complete the following steps to manually create a milestone.

1. Open the fixed price contract line that you are creating a milestone for, and on the **Invoice Schedule** tab, on the subgrid, select **+ Create new Contract line milestone**. 
2. On the **Milestone Creation** page, enter the required information based on the following table.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Milestone Name | Quick Create | Text field for the name of the milestone. | This is carried over to the project contract line milestone and the invoice. |
| Project Task | Quick Create | If the milestone is tied to project task, use this reference to add custom logic to set the milestone status based on the task status. | The application, doesn't have any downstream impact of this reference to a task. |
| Milestone Date | Quick Create | Set the date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This is carried over to the project contract line milestone and the invoice. |
| Invoice Status | Quick Create | When a milestone is created, this status is always set to **Not Ready for Invoicing** or **Not Started**. | This is carried over to the project contract line milestone and the invoice. |
| Line Amount | Quick Create | Amount or value of the milestone that will be invoiced to the customer. | This is carried over to the project contract line milestone and the invoice. |
| Tax | Quick Create | The tax amount applied on the milestone. | This is carried over to the project contract line milestone and the invoice. |

3. Select **Save and Close**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]