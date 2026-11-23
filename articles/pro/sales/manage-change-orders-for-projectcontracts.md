---
title: Change order management
description: Create, review, approve, and apply changes to confirmed project contracts with change order management in Dynamics 365 Project Operations.
author: poojafandan
ms.date: 11/23/2026
ms.topic: how-to
ms.custom: bap-template
ms.author: poojafandan
ms.reviewer: johnmichalak
---

# Change order management

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Change order management in Dynamics 365 Project Operations helps you prepare, review, and approve amendments to confirmed project contracts. Use a change order to propose changes to scope, quantities, pricing, resources, delivery dates, invoice schedules, and eligible contract terms without directly changing the active contract.

The change order experience lets you:

- Add contract lines and update eligible details on existing lines.
- Compare original and proposed values in grids and forms.
- Review billing, budget, margin, and not-to-exceed (NTE) impact before approval.
- Use custom approval workflows with the out-of-the-box approval as the final step.
- Apply approved changes through a configurable batch job.
- Review contract versions and a change order log file saved in the timeline.

> [!NOTE]
> In the first phase, you can create change orders only with a current or future effective date. Past effective dates and creation from a project aren't supported. Commands, editable fields, and status labels can vary with your security role and organization settings.

## Before you begin

Verify that you:

- Have change order management enabled for your organization.
- Confirmed the source project contract.
- Set the proposed effective date to today or a future date.
- Can access the contract, affected projects, and related contract lines.
- Have a security role that permits the action you want to perform.
- Have current contract, project work breakdown structure (WBS), pricing, and billing data.

Access is controlled through Dynamics 365 security roles. The following responsibilities are examples, not fixed product role assignments.

| Action | Typical responsibility |
| ------ | ------------- |
| **Create, edit, or cancel a draft** | Project manager or contract manager |
| **Submit for review** | Contract manager |
| **Approve, reject, or return for rework** | Designated approver |
| **Configure and monitor the application batch job** | Authorized contract manager or system administrator |
| **Review financial impact and history** | Finance or delivery operations analyst |

Your organization determines who can approve a change and whether the submitter and approver must be different users. Separation of these responsibilities isn't enforced by default.

## Set up change order management

Before users create change orders, administrators configure access, approvals, and batch processing.

| Area | Configuration or policy |
| ------ | ------------- |
| **Access** | Grant create, edit, submit, approve, reject, cancel, recall, and read access through security roles. |
| **Approval responsibilities** | Define approvers and any required separation of duties. |
| **Approval integration** | Add custom approval workflows, with the default approval as the final step. |
| **Contract application** | Configure the batch job and its schedule to apply approved change orders. |
| **Change information** | Configure reason values and other required business information. |
| **Draft work** | Decide whether cost actuals can be recorded for tasks in draft change orders. |
| **Task cleanup** | Configure whether cancellation or rejection prompts users or applies a policy to retain or delete linked tasks. |
| **Parallel activity** | Establish effective-date ordering, approval sequencing, and conflict-resolution responsibilities. |
| **Audit** | Review audit configuration, access, and retention requirements. |

Administrators can add custom fields to the change order header. Keep required fields in place. Adding new change item types isn't supported. Don't assume that existing contract custom fields are automatically included in the change order.

## Understand change order statuses

A change order includes general information, proposed contract or line changes, and references to the affected records. The status applies to the complete change order. You don't approve or reject individual lines independently.

| Status | Meaning | What happens next |
| ------ | ------------- | ------------- |
| **Draft** | The change order is being prepared, has been returned for rework, or has been recalled before application. | Add or edit permitted changes, review impact, validate, submit, or cancel. |
| **Submitted** or **In review** | The complete change order is awaiting a decision. Its contents are locked. | Approve, reject, or return for rework. |
| **Approved** | The change order passed the final out-of-the-box approval but hasn't yet been applied. | The configured batch job applies it according to its effective date. It can be recalled before application. |
| **Approved - application failed** | Approval succeeded, but the contract update failed. | Resolve the reported issue and retry application. |
| **Rejected** | The complete change order was rejected. | Review the decision or copy the rejected changes to a new draft. |
| **Canceled** | The draft was withdrawn. | Review the retained record for history. |
| **Applied** | The approved changes updated the contract. | Review the resulting contract version, billing setup, and history. |

