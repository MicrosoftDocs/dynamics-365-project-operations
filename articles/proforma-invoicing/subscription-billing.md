---
title: Subscription billing
description: How to set up subscription-based billing on a project contract line, review billing details in Microsoft Dataverse, and invoice subscription transactions through the Billing hub in Microsoft Dynamics 365 Project Operations.
author: nshrivastava
ms.author: nshrivastava
ms.date: 09/11/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Subscription billing

[!INCLUDE[banner](../includes/banner.md)]

_**Applies to:** Dynamics 365 Project Operations integrated with ERP_

Subscription billing brings recurring, schedule-driven billing into the Dynamics 365 Project Operations contract and invoicing experience. You set up a subscription on a project contract line, Dynamics 365 Finance generates the billing schedule and the billing details, and those details flow back into Project Operations where you invoice them through the same proforma invoicing process you already use for time and material and fixed-price work.

> [!NOTE]
> Currently, subscription billing is supported only for the Integrated with ERP deployment type, and for fee-type transactions.

Organizations that deliver services or products in measurable units - hours, reports, packages, licensed seats - need a billing model that supports quantity-driven invoicing, flexible unit pricing and contract terms, recurring delivery on a monthly, quarterly, or annual cadence, and revenue recognition and deferral, all tied back to the project contract and its funding sources.

Before this feature, subscription and recurring billing lived entirely in Finance and wasn't connected to the Project Operations contract and invoicing experience. Subscription billing closes that gap so you can:

- Bill recurring subscription charges from the same project contract that carries your time and material and fixed-price work.
- Generate invoices automatically from the billing schedule instead of creating them by hand each period.
- Review subscription charges alongside other transaction types on a single proforma invoice, in the Billing hub.
- Keep revenue recognition, accounting, period close, and audit in Dynamics 365 Finance, where those capabilities already live.

## Prerequisites

Subscription billing spans Project Operations and Finance, so you must turn on features in both applications and run the dual-write maps that carry the subscription data between them.

### Enable subscription billing in Finance

In **Feature management**, turn on the following features. Turn them on in the order listed, because the Project Operations features build on the base subscription billing capability.

| Feature | Why it's needed |
| --- | --- |
| Subscription billing | Provides the base billing schedule engine - subscription setup, billing schedules, billing lines, and billing detail generation. |
| Recurring contract billing | Enables the recurring billing cadence - frequency, start and end dates, and proration - used by subscription billing schedules. |
| Billing schedules and deferrals with projects | Connects billing schedules and deferrals to projects, so a billing schedule can be tied to a project and its funding source. |
| Subscription billing for Project Operations | Enables the Project Operations-specific behavior: creation of the placeholder billing schedule header from the synchronized contract line, and locking of billing detail lines once Dynamics 365 Project Operations begins invoicing. |
| (Preview) Enable project fee journals to support subscription billing for Project Operations for manufacturing | Preview. Enables project fee journal-based subscription billing for manufacturing scenarios. Turn this feature on only if that scenario applies. |
| Enable line discounts and additional fee for Project Operations integrated with ERP based scenarios | Required for discounts to appear on the invoice. Without it, line discounts don't show up on the invoice. |

### Enable subscription billing in Project Operations

In Project Operations **Feature control** settings, turn on:

| Feature | Why it's needed |
| --- | --- |
| Subscription billing | Exposes the **Subscription based** invoice schedule type on the contract line, the subscriptions tab and billing detail views, and subscription handling in the Billing hub and on the invoice. |

> [!IMPORTANT]
> Turn the feature on in Finance first, and then in Project Operations. The subscription setup and billing schedule generation that the Project Operations experience depends on originate in Finance.

### Enable the dual-write maps

Run the dual-write maps that carry subscription data between the two systems. The following maps cover the subscription billing entities:

- Project invoice proposal V2 (version 1.0.0.5)
- Project contract lines (version 1.0.0.3)
- Project subscription billing schedule header (version 1.0.0.0)
- Project subscription billing schedule lines (version 1.0.0.0)
- Project subscription billing detail lines (version 1.0.0.0)

These maps carry the billing schedule and billing details from Finance to Project Operations, and carry the invoicing lock signal back from Project Operations to Dynamics Finance. Without them, subscriptions don't appear on the contract line in Project Operations and billing details aren't available for invoicing.

## How the work is divided between Project Operations and Finance

The design keeps each system responsible for what it already does best.

| Capability | System of record |
| --- | --- |
| Project and contract | Project Operations |
| Invoicing experience | Project Operations |
| Subscription setup | Finance |
| Billing schedule logic | Finance |

In practice:

- **Finance** owns the subscription math and the scheduling engine - the billing schedule, pricing method, proration, hold, termination - and generates the billing detail records. It also owns revenue recognition, posting to AR and GL, financial compliance, period close, and audit.
- **Project Operations** owns the project and contract context and the Project Operations invoicing experience - creating the fee actuals from billing details, marking them ready to invoice, creating and confirming the proforma invoice, and tracking invoicing state.

Proforma invoice creation stays Dynamics 365 Project Operations-initiated. Dynamics 365 Finance is responsible only up to billing detail generation.

## Set up a subscription on a contract line

To set up a subscription on a contract line, follow these steps:

1. Open the project contract, and go to **Contract lines**.
1. Create or open a contract line. Keep the **Billing method** as **Time and material**; set the **Invoice schedule type** to **Subscription based**.
1. Save the contract line.

   When the contract line syncs to Finance, it automatically creates a placeholder billing schedule header with the contract, project, customer, and invoice transaction type already filled in.

