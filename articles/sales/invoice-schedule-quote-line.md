---
title: Invoice schedules on project quote lines
description: This article provides information about creating invoice schedules and milestones for quote lines.
author: poojafandan
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Invoice schedules on project quote lines

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A project quote line can include an invoice schedule. This schedule is optional during the quote phase because the application doesn't support invoicing a project when it's tied to a quote line. You can only invoice after the quote is won. The only downstream impact of creating an invoice schedule during the quote phase is that the application copies this invoice schedule to the project-based contract line. If you don't create an invoice schedule during the quote phase, you can add one on the project-based contract line.

Overall, the purpose of invoice schedules is to allow for the automatic creation of draft invoices for a project-based contract line. 

## Create a Time and material invoice schedule for a project quote line

When the billing method for a project-based quote line is Time and material, the system generates a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
1. On the **Quotes** page, open the Project quote and on the **Summary** tab, set a requested delivery date.
1. Open the time and material quote line that you need to create a date-based invoice schedule for. 
1. On the **Invoice Schedule** tab, select values in the **Billing start** and **Invoice Frequency** fields. 
1. On the subgrid, select **Generate Invoice Schedule**.
1. The application generates the invoice schedule with the **Invoice Run Date**, **Transaction Cutoff Date**, and **Run Status** fields set in the following way:

    - **Invoice Run Date** is set to the date that is dictated based on the invoice frequency.
    - **Transaction cut-off date** is set to the day before the **Invoice Run Date**.
    - **Run Status** is automatically set to **Not Run**. When the automatic invoice creation job runs for a certain invoice run date, it updates this field to either **Run Successful** or **Run Failed**.

## Create a fixed price invoice schedule for a project quote line

When the project-based quote line has a **Fixed** billing method, you can create a milestone-based or progress-based invoice schedule. Complete the following steps to automatically generate this schedule for a fixed set of milestones that are equally distributed for the calendar period.
1.	Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
1.	Add a new **Quote line** and give the quote line a name, and then select **Fixed price** as the billing method. The field **Invoice schedule type** appears, and you can select **Milestone based** or **Progress based** invoice schedule. 
1.	After you create the quote line, go to the **Invoice schedule** tab, and select values in the **Billing start** and **Invoice Frequency** fields. 
1.	On the subgrid, select **Generate Periodic Milestones**.

The system generates the invoice schedule with the following milestone information.
- Milestone Name is set to the date that is dictated based on the invoice frequency.
- Milestone Date is set to the date that is dictated based on the invoice frequency.
- Milestone Amount is calculated by dividing the quote amount on the project-based quote line by the number of milestones as dictated by the frequency, billing start, and requested delivery dates.
- If the quote line has a value in the Estimated Tax Amount field, this field is also apportioned to each milestone equally when generating periodic milestones.

Billing milestones should equal the total quoted value of the project-based quote line. If they aren't equal, an error occurs. You can fix that error by verifying that the billing milestones total the quoted value of the line by either creating, editing, or deleting milestones. After you make the changes, refresh the page.

### Manually create milestones

You can also manually create fixed price milestones when you don't want to split them periodically. To create a milestone manually:

Open the fixed price quote line where you need to create a milestone. On the **Invoice Schedule** tab, select **+ Create new quote line milestone** on the subgrid, and enter the required information based on the following table.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Milestone name | Quick create | The name of the milestone. | This milestone name goes to the project contract line milestone and to the invoice. |
| Project Task | Quick create | If the milestone is tied to project task, use this reference to add custom logic that sets the milestone status based on the task status. | The application doesn't have any downstream impact of this reference to a task. |
| Milestone date | Quick create | Set the date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This date goes to the project contract line milestone and to the invoice. |
| Invoice status | Quick create | When you create a milestone, set this status to **Not ready for invoicing**. | This status goes to the project contract line milestone and to the invoice. |
| Line Amount | Quick create | Amount or value of the milestone that you invoice to the customer. | This amount goes to the project contract line milestone and to the invoice. |
| Tax | Quick create | Tax amount that you apply to the milestone. | This tax goes to the project contract line milestone and to the invoice. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
