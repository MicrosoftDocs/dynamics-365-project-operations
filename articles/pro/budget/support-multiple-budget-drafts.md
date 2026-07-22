---
title: Support multiple draft budgets
description: Learn about how multiple draft budgets in Project Operations let Project Managers create, compare, and submit budget scenarios. Learn how to enable and manage this feature today.
author: niranjanmaski
ms.date: 07/22/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Support multiple draft budgets

[!INCLUDE [banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Project budgets help Project Managers plan, track, and control the financial performance of projects. A project budget can include cost and sales budget lines for time, material, and expense transaction classes. Project Managers can create a budget, submit it for approval, revise an approved budget, and track budget performance against actuals and forecasts.

The **Enable Multiple Project Budget Drafts** feature lets Project Managers create and maintain more than one draft budget for a project. Each draft budget can represent a different budget scenario, such as a baseline revision, scope change, resource cost change, or risk-adjusted plan. Project Managers can compare draft scenarios and submit the preferred draft budget through the standard project budget approval process.

Use this feature when you want to evaluate budget alternatives before you commit to a formal project budget revision. Draft budgets remain separate from the approved project budget until a draft is submitted and approved.

## Why use multiple draft budgets

Project budgets often need to be revised because of changes in project scope, resource plans, material requirements, expenses, or customer commitments. When only one draft budget is available, Project Managers might have to compare budget alternatives outside Project Operations before they decide which budget should move forward.

Multiple draft budgets help project teams:

- Create separate budget scenarios for the same project.
- Compare draft budgets against the approved budget or against other draft budgets.
- Keep scenario changes isolated from the approved budget baseline.
- Submit the preferred draft budget through the standard approval process.
- Reduce dependency on offline budget scenario planning.

## Prerequisites

Before you use this feature, make sure that the following prerequisites are met:

- Project budget management is available in your Project Operations environment.
- The project is eligible for project budget creation.
- You have permissions to create and update project budgets.
- The **Enable Multiple Project Budget Drafts** feature is enabled in the environment.

## Enable multiple draft budgets

An administrator must enable the feature before you can create and manage multiple draft budgets.

1. In Dynamics 365 Project Operations, go to **Feature management.**
1. Find **Enable Multiple Project Budget Drafts**.
1. Enable the feature.
1. Save the change.
1. Refresh the Project Operations app.

> [!NOTE]
> Feature availability depends on your Project Operations deployment type, environment version, and release wave availability. If the feature isn't visible, verify that the required Project Operations updates are installed in the environment.

## Project budget lifecycle

Project budgets follow the standard project budget lifecycle.

| Status | Description |
|---|---|
| Draft | You can edit the budget. |
| In Review | You submitted the budget for approval. |
| Approved | The budget is approved and used as the current budget baseline. |
| Rejected | The submitted budget isn't approved. You can update and resubmit it. |
| Revised | A previously approved budget version was replaced by a later approved version. |

When you enable multiple draft budgets, more than one draft budget can exist for the same project budget version. Each draft is a separate scenario. You can update one draft without affecting other drafts or the approved budget.

## Budget versioning with multiple drafts

Project Operations uses budget versions to identify budget revisions. When you enable multiple drafts, you can use a major version and a minor version to identify draft budgets. The major version identifies the budget revision cycle. The minor version identifies the separate draft scenario within that revision cycle.

For example, if project budget version 3 is the next revision, draft scenarios might be identified as version 3.1, version 3.2, and version 3.3.

When you create a draft budget, Project Operations determines the budget version based on the current budget state of the project.

| Current project budget state | Result |
|---|---|
| No project budget exists | A draft budget is created for version 1. |
| One or more draft budgets already exist | A new draft budget is created for the same version as the existing draft budgets. |
| An approved budget exists and no draft budget exists | A new draft budget is created for the next version. |
| An approved budget exists and one or more draft budgets exist | A new draft budget is created for the same version as the existing draft budgets. |

This behavior lets Project Managers create multiple alternatives for the same budget revision cycle. For example, if approved budget version 2 exists, a Project Manager can create multiple draft budgets for version 3 and compare them before submitting one draft for approval.

## Create a draft budget manually

Use manual creation when you want to create a draft budget and enter budget lines directly. To create a draft budget manually, follow these steps:

1. Open the project.
1. Select the **Budget** tab.
1. Select **Budget** > **Manual**.
1. Enter the required budget information.
1. Add cost budget lines or sales budget lines.
1. Save the budget.

The budget is created in **Draft** status. If other draft budgets already exist for the project, the new draft is created for the same budget version.

## Create a draft budget by importing from a source

Use import when you want to create a draft budget from a supported source, such as project estimates. To create a draft budget by importing from a source, follow these steps:

1. Open the project.
1. Select the **Budget** tab.
1. Select **Budget** > **Import**.
1. Select the source for the budget lines.
1. Review the import options.
1. Select **Import**.
1. Review and update the imported budget lines as required.

Manual creation and import use the same versioning rules. If an approved budget exists and no draft budget exists, the imported budget is created as the next version. If one or more draft budgets already exist, the imported budget is created as another draft for the same version.

## Work with multiple draft budgets

When multiple draft budgets exist, use the budget selector, budget list, or available budget navigation experience to open the draft that you want to review or update.

For each draft budget, users with the required permissions can:

- Add, update, or remove budget lines.
- Change quantities, amounts, and budget line details.
- Import or re-import budget lines from a supported source.
- Compare the draft with an approved budget or with another draft, where comparison is available.
- Submit the selected draft for approval.
- Delete a draft that's no longer required, if deletion is allowed for the draft status.

> [!IMPORTANT]
> A draft budget is a working scenario. It doesn't become the official project budget baseline until it's submitted and approved.

## Re-import budget lines into a draft

Re-import is available when a draft or rejected budget exists. If multiple draft budgets exist, select the draft budget that should receive the re-imported lines.

When you re-import budget lines, select one of the supported import strategies:

- **Merge Source Lines into Existing Lines** – Updates matching imported lines and adds new source lines. Manually added lines are preserved.
- **Remove Imported Lines and Re-Create While Preserving Manual Lines** – Removes lines that came from the previous import, re-imports from the selected source, and preserves manually added lines.
- **Full Re-Create** – Replaces all budget lines from the selected source, including manually added lines.

Use re-import when source data has changed and the draft budget should be refreshed before it's reviewed or submitted.

## Submit a selected draft for approval

When you decide which draft budget should become the proposed budget revision, submit that draft for approval. To submit a selected draft for approval, follow these steps:

1. Open the project.
1. Select the **Budget** tab.
1. Select the draft budget to submit.
1. Select **Submit**.
1. Confirm the submission.

The selected draft moves to **In Review** and follows the configured budget approval process. Other draft budgets remain separate scenarios unless they're deleted or otherwise handled by your organization's process.

## Approve a draft budget

A reviewer or approver can approve the budget that's in review by using the standard budget approval experience.

When you approve the in-review budget:

- The selected budget becomes the approved budget for the project.
- The previously approved budget version is revised.
- The approved budget is used for budget-to-actual tracking and variance review.

## Revise an approved budget

Use the standard revision process when you need to change an approved project budget. To revise an approved budget, follow these steps:

1. Open the approved project budget.
1. Select **Revise**.
1. Create a new draft budget for the next version.
1. Add or update budget lines.
1. Submit the draft for approval.

When you enable multiple draft budgets, you can create extra drafts for the same revision version and compare them before submitting one for approval.

## Delete a draft budget

You can delete draft budgets that are no longer needed if they're eligible for deletion. To delete a draft budget, follow these steps:

1. Open the project.
1. Select the **Budget** tab.
1. Select the draft budget to delete.
1. Select **Delete**.
1. Confirm the deletion.

When you delete a draft budget, you remove that draft scenario. This action doesn't change the approved budget.

## Security and permissions

Users must have the required project and budget permissions to create, edit, submit, approve, or delete draft budgets. Users with read-only access can view budget information, but they can't update draft budgets unless their security role allows budget editing.

## Considerations

- Use multiple draft budgets for budget scenario planning. They don't replace the standard budget approval process.
- The approved budget remains the official project budget baseline.
- Review draft budgets before submission to make sure that lines, amounts, dates, and dimensions are correct.
- If actual costs already exist for a project, validate that the selected draft budget is appropriate before submitting it for approval.
- Organizations should define naming guidance for draft scenarios so that users can clearly identify the purpose of each draft.

## Additional notes

- The **Budgets** area in the left navigation pane provides a consolidated view of project budgets. You can see projects in this area and expand a project to view the budget versions associated with that project.
- An upcoming release enhances the **Budget List** page to show budget summary information for each budget version. This enhancement helps you review key budget information without opening each budget record individually.
- When you approve a budget, you establish the selected budget as the active project budget baseline. As part of the approval process, the system deletes previous draft budgets for the same project to avoid ambiguity and to maintain a clear source of truth.
- Draft budgets are intended for planning, comparison, and approval preparation. Review and validate the selected draft before approval because the system doesn't retain other draft versions after approval.
- If you need more changes after approval, create a new budget revision or draft budget according to your organization's budget governance process.

## Related information

- [Project budget management overview](projectbudgetmanagement.md)
- [Create a project budget from estimates](create-project-budget-from-estimates.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