1. Enter the subscription details:
   - Start date and end date
   - Billing frequency — one-time, daily, biweekly, monthly, quarterly, semiannually, or annually
   - Proration
   - Billing line configuration

1. Add billing lines for the services or items you're billing. Each line includes details such as description, transaction class, quantity, unit of measure, unit price, net amount, product, and transaction category.

A contract can have more than one subscription:

- One contract can have multiple billing schedule headers (subscriptions).
- One schedule header can have multiple billing lines.
- One billing line generates multiple billing details, based on its start date, end date, and frequency.

Each subscription is billed on its own schedule, which means you can send separate invoices for each subscription.

## Review subscriptions and billing details in Project Operations

Finance synchronizes the billing schedule header and the billing schedule line details back to Project Operations. They appear as a read-only view on the subscription contract line. Use **View billing detail** on the subscription line to check what was generated.

In this release, subscriptions appear on a dedicated tab on the contract and contract line forms.

## Invoice subscription transactions

Finance generates billing details and sends them to Project Operations. From that point, invoicing follows the standard Project Operations workflow:

1. Open the **Billing hub**.
1. Open the **Invoiceable backlog** for the subscription contract line.
1. Select the subscription transactions, and mark them **Ready to invoice**.
1. Select the transactions again, and then select **Add to invoice**. You land on the proforma invoice summary.
1. Review the charges:
   - Subscription charges on the **Subscriptions** tab.
1. Confirm the proforma invoice in Dynamics 365 Project Operations.
1. Create the invoice proposal in Dynamics 365 Finance, where you post the invoice. Update the billing detail to reflect what was invoiced.

Billing details are only picked up for invoicing once they fall within the invoice cut-off date, so a schedule that extends into future periods doesn't pull forward charges that aren't yet due.

You can automate steps 3 through 7. You can automatically create fee actuals, mark them ready to invoice, pull them into a proforma invoice, and confirm them through the existing Dynamics 365 Project Operations invoice batch capabilities, so recurring charges bill without manual intervention each period.

## Editing restrictions after invoicing begins

You can edit subscription billing parameters in Finance up until Project Operations starts invoicing activity for a billing detail. At that point, a signal synchronizes back to Finance and the corresponding billing detail lines become read-only there.

This process prevents pricing or quantity changes in Finance after invoicing starts downstream in Project Operations. It also avoids the two systems disagreeing about what was billed.

## Managing subscriptions over the contract lifecycle

Perform subscription management actions in Finance, such as placing a billing line on hold, terminating a subscription, and editing or deleting a subscription. The read-only view in Project Operations reflects the resulting billing schedule and billing details.

## Auto invoice setup

Recurring subscription charges work well with automated invoicing. The billing schedule already determines what to bill and when to bill it. So, you can create, confirm, and post the invoice each period without manual intervention. Configure automation in two places: proforma invoice creation in Dynamics 365 Project Operations, and invoice posting in Dynamics 365 Finance.

### Set up automatic proforma invoice creation in Project Operations

Follow the steps in [Set up automatic invoice creation](/dynamics365/project-operations/pro/proforma-invoicing/configure-automated-invoice-creation-sales) to configure automated invoice creation for the project contract.

After you complete the setup, run the **ProcessRunner** flow. The flow must run before you create proforma invoices automatically.

### Set up automatic invoice posting in Finance

#### Prerequisite

The dual-write map **Project invoice proposal V2** must be on version **1.0.0.5** or later. That version adds the `ShouldAutoPost` field, which carries the **Post invoice automatically** value from Project Operations to Finance. On earlier versions, such as 1.0.0.4, the value doesn't synchronize and proposals aren't picked up for automatic posting.

Updating the map version takes effect for newly synchronized invoice proposals. Proposals that synchronized before the update aren't corrected retroactively.

#### Configure the posting batch job (only required if no auto-post batch job exists)

To configure the posting batch job, follow these steps:

1. Go to **Project management and accounting** > **Periodic** > **Invoice** > **Post invoice proposals**.

1. **Filter for auto-post proposals only.** Select **Select**, and add the following range on the **Invoice proposal** table: **Post invoice automatically** = **Yes**.

1. **Turn on late selection.** Set **Late selection** to **Yes**.

   > [!IMPORTANT]
   > Late selection is required for recurring runs. Without it, the dialog freezes the records that match at the time of setup into the job, and that same fixed list runs every time. With it, the query runs again on each execution and picks up newly synchronized proposals.

1. **Schedule the job with a recurrence.** Select **Batch** in the lower right, and configure:

   - **Batch processing** — **Yes**
   - **Task description** — for example, `Post subscription-based invoice proposals`

1. Select **Recurrence**, and configure:

   - **Start date** and **Start time** — choose a window after the Dynamics 365 Project Operations synchronization completes
   - **No end date**
   - **Pattern** — **Minutes**, every **10** minute(s)

1. Select **OK**, and then select **OK** on the main dialog.

With both halves in place, subscription invoices are created and confirmed in Project Operations, synchronized to Finance as invoice proposals flagged for automatic posting, and posted by the recurring batch job — with no manual step each billing period.

## Additional information

- [Manage a proforma project invoice with modern invoice form](modern-invoicing.md)
- [Create proforma project invoices with Billing hub](billing-hub.md)
- [Proforma project invoices](../pro/proforma-invoicing/create-manual-proforma-invoice-sales.md)