The usual sequence is **Draft** > **Submitted** > **Approved** > **Applied**. **Return for rework** changes a submitted change order back to **Draft**; there is no separate rework status. **Recall** returns an approved change order to **Draft**, provided it hasn't been applied. Rejection or cancellation doesn't update the active contract.

> [!IMPORTANT]
> Approval and application are different steps. An approved change order doesn't mean that the active contract is already updated. Check the application result before relying on the revised contract for billing or delivery.

## Create a change order from a contract

To create a change order from a contract, follow these steps:

1. Open **Project Operations**.
1. Go to **Sales** > **Project contracts**.
1. Open the confirmed contract that you want to amend.
1. Go to the **Change order** tab.
1. Select **Create new change order**.
1. Review the source contract reference and enter the change order information.
1. Save the draft.

| Information | Guidance |
| ------ | ------------- |
| **Effective date** | In Phase 1, select the current date or a future date when creating a change order. You can't select a past effective date. |
| **Reason for change** | Required. Select the appropriate reason from your organization's configurable list. |
| **Summary of changes** | Describe the business need, proposed scope, and intended outcome. This field is optional unless your organization requires it. |
| **Supporting information** | Add documents, notes, or comments to the header or individual lines as needed for review. |

The system assigns a change order ID, sets the status to **Draft**, and links it to the source contract. You can use existing contract information to prepare changes. Fields that you can't amend remain locked.

### Choose the effective date

When you create a change order in Phase 1, select today or a future date as the effective date. You can't create a change order with a past effective date.

Review work recorded while the change order is pending. Approval and application remain separate steps, and you can recall an approved change order before application.

> [!IMPORTANT]
> Phase 1 allows current and future effective dates, but not past effective dates. Issued, paid, billed, or locked transactions can require a separate financial correction process.

## Define scope and contract changes

A draft can contain multiple related changes. Keep changes that need a single approval decision together. If changes require different effective dates or independent approval decisions, prepare separate change orders. Each change order must have a current or future effective date when you create it.

| Change | Examples |
| ------ | ------------- |
| **Add a contract line** | New delivery scope or an extra commercial work package |
| **Modify a contract line** | Quantity, price, role, resourcing unit, chargeability, split percentage, or dates |
| **Update contract terms** | Amend eligible header fields, such as requested delivery date, account manager, or NTE limit |

### Add a contract line

To add a contract line, follow these steps:

1. Open the draft change order and select the option to add a contract line.
1. Enter the required project, billing method, transaction classes, dates, and commercial information.
1. Add line details manually or import eligible tasks from the linked project.
1. Configure resources, pricing dimensions, chargeability, and billing details.
1. Save the line and review its impact.

When importing tasks, select tasks that are eligible for the line's transaction classes and aren't already mapped to an incompatible active contract line.

### Modify an existing line

To modify an existing line, follow these steps:

1. Select the original contract line that you want to change.
1. Add it to the change order.
1. Review the copied values and original record reference.
1. Change the permitted fields and save.
1. Compare the proposed values and financial impact with the original line.

Eligible changes include line details, tasks, quantities, prices, roles, resourcing units, resource assignments, chargeability options, split billing percentages, dates, and durations. The change order line keeps its reference to the original contract line for traceability.

The existing contract line's project link and billing method must stay the same, including for uninvoiced work. When you create a new line, specify its project and billing method as part of the new line setup.

### Remove a line detail and add it to another line

There's no direct move action for line details. Update the affected lines separately.

To remove a line detail and add it to another line, follow these steps:

1. Update the source contract line to remove the line detail.
1. Update the target contract line to add that line detail.
1. Validate transaction classes, dates, task eligibility, and dependencies for both updates.

Don't change either existing line's project link or billing method. A task can't be associated with two active contract lines.

### Remove a contract line or task

Select the original line or eligible task and mark it for deletion through the change order. Review dependencies and financial history before submission.

You can't remove a change item if doing so would invalidate another active change item. For example, removing the item that establishes a task association can invalidate another item that modifies that association. Resolve the dependency or revise the related changes together.

Marking an item for deletion in a draft doesn't immediately remove it from the active contract.

### Update contract terms

For a change order created from a contract, amend the eligible header fields exposed in your environment. Examples include the contract title, requested delivery date, account manager, not-to-exceed limit, and nonprimary customer information.

