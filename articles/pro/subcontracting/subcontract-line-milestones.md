---
title: Subcontract line milestones
description: Learn how to create and manage milestone-based invoice schedules for subcontract lines in Dynamics 365 Project Operations. Follow step-by-step instructions to automate or manually set milestones.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract line milestones

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

In Dynamics 365 Project Operations, a subcontract line with a fixed-price billing method can specify a milestone-based invoice schedule with the vendor.

You can generate milestones for vendor invoicing automatically by using a set frequency, or you can create them manually.

## Automatically create a milestone-based invoice schedule for a subcontract line

Complete the following steps to automatically generate a milestone-based invoice schedule for a fixed set of equally distributed milestones.

1. Go to **Settings** > **Invoice Frequencies** and set up the invoice frequency for the subcontract lines.
1. Open the **Subcontracts** page, open the subcontract that you want to work with, and then open the fixed-price subcontract line for which you're going to create a milestone schedule.
1. On the **Subcontract Line Milestones** tab, select **Generate Periodic Milestones**.
1. In the dialog box, enter or select a date range, the number of milestones, and the invoice frequency. You can select a start date, or you can select the number of milestones and the invoice frequency or start date, or you can select the end date and invoice frequency. You can't select the end date and the number of milestones.
Using this information, the system generates milestones and records that are shown in the **Milestones** grid.

   - **Milestone Name** - The name of the milestone is set to the date of the milestone based on the invoice frequency.
   - **Milestone Date** - The date based on the invoice frequency.
   - **Milestone Amount** - Calculated by dividing the subtotal amount on the subcontract line by the number of milestones.

If the subcontract line has a value in the **Estimated Tax Amount** field, the system adds this value to each milestone equally when generating periodic milestones.

The sum of the subcontract line milestone amounts should be equal to the value of the subcontract line. If they're not equal, an error occurs. You can fix the error and verify that the milestone total is equal to the subcontract line value by creating, editing, or deleting milestone and tax amounts. After you make the changes, save and refresh the page to ensure that there are no more errors.

## Manually create subcontract line milestones

You can manually create fixed-price milestones on a subcontract line when you don't want to split them periodically. To create a subcontract line milestone manually, complete the following steps.

1. On the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
1. Open the fixed price subcontract line for which you want to create a milestone.
1. On the **Subcontract line milestones** tab, on the sub grid, select **+ New Subcontract Line Milestone**.
1. On the **New Subcontract Line Milestone** page, enter the required information based on the following table.

    | Field | Description |Functional impact|
    | --- | --- |----------------------|
    | Milestone Name | The name of the milestone. |This name appears as the first column in all lookups based on subcontract line milestones. The vendor invoice line that you create based on this milestone also uses the name of the subcontract line milestone as the default name of the vendor invoice line.|
    | Description | A description of the milestone. |The vendor invoice line that you create based on this milestone also uses the description of the subcontract line milestone as the default description of the vendor invoice line.|
    | Milestone Date | The date when the automatic invoice creation process should look for the status of this milestone to consider it for invoicing.| This value is the default date of the vendor invoice line when invoicing for this subcontract line. |
    | Amount | The amount or value of the milestone that you invoice to the customer. |This value is the default amount on the vendor invoice line when invoicing for this subcontract line. |
    | Tax | The tax amount applied on the milestone.| This value is the default tax amount on the vendor invoice line when invoicing for this subcontract line. |
    | Amount after tax | This read-only field is calculated as Amount + Tax.|This value is the default on the vendor invoice line when invoicing for this subcontract line. |
    | Invoice Status | When you create the milestone, always set this status to  **Not ready for invoicing**.|  When you set the status to **Ready to Invoice**, the vendor invoice creation includes this milestone on the vendor invoice. |

1. Select **Save and Close**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
