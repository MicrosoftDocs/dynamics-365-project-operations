---
title: Create invoice schedules on a project contract line
description: This article provides information about creating invoice schedules and milestones.
author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Create invoice schedules on a project contract line

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

You can attach an invoice schedule on a project-based contract line. Invoicing is only allowed after the contract is won to create a Project contract. Invoice schedules allow draft invoices for a project-based contract line to be created automatically. If you plan to always create invoices manually, you can skip creating invoice schedules on a project-based contract line or a contract line.

## Create a time and material invoice schedule for a project-based contract line

When a project-based contract line has a time and material billing method, you can create a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **Invoice Frequencies** to set up invoice frequency.
2. Open the project contract and on the **Summary** tab, set the requested delivery date.
3. Open the time and material contract line that you want to create a date-based invoice schedule for. 
4. On the **Invoice Schedule** tab, select a billing start date and the invoice frequency. 
5. On the subgrid, select **Generate Invoice Schedule**.

    The system generates the invoice schedule with the following field information:

    - **Invoice Run Date** is set to the date based on the invoice frequency.
    - **Transaction Cut-off Date** is set to the day before the **Invoice Run Date**.
    - **Run Status** is automatically set to **Not Run**. When the automatic invoice creation job runs for a certain **Invoice Run Date**, this field is updated to **Run Successful** or **Run Failed**.

## Create a fixed price invoice schedule for a project-based contract line

When a project-based contract line has a fixed price billing method, you can create a milestone-based invoice schedule. Complete the following steps to automatically generate a milestone-based invoice schedule for a fixed set of milestones that distribute equally for the calendar period. The following steps are applicable for **Invoice Schedule Type** values of **Progress - based** and **Completed Milestones**. 

1. Go to **Settings** > **Invoice Frequencies** to set up invoice frequency.
2. Open the project contract and on the **Summary** tab, set the requested delivery date.
3. Open the fixed price contract line on which you need to create a milestone schedule. 
4. On the **Invoice Schedule (Billing Milestones)** tab, select the billing start date and the invoice frequency. 
5. On the subgrid, select **Generate Periodic Milestones**.

    The system generates the invoice schedule with the following milestone information.

    - **Milestone Name** is set to the date that is dictated based on the invoice frequency.
    - **Milestone Date** is set to the date that is dictated based on the invoice frequency.
    - **Milestone Amount** is calculated by dividing the contract amount on the project-based contract line by the number of milestones as dictated by the frequency, billing start, and requested delivery dates.
    - If the contract line has a value in the **Estimated Tax Amount** field, this field is also apportioned to each milestone equally when generating periodic milestones.

Billing milestones should equal the contracted value of the project-based contract line. If they aren't equal, an error occurs. You can fix that error by verifying that the billing milestones total the contracted value of the line by either creating, editing, or deleting milestones. After the changes are made, refresh the page.

### Manually create milestones

Fixed price milestones can be generated manually when they aren't periodically split. To create a milestone manually, complete the following steps.

1. Open the fixed price contract line on which you want to create a milestone. 
2. On the **Invoice Schedule** tab, on the subgrid, select **+ Create new Contract line milestone**.
3. On the **Milestone Creation** form, enter the required information based on the following table. 

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Milestone Name | Quick Create | Text field for the name of the milestone. | This field is included on the project contract line milestone and the invoice. |
| Project Task | Quick Create | If the milestone is tied to a project task, use this reference to add custom logic and set the milestone status based on the task status. | There isn't a downstream impact of this reference to a task. |
| Milestone Date | Quick Create | The date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This field is included on the project contract line milestone and the invoice. |
| Invoice Status | Quick Create | When the milestone is created, this status is always set to **Not ready for invoicing** or **Not started**. | This field is included on the project contract line milestone and the invoice. |
| Line Amount | Quick Create | The amount or value of the milestone that's invoiced to the customer. | This field is included on the project contract line milestone and the invoice, |
| Tax | Quick Create | The tax amount applied on the milestone. | This field is included on the project contract line milestone and the invoice. |

4. Select **Save and Close**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