Required fields and date consistency rules still apply. Not all contract fields are amendable. For example, when a start and end date are required, the end date must be later than the start date.

### Change an invoice schedule

Invoice schedule changes apply only to eligible uninvoiced amounts. Before proposing the change:

1. Review the amount already invoiced and any locked billing records.
1. Identify the uninvoiced portion that the amendment should affect.
1. Update the eligible milestones or invoice schedule within the line's existing billing method.
1. Review the proposed dates and amounts, and resolve validation issues before submission.

Changing the invoice schedule doesn't change the line's billing method or rewrite billed history.

## Work with project tasks

Task association and billing behavior depend on whether the contract line uses task-based or transaction class-based billing.

### Task-based billing

With task-based billing, you explicitly associate tasks with contract lines. Tasks from the same project and transaction class can belong to different lines, but a single task can belong to only one active contract line at a time.

To add tasks through a change order, follow these steps:

1. Create the tasks in the project's WBS.
1. Open the new or existing line in the draft change order.
1. Use **Task Billing Setup** to import and associate eligible tasks.
1. Review task conflicts and any pending-change warnings.
1. Save the task setup, then review the proposed field, financial, and billing changes before submitting.

Approval authorizes the proposed association. Application makes it part of the updated contract and establishes billing eligibility.

| Situation | Behavior |
| ------ | ------------- |
| **A task is referenced in another pending change order** | An informational warning identifies the overlap. Pending participation alone doesn't establish an active contract association. |
| **A task is already associated with an active line or approved change order line** | Remove the existing association through the appropriate controlled change before attempting an incompatible reassignment. |
| **Two pending changes attempt to claim the same task** | The first successfully approved change establishes the authoritative association. Later approvals are validated against the latest state. |
| **A referenced task is deleted from the WBS** | Approval or application can fail validation. Correct the reference before continuing. |
| **A task is added to a target line after removal from its source line** | Use separate source-line removal and target-line addition updates. Eligible unbilled actuals are reevaluated when the approved changes are applied. Billed actuals aren't reassociated. |

### Transaction class-based billing

With transaction class-based billing, you associate scope with transaction classes such as **Time**, **Expense**, **Material**, and **Fee**. You can't assign the same transaction class to multiple contract lines for the same project.

Tasks in the project's WBS are eligible under the associated transaction class without an explicit task-to-line mapping. Adding a task to such a project doesn't, by itself, require a change order. Whether your organization requires one for scope governance is a business-process decision.

Use a change order to amend the line's pricing, funding, dates, commercial terms, or relevant line details. When removing or modifying scope through a change order, ensure that contract line details and project data remain consistent. Missing or invalid references can block application.

## Review original and proposed values

Use grid highlighting and the **Review changes** form action to compare the original and proposed values. Complete this review before submission, and repeat it during approval review.

### Review changes in a grid

The grid highlights new records and changed values so that you can identify the proposed changes.

| Change | How to review |
| ------ | ------------- |
| **New record** | The record is highlighted in the grid. Review its details before proceeding. |
| **Changed cell** | The cell is highlighted. Hover over it to see the original value and the changed value. |

### Review changes on a form

When a form contains changes, the **Review changes** button is available on the form.

To review changes on a form, follow these steps:

1. Open the form that contains the changed fields.
1. Select **Review changes** to open the side pane.
1. Review each changed field in the pane and compare its original value with its changed value.

Review these field-level differences together with the financial and operational impact described in the following sections. A field comparison shows what changed; impact analysis helps you assess the consequences.

## Review financial and operational impact

Before submitting or approving a change order, compare its proposed result with the currently approved contract baseline. Review both the overall effect and the contribution of individual lines.

> [!IMPORTANT]
> Impact analysis evaluates this change order only. It doesn't aggregate other draft or submitted change orders on the same contract. Review those change orders separately and refresh the analysis after the approved baseline changes.

