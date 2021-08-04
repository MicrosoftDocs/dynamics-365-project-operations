---
title: Subcontract line milestones
description: This topic provides information that will help you create and maintain a milestone based invoice schedule for a subcontract with a vendor.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract line milestones

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract line in Project Operations with a Fixed Price Billing method can specify a milestone-based invoice schedule with the vendor.

Milestones for vendor invoicing can be generated automatically using a set frequency or manually.

## Creating milestone-based invoice schedule automatically for a Subcontract line:

The following steps will automatically generate a milestone-based invoice schedule for a fixed set of milestones that distribute equally for the calendar period.

1. Go to  **Settings**  \&gt;  **Invoice Frequencies**  to set up a desired invoice frequency.
2. Open the fixed price subcontract line on which you need to create a milestone schedule.
3. On the  **Subcontract Line Milestones**  tab, select  **Generate Periodic Milestones**.
4. A dialog opens that allows you to input a date range, number of milestones and invoice frequency. You have the choice to input a start date, number of milestones and invoice frequency or start date, end date and invoice frequency. Both end date and number of milestones cannot be filled.
5. Using this information, the system generates milestones and records are shown in the Milestones grid.

- **Milestone Name**  is set to the date that is dictated based on the invoice frequency.
- **Milestone Date**  is set to the date that is dictated based on the invoice frequency.
- **Milestone Amount**  is calculated by dividing the subtotal amount on the subcontract line by the number of milestones as dictated by the parameters input on the dialog.

1. If the subcontract line has a value in the  **Estimated Tax Amount**  field, this field is also apportioned to each milestone equally when generating periodic milestones.

Sum of the Subcontract line milestone amounts should equal the value of the subcontract line. If they aren&#39;t equal, an error occurs. You can fix that error by verifying that the milestones total is equal to the subcontract line value by either creating, editing, or deleting milestone and tax amounts. After the changes are made, save and refresh the page to ensure that errors no longer appear.

## Manually creating subcontract line milestones

Fixed price milestones on a subcontract line can be generated manually when they aren&#39;t periodically split. To create a subcontract line milestone manually, complete the following steps.

Open the fixed price subcontract line on which you want to create a milestone.

On the  **Subcontract line milestones**  tab, on the sub grid, select  **+ New Subcontract line milestone**.

On the New Subcontract line milestone page, enter the required information based on the following table.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Milestone Name | Quick Create | Text field for the name of the milestone. | This field will be used to identify the milestone in all downstream lookups and on the vendor invoice. |
| Description | Quick Create | A description of the Milestone | Used primarily for identification |
| Milestone Date | Quick Create | The date on which the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. | This will be shown on the vendor invoice line when invoicing for this subcontract.\* |
| Amount | Quick Create | The amount or value of the milestone that will be invoiced to the customer. | This will be shown on the vendor invoice line when invoicing for this subcontract.\* |
| Tax | Quick Create | The tax amount applied on the milestone. | This will be copied over to the vendor invoice line when invoicing for this subcontract.\* |
| Amount after tax | Quick create | A read-only field that is calculated as Amount + Tax | This will be copied over to the vendor invoice line when invoicing for this subcontract.\* |
| Invoice Status | Quick Create | When the milestone is created, this status is always set to  **Not ready for invoicing**   | When the status is &quot;ready to invoice&quot;, vendor invoice creation will include this milestone on the vendor invoice\* |

Select  **Save and Close**.

*See Subcontracting in Project Operations - Early Access Scope

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
