---
title: Create and confirm transaction journals
description: Learn how to create time, expense, and material transactions, preview generated journal lines, and confirm transaction journals in Dynamics 365 Project Operations.
author: abriccetti
ms.author: abriccetti
ms.reviewer: johnmichalak
ms.date: 11/17/2026
ms.topic: how-to
ms.custom:
  - bap-template
#customer intent: As a project accountant or billing administrator, I want to create and review project transactions so that I can record connected financial actuals without creating individual operational entries.
---

# Create and confirm transaction journals

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

> [!IMPORTANT]
> This pre-release documentation draft describes the latest implemented behavior. It doesn't establish feature availability or a release date.

<!-- TODO: Before publication, confirm supported deployment applicability and add the Applies To line. -->
<!-- TODO: Before publication, confirm feature availability and the minimum released version; replace the draft notice with verified availability guidance. -->
<!-- TODO: Before publication, obtain editorial confirmation of ms.reviewer: johnmichalak. -->

Use transaction journals in Microsoft Dynamics 365 Project Operations to record time, expense, and material transactions, such as initial balances during migration or other transactions that require controlled entry and review. Transaction journals don't create individual time entries, expense entries, material usage logs, or project approval records.

Unlike entry journals, where you enter individual cost or sales journal lines, transaction journals let you enter each source transaction once. The system generates the applicable journal lines and their relationships by using project, contract, pricing, and billing rules. Preview those lines, and then confirm the journal to create actuals.

## Prerequisites

The feature is off by default. An administrator can enable it. To enable transaction journal, follow these steps:

1. In the **Project Operations** app, go to **Settings**.
1. Under **General**, select **Parameters**.
1. Open the project parameters record and select **Enable Transaction Journal**.

The following existing out-of-the-box security roles receive all eight permissions on the new **Transaction Detail** entity: **Create**, **Read**, **Write**, **Delete**, **Append**, **Append To**, **Assign**, and **Share**. **Append** and **Append To** allow records to be associated with other records.

| Role | Scope of the new permissions |
| --- | --- |
| Account Manager | Their business unit and child business units |
| Project Manager | Their business unit and child business units |
| Project Billing Administrator | Their business unit and child business units |
| Practice Manager | Entire organization |

Before you create a transaction journal:

- Ensure you have access to journals, transaction details, actuals, and the related project and reference records that you need. Access to transaction details alone isn't sufficient.
- Review the applicable project, contract, pricing, and billing setup. These settings determine the outputs generated for each transaction.

## Create a transaction journal

To create a journal, follow these steps:

1. In the **Sales** area, under **Transactions**, select **Journals**.
1. Select **New**.
1. Enter a description and set **Journal Type** to **Transaction creation**.
1. Save the journal.

The journal starts in **Draft** status. After you save it, use the **Transactions** tab to add the source transactions.

## Add time, expense, or material transactions

To add a transaction, follow these steps:

1. On the **Transactions** tab, open the **New transaction** dropdown menu.
1. Select **Time**, **Expense**, or **Material**.
1. Enter the transaction date, project, quantity, and the other information required for the selected transaction class.
1. Save the transaction.
1. Repeat these steps for the other transactions that you want to include in the journal.

To change a transaction before previewing the journal, select the transaction and then select **Edit**.

## Understand pricing and generated outputs

Leave a price blank to let Project Operations determine it through the applicable pricing setup. Enter a price to override that default. An explicit price of zero is an override, not a request to use a default price.

Cost, unbilled sales, interorganizational sales, and resourcing unit cost price overrides apply only when the corresponding output is applicable. Entering an override doesn't cause an otherwise inapplicable output to be generated.

The system determines the unbilled sales currency from the applicable contract. You don't enter a separate sales currency on the transaction.

> [!NOTE]
> Standard transaction forms don't expose cost, interorganizational sales, or resourcing unit cost currency inputs. If a customization exposes these inputs, each currency override requires a corresponding price override. A price override without a currency override uses the default currency.

Depending on the transaction and its setup, generated outputs can include:

- Cost and unbilled sales journal lines.
- Interorganizational sales and resourcing unit cost journal lines for eligible time and expense transactions. Material transactions don't generate these interorganizational outputs.
- Lines that reflect customer splits and applicable billing rules.
- Relationships that connect the generated transactions to each other and to their source.

## Preview journal lines and resolve errors

Preview validates the source transactions and generates priced journal lines and their connections. It doesn't create actuals.

To preview the journal, follow these steps:

1. Add at least one source transaction to the draft journal.
1. Select **Preview**.
1. If preview succeeds, review the generated records on the **Journal lines** tab, including their prices and applicable cost and sales outputs.

After a successful preview, the journal has **Active** status and the source transactions have **Previewed** status.

### Resolve validation errors

Preview validates all source transactions before generating any lines. If any transaction fail validation, the whole journal remains in **Draft** status, no journal lines are generated for any transaction, and invalid transactions are marked **Failed**.

Review the displayed errors, correct or delete the invalid draft transactions, and select **Preview** again.

## Reset a preview and make changes

If you need to change a successfully previewed journal, reset the preview before editing.

1. On the active, unposted journal, select **Cancel**.
1. Verify that the journal returns to **Draft** status.
1. On the **Transactions** tab, select a transaction and then select **Edit**. Make your changes and save the transaction.
1. Select **Preview** again and review the regenerated lines.

Canceling a preview deletes the generated journal lines, retains the source transactions, and resets their status to **New**. It doesn't cancel posted actuals.

## Confirm the transaction journal

To create actuals from the previewed journal, follow these steps:

1. Complete a successful preview and review the generated journal lines.
1. Select **Confirm**.
1. Review the resulting actuals.

Confirmation posts the existing journal lines. The journal becomes posted and inactive, and its source transactions have **Confirmed** status.

> [!IMPORTANT]
> A posted transaction journal can't be reopened, edited, deleted, or reset. Its confirmed source transactions can't be edited.

## Understand cancellation and reevaluation limitations

### Cancel actuals from a transaction journal

To cancel actuals, enable the separate feature used to cancel actuals created from entry journals.

> [!IMPORTANT]
> When you select one actual for cancellation, you include all current actuals from the same source transaction, across transaction types and customer splits, but not other source transactions in the journal. The entire required set must be eligible, or cancellation doesn't proceed. Review this scope before confirming.

Cancellation creates reversal history without changing the original source transaction or reopening its posted journal.

Follow the general workflow in [Cancel actuals created from entry journals](cancel-actuals-from-entry-journals.md), using the transaction-journal cancellation scope described here.

### Correction and automatic reevaluation

Manual **Correct entries** corrections aren't supported for transaction-journal actuals in either the legacy or new correction journals experience.

> [!NOTE]
> Support for modifying transactions that originate from transaction journals through the new correction journals experience is planned for a future release.

Automatic reevaluation can still apply when supported changes affect the transaction. It uses the original source inputs: explicit price overrides, including zero, remain overrides, while originally blank prices are determined again from the current pricing setup. Reevaluation isn't a way to edit a posted source transaction, and sales-only reevaluation isn't supported.

Before confirmation, applicable project, contract, or pricing changes can refresh eligible previewed journal lines without creating actuals.

## Related content

- [Actuals overview](actuals-overview.md)
- [Create and confirm Entry journals](create-confirm-entry-journals.md)
- [Transaction connections - Link actuals of different transaction types](connectingactuals.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