| Area | What to review |
| ------ | ------------- |
| **Revenue and contract value** | Current value, proposed value, and increase or decrease |
| **Cost** | Additional or reduced delivery cost |
| **Gross margin** | Before-and-after margin amount and percentage |
| **Not-to-exceed (NTE) exposure** | Limit, spent and committed amounts, proposed utilization, and remaining capacity |
| **Billing** | Milestone dates, invoice schedules, and uninvoiced amounts affected |
| **Budget and forecast** | Scope or price changes that require budget adjustments and affect forecasts |
| **Timeline** | Delivery-date, task-date, or billing-date shifts |
| **Actuals at risk** | Exposure from work recorded while a change order is pending, when this information is available |
| **Parallel activity** | Other pending change orders that affect the same lines or tasks |

### Review proposed billing and budget effects

While the change order is in **Draft**, review the billing and budget effects before submission. The approver reviews these effects again before making a decision.

| Existing billing arrangement | Review before submission and approval |
| ------ | ------------- |
| **Fixed Price, milestone-based** | Proposed new or revised milestones, invoice plan, and required budget adjustments |
| **Fixed Price, progress-based** | Proposed task contributions, progress weighting, calculations, and billing schedule |
| **Time and Material** | Expected effects on eligible unbilled sales actuals, task associations, pricing, and invoice timing |

Identify required project budget adjustments and who will make them. Review projected margin, utilization, and forecasts before seeking approval. The existing line's project link and billing method remain unchanged.

### Review expected actuals reevaluation

Before submission and approval, identify eligible unbilled actuals that proposed task changes could affect. When approved changes are applied, these actuals can be reassociated with the resulting contract line and, where required, reversed and recreated.

Billed actuals aren't reassociated, and invoice history isn't rewritten. Review any separate credit, debit, or other financial correction process required for issued or locked billing records before seeking approval.

### Review gross margin

Gross margin is revenue minus total cost. The following calculations show the proposed margin and its change:

- Gross margin percentage = `(Revenue - Total cost) / Revenue * 100`
- Margin impact in percentage points = `Proposed margin percentage - Current margin percentage`

Calculate the margin percentage when revenue has a nonzero value.

For example, a contract with revenue of $500,000 and cost of $350,000 has a margin of $150,000, or 30%. A change order that increases revenue to $560,000 and cost to $395,000 raises the margin to $165,000 but lowers the margin percentage to approximately 29.5%.

The change therefore adds $15,000 in margin while reducing the margin rate by approximately 0.5 percentage points. Review both measures; extra revenue doesn't necessarily improve profitability.

### Review NTE utilization

For applicable Time and Material lines, the NTE limit is the maximum billable sales amount. NTE consumption includes:

- **Spent:** Invoiced Billed Sales actuals.
- **Committed:** Chargeable Unbilled Sales actuals with an NTE status of Committed.

The impact calculation compares existing consumption with consumption and limits proposed by this change order.

- Consumed NTE = `Spent + Committed`
- Available NTE = `Current NTE limit - Consumed NTE`
- Current utilization percentage = `Consumed NTE / Current NTE limit * 100`
- Proposed utilization percentage = `(Consumed NTE + Billable change) / (Current NTE limit + NTE adjustment) * 100`
- NTE impact in percentage points = `Proposed utilization percentage - Current utilization percentage`

**Billable change** is the incremental customer-facing sales value introduced by the change. **NTE adjustment** is the proposed increase or decrease in the limit.

For a new line, proposed utilization compares its proposed billable sales with its proposed NTE limit. For an existing line, the calculation includes its existing spent and committed amounts. Contract-level analysis includes the applicable lines in this change order without double-counting them.

For example, consumption of $86,000 against a $100,000 limit means 86% utilization. A change that adds $20,000 in billable value without increasing the limit raises projected utilization to 106%: an increase of 20 percentage points and an exposure of 6% over the limit.

Values below 100% indicate remaining capacity; 100% means the limit is fully utilized; values above 100% indicate an overrun. Fixed-price lines and records with missing, zero, or otherwise inapplicable limits show **Not applicable** rather than a utilization percentage.

Proposed values are previews, not updates to active NTE records. Review amounts in contract currency and the applicable currency conversion policy. Displayed percentages can be rounded to one decimal place.

### Review line-level drivers and pending-work exposure

Use the line-level breakdown to identify which changes contribute to cost, revenue, margin, NTE exposure, and timing shifts. A scope increase and a billing-date change can have very different effects even when both belong to the same amendment.

Review work recorded while the change order is pending and any available actuals-at-risk information. Confirm that the financial treatment matches the agreement before proceeding. This review doesn't enable past-dated change order creation in Phase 1.

