---
title: Subcontract line milestones
description: This topic explains how to create and maintain a milestone-based invoice schedule for a subcontract with a vendor.
author: rumant
ms.date: 08/06/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract line milestones

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

A subcontract line in Dynamics 365 Project Operations with a fixed-price billing method can specify a milestone-based invoice schedule with the vendor.

Milestones for vendor invoicing can be generated automatically using a set frequency or, you can create them manually.

## Create a milestone-based invoice schedule automatically for a subcontract line

Complete the following steps to automatically generate a milestone-based invoice schedule for a fixed set of equally distributed milestones.

1. Go to **Settings** > **Invoice Frequencies** and set up the invoice frequency for the subcontract lines.
2. Open the **Subcontracts** page, open the subcontract you want to work with, and then open the fixed-price subcontract line for which you are going to create a milestone schedule.
3. On the **Subcontract Line Milestones** tab, select **Generate Periodic Milestones**.
4. In the dialog box, enter or select a date range, the number of milestones, and the invoice frequency. You can select a start date, or you can select the number of milestones and the invoice frequency or start date, or you can select the end date and invoice frequency. You can't select the end date and the number of milestones.
Using this information, the system generates milestones and records are shown in the **Milestones** grid.

   - **Milestone Name**  is set to the date based on the invoice frequency.
   - **Milestone Date**  is set to the date based on the invoice frequency.
   - **Milestone Amount**  is calculated by dividing the subtotal amount on the subcontract line by the number of milestones.

If the subcontract line has a value in the **Estimated Tax Amount** field, this value is added to each milestone equally when generating periodic milestones.

The sum of the subcontract line milestone amounts should be equal to the value of the subcontract line. If they aren't equal, an error occurs. You can fix the error and verify that the milestones total is equal to the subcontract line value by creating, editing, or deleting milestone and tax amounts. After the changes are made, save and refresh the page to ensure that there are no more errors.

## Manually create subcontract line milestones

Fixed-price milestones on a subcontract line can be generated manually when they aren't periodically split. To create a subcontract line milestone manually, complete the following steps.

1. On the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
2. Open the fixed price subcontract line for which you want to create a milestone.
3. On the **Subcontract line milestones** tab, on the sub grid, select **+ New Subcontract Line Milestone**.
4. On the **New Subcontract Line <ilestone** page, enter the required information based on the following table.

    | Field | Description |
    | --- | --- |
    | Milestone Name | The name of the milestone. |
    | Description | A description of the milestone.  |
    | Milestone Date | The date when the automatic invoice creation process should look for the status of this milestone to consider it for invoicing. This value is included on the vendor invoice line when invoicing for this subcontract. |
    | Amount | The amount or value of the milestone that will be invoiced to the customer. This value is included on the vendor invoice line when invoicing for this subcontract. |
    | Tax | The tax amount applied on the milestone. This value is included on the vendor invoice line when invoicing for this subcontract. |
    | Amount after tax | This read-only field that is calculated as Amount + Tax. This value is included on the vendor invoice line when invoicing for this subcontract. |
    | Invoice Status | When the milestone is created, this status is always set to  **Not ready for invoicing**.  When the status is **Ready to Invoice**, the vendor invoice creation includes this milestone on the vendor invoice. |

5. Select **Save and Close**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
