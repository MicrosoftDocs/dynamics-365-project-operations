---
title: Invoice schedules on project quote lines
description: This article provides information about creating invoice schedules and milestones for quote lines.
author: poojafandan
ms.date: 09/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Invoice schedules on project quote lines

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

A project quote line gives the ability to express an invoice schedule. This is optional during the quote phase because the application doesn't support invoicing a project when it's tied to a Quote line. Invoicing is only allowed after the quote is won. The only downstream impact of creating an invoice schedule during the quote phase is this invoice schedule is copied over to the project-based contract line. If you don't create an invoice schedule during the quote phase, you can do so on the project-based contract line.

Overall, the purpose of invoice schedules is to allow for the automatic creation of draft invoices for a project-based contract line. 

## Create a Time and material invoice schedule for a project quote line

When the billing method for a project-based quote line is Time and material, the system generates a date-based invoice schedule. To automatically generate a date-based invoice schedule, complete the following steps.

1. Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
2. On the **Quotes** page, open the Project quote and on the **Summary** tab, set a requested delivery date.
3. Open the time and material quote line that you need to create a date-based invoice schedule for. 
4. On the **Invoice Schedule** tab, select values in the **Billing start** and **Invoice Frequency** fields. 
5. On the subgrid, select **Generate Invoice Schedule**.
6. The application generates the invoice schedule with the **Invoice Run Date**, **Transaction Cutoff Date**, and **Run Status** fields set in the following way:

    - **Invoice Run Date** is set to the date that is dictated based on the invoice frequency.
    - **Transaction cut-off date** is set to the day before the **Invoice Run Date**.
    - **Run Status** is automatically set to **Not Run**. When the automatic invoice creation job runs for a certain invoice run date, it updates this field to either **Run Successful** or **Run Failed**.

## Create a Fixed price invoice schedule for a project quote line

When the project-based quote line has a **Fixed** billing method, you can create a milestone based or progress based invoice schedule. Complete the following steps to automatically generate this schedule for a fixed set of milestones that are equally distributed for the calendar period.
1.	Go to **Settings** > **invoice frequencies** and set up an invoice frequency.
2.	Add a new **Quote line** and give the quote line a name, then select **Fixed price** as the billing method. The field **Invoice schedule type** appears, in which you have option to select **Milestone based** or **Progress based** invoice schedule. 
3.	Once the quote line is created, you can go to **Invoice schedule** tab, select values in the **Billing start** and **Invoice Frequency** fields. 
4.	On the subgrid, select **Generate Periodic Milestones**.

The system generates the invoice schedule with the following milestone information.
•	Milestone Name is set to the date that is dictated based on the invoice frequency.
•	Milestone Date is set to the date that is dictated based on the invoice frequency.
•	Milestone Amount is calculated by dividing the quote amount on the project-based quote line by the number of milestones as dictated by the frequency, billing start, and requested delivery dates.
•	If the quote line has a value in the Estimated Tax Amount field, this field is also apportioned to each milestone equally when generating periodic milestones.

Billing milestones should equal the total quoted value of the project-based quote line. If they aren't equal, an error occurs. You can fix that error by verifying that the billing milestones total the quoted value of the line by either creating, editing, or deleting milestones. After the changes are made, refresh the page.

### Manually create milestones

Fixed price milestones can also be generated manually when they aren't periodically split. To create a milestone manually:

Open the Fixed price quote line where you need to create a milestone. On the **Invoice Schedule** tab, on the subgrid, select **+ Create new quote line milestone** and enter the required information based on the following table.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Milestone name | Quick create | The name of the milestone. | This milestone is propagated to the project contract line milestone and to the invoice |
| Project Task | Quick create | If the milestone is tied to project task, you can use this reference to add custom logic set the milestone status based on the task status. | The application doesn't have any downstream impact of this reference to a task. |
| Milestone date | Quick create | Set the date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This date is propagated to the project contract line milestone and to the invoice. |
| Invoice status | Quick create | When a milestone is created, this status is always set to **Not ready for invoicing**. | This status is propagated to the project contract line milestone and to the invoice. |
| Line Amount | Quick create | Amount or value of the milestone that is invoiced to the customer. | This amount is propagated to the project contract line milestone and to the invoice. |
| Tax | Quick create | Tax amount that is applied to the milestone. | This tax is propagated to the project contract line milestone and to the invoice. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