## Manage parallel change orders

Review parallel activity before submitting a draft, and repeat the check before approval and application. Multiple drafts can affect the same contract line, but approval order determines the authoritative changes and the baseline for later decisions.

- Review related drafts, submitted changes, and approved changes awaiting application.
- Sequence approvals in ascending effective-date order.
- Refresh impact analysis after another approval changes the baseline.
- Recheck task ownership, dependencies, NTE exposure, billing state, and dates.
- Resolve conflicts before proceeding. Submission doesn't reserve a task or guarantee approval.

Interactive approval processes one change order at a time. If you configure a back-end approval utility, define the sequence so that changes to the same contract are validated against the latest state.

For example, two drafts might attempt to associate the same unlinked task with different lines. The first successfully approved change establishes the authoritative association. Correct the second draft if that association makes its proposal invalid.

## Cancel a draft and manage task cleanup

If you decide not to proceed with the proposed changes, cancel the draft instead of submitting it.

To cancel a draft and manage task cleanup, follow these steps:

1. Open the draft change order.
1. Select **Cancel**.
1. Review the confirmation and any linked-task cleanup prompt.
1. Confirm the cancellation and the appropriate task handling.

When you cancel or reject a change order, your organization's configuration or a prompt determines whether linked tasks are deleted from the WBS or retained without their change order and contract-line references.

> [!IMPORTANT]
> Deleting linked WBS tasks changes the project plan. Review delivery dependencies and recorded costs before choosing deletion. Retaining tasks doesn't authorize billing for rejected or canceled scope.

Canceled and rejected change orders remain available for history and reporting. Neither update the original contract nor automatically cancel recorded cost actuals.

## Validate and submit a change order

To validate and submit a change order, follow these steps:

1. Open the draft and confirm that it includes all intended changes.
1. Review the highlighted grid records and cells, use **Review changes** on forms to compare original and proposed field values, and review attachments and comments.
1. Complete the billing, budget, financial impact, task association, effective date, and parallel change reviews.
1. Select **Validate**, when available.
1. Resolve errors and review warnings.
1. Select **Submit**.

Validation checks required fields, including **Reason for change**, as well as billing methods, effective dates, task linkage, conflicting changes, and dependencies. Budget threshold checks can produce warnings that require review.

A draft can contain both valid and invalid lines, but submission is blocked until every line is valid. Correct invalid lines, remove them without breaking dependencies, or move them to a separate draft.

Submission changes the complete header and its lines to **Submitted** or **In review**. The contents become read-only while a decision is pending.

### Record work while the change order is pending

An organization setting controls whether you can record cost actuals for tasks associated with a draft change order.

When permitted, cost recording doesn't authorize billing. Sales actuals aren't created for a task association that exists only in the pending change order. You can't invoice that scope before approval and application.

## Review and decide a change order

As an authorized approver:

1. Open the submitted change order.
1. Review the business reason, summary, and supporting information. Inspect the highlighted grid records and cells, and use **Review changes** on forms to compare original and proposed values.
1. Review the proposed billing and budget effects, financial impact, timeline changes, and actuals exposure.
1. Check other pending change orders on the same contract.
1. Verify the effective-date sequence.
1. Complete any configured custom approval steps before the final out-of-the-box approval.
1. Select **Approve**, **Reject**, or **Return for rework** for the complete change order.

| Decision | Result |
| ------ | ------------- |
| **Approve** | Runs the final out-of-the-box approval validations and marks the complete change order **Approved** for batch application if validation succeeds. |
| **Return for rework** | Changes the status back to **Draft**, makes permitted fields editable again, and retains reviewer comments and approval history. |
| **Reject** | Rejects the entire change order without applying its changes to the contract. |

> [!IMPORTANT]
> Approval is all-or-nothing at the header level. If only some changes should proceed, select **Return for rework** so the preparer can separate the excluded changes into another draft. Don't approve the whole change order expecting individual lines to be omitted.

Validation runs again at approval, including approval performed through a configured back-end process. If the underlying contract or task state changed after submission, approval can be blocked even though submission succeeded.

### Rework and resubmit a change order

To rework and resubmit a change order, follow these steps:

