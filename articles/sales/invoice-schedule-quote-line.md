---
title: Invoice schedules on project-based quote lines
description: This article provides information about creating invoice schedules and milestones for quote lines.
author: rumant
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Invoice schedules on project-based quote lines

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

A project-based quote line gives the ability to express an invoice schedule. This is optional during the quote phase because the application does not support invoicing a project when it is tied to a Quote line. Invoicing is only allowed after the quote is won. The only downstream impact of creating an invoice schedule during the quote phase, is that this invoice schedule is copied over to the project-based contract line. If you do not create an invoice schedule during the quote phase, you will be able to do so on the project-based contract line.

Overall, the purpose of invoice schedules is to allow for the automatic creation of draft invoices for a project-based contract line. 

## Create a Time and material invoice schedule for a project-based quote line

When the billing method for a project-based quote line is Time and material, the system generates a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
2. On the **Quotes** page, open the Project quote and on the **Summary** tab, set a requested delivery date.
3. Open the time and material quote line that you need to create a date-based invoice schedule for. 
4. On the **Invoice Schedule** tab, select values in the **Billing start** and **Invoice Frequency** fields. 
5. On the subgrid, select **Generate Invoice Schedule**.
6. The application generates the invoice schedule with the **Invoice Run Date**, **Transaction Cutoff Date**, and **Run Status** fields set in the following way:

    - **Invoice Run Date** is set to the date that is dictated based on the invoice frequency.
    - **Transaction cut-off date** is set to the day before the **Invoice Run Date**.
    - **Run Status** is automatically set to **Not Run**. When the automatic invoice creation job runs for a certain invoice run date, it will update this field to either **Run Successful** or **Run Failed**.

## Create a Fixed price invoice schedule for a project-based quote line

When the project-based quote line has a **Fixed** billing method, the system creates a milestone-based invoice schedule. Complete the following steps to automatically generate this schedule for a fixed set of milestones that are equally distributed for the calendar period.

1. Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
2. On the **Quotes** page, open the Project quote and on the **Summary** tab, set a requested delivery date.
3. Open the fixed price quote line that you need to create a milestone schedule for. 
4. On the **Invoice Schedule** tab, select values in the **Billing start** and **Invoice Frequency** fields. 
5. On the subgrid, select **Generate Periodic Milestones**.
6. The application generates the invoice schedule with a milestone name, date, and amount.

    - The milestone name is set to the date that is dictated based on the invoice frequency.
    - The milestone date is set to the date that is dictated based on the invoice frequency.
    - The milestone amount is computed by dividing the quote amount on the project-based quote line by the number of milestones as dictated by the frequency and billing start and requested delivery dates.
    - If the Quote line also has as estimated tax amount, this value is split between each milestone equally when generating periodic milestones.

### Manually create milestones

Fixed price milestones can also be generated manually when they are not periodically split. To create a milestone manually:

Open the Fixed price quote line where you need to create a milestone. On the **Invoice Schedule** tab, on the subgrid, select **+ Create new quote line milestone** and enter the required information based on the following table.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Milestone name | Quick create | The name of the milestone. | This is propagated to the project contract line milestone and to the invoice |
| Project Task | Quick create | If the milestone is tied to project task, you can use this reference to add custom logic set the milestone status based on the task status. | The application, does not have any downstream impact of this reference to a task. |
| Milestone date | Quick create | Set the date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This is propagated to the project contract line milestone and to the invoice. |
| Invoice status | Quick create | When a milestone is created, this status is always set to **Not ready for invoicing**. | This is propagated to the project contract line milestone and to the invoice. |
| Line Amount | Quick create | Amount or value of the milestone that will be invoiced to the customer. | This is propagated to the project contract line milestone and to the invoice. |
| Tax | Quick create | Tax amount that will be applied to the milestone. | This is propagated to the project contract line milestone and to the invoice. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]