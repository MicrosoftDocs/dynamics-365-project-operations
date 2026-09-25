---
title: Create and confirm correction journals (new experience)
description: Learn how to create, review, and confirm correction journals in the new correction journals experience in Microsoft Dynamics 365 Project Operations.
author: abriccetti
ms.author: abriccetti
ms.reviewer: johnmichalak
ms.date: 09/25/2026
ms.topic: how-to
ms.custom:
  - bap-template
ms.service: dynamics-365-project-operations
ms.search.scope: ProjectOperations

---

# Create and confirm correction journals (new experience)

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

> [!IMPORTANT]
> This article applies to the **new correction journals experience** when you enable it from the **Feature control** menu.
>
> If your organization isn't using this feature yet, see [Create and confirm correction journals (legacy experience)](/dynamics365/project-operations/actuals/create-confirm-correction-journals).

The new correction journals experience in Dynamics 365 Project Operations streamlines how you correct approved actuals. You can add approved time, expense, and material transactions to one draft correction journal, apply updates to selected entries, preview generated lines, and confirm when ready.

## Before you begin

- You can only correct **approved** and correction-eligible transactions.
- You must have access to correction journals and source transactions.
- A correction journal must be in **Draft Adjustment** status to add entries or edit corrections.
- After a journal is confirmed, it becomes read-only.

## Start a correction journal

To start a correction journal, follow these steps:

1. Open an eligible transaction list (for example, approved transactions or billing backlog views).
1. Select one or more entries to correct.
1. Select **Correct entries**. A new draft correction journal opens with your selected entries in the **Correction entries** grid.

You can also open an existing correction journal in **Draft Adjustment** status and add more eligible entries before confirmation, or create a new draft correction journal by selecting **Entry Specific Corrections** from the journal type dropdown menu during journal creation.

## Add and edit corrections

To add and edit corrections, follow these steps:

1. Select one or more entries in the **Correction entries** grid.
1. Select **Edit entries** to open the side pane.
1. Change one or more correction fields. The fields shown in the side pane depend on the selected transaction class or classes.
1. Select **Apply and continue** to apply your changes and keep the pane open. You can then select a different group of entries and apply different corrections in the same journal. Alternatively, select **Apply and close** to apply your changes and close the pane, or **Apply and preview** to apply your changes, generate journal lines, and close the pane.

Correction fields available in the side pane include:

- Project and project task
- Transaction date
- Subcontract and subcontract line
- Bookable resource
- Quantity and billable quantity
- Internal description and external comments
- Sales price and cost price

Class-specific fields include:

- **Time:** Resource role
- **Expense:** Expense category
- **Material:** Product and Write-in product description

## Understand validation behavior

- The pane shows only fields valid for your current selection.
- If you select mixed transaction classes, class-specific fields are hidden.
- For mixed-class bulk updates, quantity, billable quantity, cost price, and sales price aren't available.
- The system enforces field consistency (for example, nonbillable entries can't carry billable quantity).

> [!IMPORTANT]
> Entries that remain eligible for correction are included when journal lines are generated, even if you don't edit them. Preview generates reversal and replacement journal lines; it doesn't post the changes to actuals. Confirmation posts those lines to reverse the original actuals and create replacement actuals.
>
> An unchanged entry can therefore still result in reversal and replacement transactions. Remove entries that you don't want processed before previewing or confirming the journal.

## Preview to generate journal lines

To generate journal lines, follow these steps:

1. After entering corrections, select **Preview** on the journal command bar, unless you already selected **Apply and preview** in the side pane. Both actions generate the journal lines needed to reverse existing actuals and create replacement actuals based on your corrections. Depending on the scenario, multiple journal lines can be generated for a single source entry.
1. Review the generated reversal and replacement lines on the **Journal lines** tab.
1. To make further corrections, select **Cancel** on the journal command bar. This action deletes the preview-generated journal lines and returns the journal to **Draft Adjustment**. Make your changes, and then select **Preview** again to review the updated lines. If you use **Apply and preview** to apply those changes, review the generated lines without selecting **Preview** again.

Preview is optional. If you select **Confirm** before selecting **Preview**, the system automatically generates the preview journal lines and then immediately continues with confirmation in the same action.

## Confirm the correction journal

To confirm the correction journal, follow these steps:

1. Verify the correction entries. If you used preview, also review the generated journal lines.
1. Select **Confirm**.

After confirmation:

- Corrected actuals are created.
- The journal is finalized and can no longer be edited.
- Historical records remain available for audit and investigation.

## Track correction status

Each correction entry indicates whether it was:

- Added but left unchanged
- Modified after being added to the journal

The system retains each entry's correction status after confirmation to support traceability. This modified or unchanged status is separate from the journal's status. After confirmation, the journal is finalized and can no longer be edited.

## Limitations and release scope

- Mixed-class bulk updates are limited to shared fields.
- You can add only approved transactions that are eligible for correction.
- Custom fields might require extra implementation logic to fully participate in correction processing.
- Contract or contract-line re-evaluation actions are separately controlled and you shouldn't treat them as the default correction flow unless they're explicitly enabled in your environment.