1. Open the change order that was returned for rework. Its status is **Draft**.
1. Read the reviewer comments and validation messages.
1. Update permitted fields, such as descriptions, quantities, pricing, or dates.
1. Validate again and select **Submit**.

Rework preserves line IDs, references, and approval history. Protected fields and contract associations remain read-only. Resubmission moves the change order to **Submitted** or **In review**. Follow the configured workflow, ending with the default approval.

### Reuse rejected changes

Rejected changes remain on the original change order as evidence of the decision. To propose them again, use the copy action to create a new draft, make the required corrections, and submit that new change order.

Copying rejected changes doesn't reopen or overwrite the rejected record.

Recorded cost actuals remain in the system after rejection. Follow your organization's financial process if those costs must be canceled, and review the task-cleanup guidance before finalizing the rejection.

### Recall an approved change order

An authorized user can recall a change order after approval and before the batch job applies the changes.

To recall an approved change order, follow these steps:

1. Open the approved change order and confirm that it isn't applied.
1. Select **Recall**. The status returns to **Draft**.
1. Make the required changes and review their impact.
1. Validate and resubmit the change order for approval.

You can't recall an applied change order. Further changes to an applied contract require the appropriate amendment or financial correction process.

## Apply approved changes to the contract

The configured batch job applies approved change orders according to their effective dates. Configure the job and its schedule to meet your organization's requirements.

To apply approved changes to the contract, follow these steps:

1. Confirm that the change order completed the final out-of-the-box approval and is **Approved**.
1. Verify its effective date and position relative to other amendments.
1. Check that the application batch job is configured and scheduled appropriately.
1. Monitor the batch job and the change order's application result.
1. Confirm that application succeeded before verifying the resulting contract.

The system validates the change order again before updating the contract. Application updates eligible fields, scope, task associations, billing arrangements, and financial information. Existing lines retain their project links and billing methods.

### Verify the applied results

After application, compare the result with the approved changes. This step is a completion check, not the initial billing or budget review.

To verify the applied results, follow these steps:

1. Open the source contract and confirm the new version and approved changes.
1. Verify task associations and eligible unbilled actuals reevaluation.
1. Compare the milestones, invoice plan, or billing schedule with the approved proposal.
1. Confirm that required budget adjustments are completed or assigned to the responsible user.
1. Compare the resulting margin, utilization, and forecasts with the reviewed impact.

### Recover from an application failure

If validation or application fails, the status changes to **Approved - application failed**. Review the batch job and change order errors, resolve the issue, and arrange reprocessing through the batch job.

For example, you might delete a referenced task from the project after you prepare the change order. Restore a valid reference through the permitted correction process before retrying.

Don't treat a failed application as a completed contract amendment. The contract update doesn't retain a partially applied set of approved changes.

## Review contract versions and audit history

Use the contract's version history and change order log to understand what changed, who authorized it, and which amendment produced the current contract.

### Open the change order log file

When you apply a change order, Project Operations creates a change order log file and saves it in **Timeline**. The file contains all changes included in the applied change order.

To open the change order log file, follow these steps:

1. Open **Timeline** and locate the log file for the applied change order.
1. Open the file to review the complete set of changes.
1. Use the log for future reference or reporting.

### Review version and audit details

Each applied change order results in a new contract version. Before-change snapshots and field-level differences support comparison with earlier agreements. Review the baseline captured for approval alongside the final applied version.

The history includes:

- Change order ID, source contract, affected lines, and contract version.
- Original and revised field values.
- Users and timestamps for submission, approval, return for rework, recall, rejection, cancellation, and application.
- Reviewer comments and decision reasons.
- Validation outcomes at submission, approval, and application.
- Task association, reassignment, and removal events.
- Submission order and approval order for parallel change orders.

You can access historical versions from the contract form. Rejected and canceled records retain evidence of the proposed changes and decisions even though those changes weren't applied.

### Export details and share supporting records

Use standard record export capabilities to export change order details for stakeholder review, reporting, or audit, subject to your permissions. Include the relevant supporting documents and decision information according to your organization's process.

Automatic generation of a dedicated formal change proposal document isn't part of the workflow covered in this article. Standard exports and the applied change order log aren't the same as a customer-ready proposal document generator.

## Disable change order management

Only an administrator can change the feature setting. Disabling requires confirmation and is recorded for audit.

If no change orders exist, you can fully disable the feature. If Draft, Submitted, or Approved change orders remain, resolve them through the supported cancellation, deletion, recall, or completion process before disabling. Existing change orders remain searchable and readable after disablement.

## Common issues

| Issue | What to check or do |
| ------ | ------------- |
| **Create new change order** isn't available | Open the confirmed contract and go to the **Change order** tab. Check feature availability, whether it's enabled, and your permissions. |
| **A header field can't be edited** | Confirm that the field is eligible for amendment, the change order is in an editable state, and you have the required permissions. |
| **A project doesn't show an option to create a change order** | This behavior is expected in Phase 1. Open the confirmed contract, go to the **Change order** tab, and select **Create new change order**. |
| **A task doesn't appear for import** | Confirm that the task exists in the WBS, matches the line's transaction classes, and isn't already associated with an incompatible active line. |
| **Another pending change order is reported for a task** | Review the other change order and coordinate approval sequencing. A warning doesn't reserve the task. |
| **A transaction class can't be added to a line** | Check whether another line for the same project already owns that transaction class. |
| **A change item can't be removed** | Identify another active item that depends on it. Revise or separate the dependent changes together. |
| **Submission is blocked** | Resolve invalid lines, missing required values, inconsistent dates, task conflicts, or billing dependencies. Every line must be valid. |
| **A submitted change order can't be edited** | Ask the approver to select **Return for rework**. The status returns to **Draft**, where permitted fields can be edited. |
| **Only some lines should be approved** | Select **Return for rework** and separate excluded changes into a new draft. Approval applies to the complete header. |
| **An approved change order needs changes** | Select **Recall** before it is applied. Edit the resulting draft, validate, and resubmit for approval. Applied change orders can't be recalled. |
| **Approval fails after successful submission** | Recheck the latest contract and task state. Another change order might have introduced a conflict. |
| **Impact values changed** | Refresh the analysis and check whether another approved change changed the baseline. Pending drafts aren't aggregated. |
| **NTE utilization shows **Not applicable**** | Check the billing method and whether a valid, nonzero NTE limit applies. |
| **A project link or billing method can't be changed** | Change orders don't support changing either value on an existing contract line, even for uninvoiced work. |
| **A past effective date can't be selected when creating a change order** | Phase 1 supports current or future effective dates only. Select today or a future date; use the appropriate separate process for historical financial corrections. |
| **Work can be recorded but not invoiced** | Verify the draft-cost setting and whether the scope is approved and applied. Cost recording doesn't establish billing eligibility. |
| **Custom approvals are complete, but the change order isn't **Approved**** | Complete the default approval as the final workflow step. |
| **The change order is approved, but the contract hasn't changed** | Check its effective date and the application batch job's configuration, schedule, and result. |
| **Contract application failed** | Review the batch job and change order errors, resolve the issue, and arrange batch reprocessing. |
| **Rejection didn't remove recorded costs** | This behavior is expected. Review retained cost actuals through the normal financial correction process. |
| **A notification wasn't received** | Ask the administrator to check the configured flow or notification rule. Status transitions don't provide fixed notifications automatically. |
| **The feature can't be disabled** | Resolve outstanding Draft, Submitted, or Approved change orders and retry as an administrator. |

## Customer-specific configuration

### Configure custom approval workflows

Add your organization's custom approval workflow, such as internal business reviews or customer sign-off. Configure the default change order approval as the final step, after all required custom approvals are complete.

Completing a custom approval step alone doesn't mark the change order as approved or apply the changes. The final default approval runs the standard validations and marks the change order **Approved** for batch application.

### Configure the application batch job

A batch job applies approved change orders to their contracts. Configure the job and its schedule according to your organization's processing requirements and effective-date sequencing.

Define who monitors job execution and resolves application failures. An approved change order waits for the batch job to process it according to its effective date.

### Configure notifications

Submission, approval, rejection, and return-for-rework notifications aren't provided as fixed product behavior. Configure notifications by using Power Automate or the Dynamics 365 notification framework, based on change order status transitions.

Confirm the recipients and triggers, including who handles a failed application. **Return for rework** changes the status to **Draft**, not to a separate revision status.

## Additional information

- [Header details for project contracts](project-contract-settings-sales.md)
- [Project contract lines overview](manage-contract-values-project-based-sales.md)
