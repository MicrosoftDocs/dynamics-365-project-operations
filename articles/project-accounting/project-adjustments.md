---
title: Project adjustments
description: This article provides information about project adjustments.
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project adjustments

_**Applies To:** Project Operations for manufacturing-based scenarios_

## Adjustments overview

You can configure Microsoft Dynamics 365 Project Operations so that users can make changes to posted transactions. You can adjust project transactions individually, or you can select multiple transactions at a time in a list of all project transactions. Use project adjustments, for example, to mass-update the billable status, recalculate cost after a configuration change, or update funding sources.

Users can access the project adjustment functionality in several ways:

- By using the **Adjust transactions** page that you can access from **Project Management and accounting** \> **Setup**.
- By using the **Adjustment** button on the **Posted project transactions** page that you can access from **Project Management and accounting** \> **Transactions**.
- By using the **Adjustment** button on the **Posted project transactions** page in the context of a project. You can access this page from **Project Management and accounting** \> **All projects**.

To allow adjustments, enable one or more transaction statuses from **Project Management and accounting** \> **Project Management and accounting parameters** on the **General** tab under the section **Allow adjustment of transaction status**. Examples of transaction statuses include posted transactions, invoiced transactions, or eliminated transactions. If you set any transaction status to **No**, transactions in that status don't appear within the adjustment process as selectable for adjustment.

## Adjustments process flow

The following steps show the typical flow for processing adjustments.

1. Open the **Project adjustments** page.
1. Select **Select** to search for transactions that meet the expected criteria for adjustment.
1. In the list of transactions, select all transactions or a subset of the transactions for adjustment.
1. Select **Adjust**, and modify the attributes on the line. Alternatively, if you manually specified the values during transaction entry, you can select to enter default system values.
1. The list of transactions is returned, and a check mark appears in the **Pending adjustment** column to indicate where you made changes. The lower half of the page shows any adjustments that have pending changes. You can make more detailed changes beyond what was shown on the previous page.
1. Select **Post** to post the adjustment transactions.

Depending on the configuration, the system typically creates new transactions for the adjustment.

- The system sets the **Invoice Status** field of the original transaction to **Adjusted**.
- The system creates a reversal transaction to reverse the original transaction, and sets the **Status** field to **Adjusted**.
- The system creates a new transaction that has the changes that you made during the adjustment process.

### Select multiple posted project transactions for adjustments and credit notes

The 10.0.30 release introduces a feature that enables you to select multiple transactions for adjustment at a time from the **Posted project transactions** page.

Before you can use this feature, you must enable it in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if necessary. In the **Feature management** workspace, search for and select **Multi-select posted project transactions for adjustments and credit notes**, and then select **Enable now**.

This feature enables the following key functionality:

- You can access it from the posted transaction page within a project by using the existing **Adjustment** button.
- It enables a multiselect control on the **Posted project transactions** page. You can apply filters to the list page and select your records before you begin adjustments.
- It disables the **Adjustment** button if any single transaction can't be adjusted, or if you select a combination of credit notes and journals together instead of individually.
- Because of the addition of the multiselect control, the **Committed cost** link in the ribbon is no longer disabled if multiple rows are selected.
- It adds the following warning message: "You selected more than (selected number) records for adjustment. Proceeding with this action might take some time. Are you sure you would like to proceed with this action?"

This feature also removes step 2 from the process flow that was described earlier in this article. Therefore, the list of transactions for adjustment includes any transactions that you selected before opening the **Adjust transactions** page. You don't have to use the **Select** button to search for them.

> [!NOTE]
> Even if you disable this feature, you can still select multiple records for adjustment. However, only one record _remains selected_, and the **Select transactions** dialog box appears immediately after you select to open adjustments.

## Adjustment performance improvement

In version 10.0.45, a new feature changes how the system processes adjustments and improves performance.

Before you can use this feature, you must enable it in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if necessary. In the **Feature management** workspace, search for and select **Project adjustment posting performance improvements**, and then select **Enable now**.

This feature enables several improvements:

1. The feature changes the behavior so the system posts project transactions individually, rather than all together. With this change, the system creates individual vouchers and journals instead of processing all transactions together in a single voucher. This change prevents any adjustment failures from blocking the adjustment of other unrelated transactions. The change also limits the amount of data in a single general ledger journal and voucher, which improves reporting and analysis of individual transactions.

1. To assist with fixing configuration problems that can cause adjustment failures, the feature introduces a new form to track failures. After you resolve the configuration problem, you can select the transaction for adjustment from the list of failures, make the proposed change, and see it succeed and removed from the list. If there's a reason the adjustment can't proceed, such as no available funding limit, you can delete the failed adjustment to remove it from the list.

   In **Project management and accounting**, go to **Periodic**, and **Transactions**. Open **Adjust transactions status**.

   This page provides visibility into the failed adjustment and the error text in the reason column.

   The **Adjust transaction** button in the ribbon enables you to easily perform the adjustment again. However, the form doesn't remember what change you made, so you need to apply those changes again in the adjustment process.

1. The feature adds a new Infolog on adjustment failure. It displays the message "Posting failed for some transactions. You can view the errors in the Adjust transactions status page." The Infolog provides a "view errors" link to take you directly to this new page.

1. The feature enables multithreading to allow the new smaller transaction size to run in parallel. Instead of waiting for 1,000 individual lines to post sequentially, multiple batch tasks now run these lines in parallel, based on the configured number of threads.

The feature adds a new parameter in the **Project management and accounting parameters** form in the **General** tab for **Max batch tasks for adjustment tasks**. The default value is 0, which indicates four batch tasks are used.

With this change, it's important to use batch processing in adjustments whenever you're processing more than a few lines. Because of the increased overhead in creating more journals and vouchers, there might be a slight decrease in performance when adjusting without batch. But there's a significant increase in performance when running in batch.

> [!NOTE]
> Multiple performance improvements were added in the 10.0.46 and 10.0.47 releases focusing on set-based processing. Users see an improved experience in the adjustment form when working with a large number of transactions and sending the adjustments to batch.

## Adjust dates

When you perform an adjustment, the system prompts you for an **adjustment date**. This date represents the ledger date or voucher date that can affect the financial date of the transaction. The system sets the **adjustment date** to the current date by default. In some cases, you need to adjust the date when the transaction took place, which is often represented as the **project date**. When you adjust a transaction, the system assumes that you're only adjusting the ledger date and that no edits to the **project date** are necessary.

A new feature introduced in the 10.0.42 release enables the ability to edit the **project date** or default from the **adjustment date**. This feature is especially useful with timesheets when you log time for the wrong day and don’t catch the error before approval and posting.

In the **Feature management** workspace, enable the **Enable editing of project date for project adjustments** feature to allow edits to the **project date**.

When the **Adjust transactions** form opens, a new default values toggle is available to **Set project date from adjustment date**. When you select this option, the **project date** defaults from the **adjustment date** provided.

In the **Adjustments** form, the bottom grid where you make edits now lets you make manual changes to the **Project date** where previously it was read only.

## Troubleshooting when transactions are missing from **Adjust transactions**

You might encounter an issue where you want to adjust a transaction but it doesn't appear within **Adjust transactions**. If you start an adjustment but interrupt it by closing the browser window or your session times out, the transaction might be locked in the adjustment cache. You can clear the cache and make the transaction available again by running the periodic process. Use the **Clear adjustments posting cache** page that you can access from **Project Management and accounting** \> **Periodic** \> **Transactions** to resolve this issue.

Starting with the 10.0.45 release, a new Infolog appears within adjustments if you select a transaction for adjustment that is already in progress. The message displays: "One or more transactions couldn't be selected for adjustment because they're already being processed. If this isn't expected, wait until adjustments are complete and clear the adjustments posting cache."

## Scenarios where transactions are unavailable for adjustment

| Scenario Overview               | Configuration Details | Description |
|---------------------------------|-----------------------|-------------|
| Stocked product with multiple funding sources | When a sales order includes a stocked product, has multiple funding sources on the project contract, and the **Enable packing slip cancellation for item requirements cancellation** feature is enabled.| Item requirements can't be split into multiple sales records.|

## Adjustment transaction statuses that you can enable or disable for adjustments

Enable or disable the following statuses on the **General** tab of the **Project management and accounting parameters** page:

- Posted
- Invoice Proposal
- Invoiced
- Estimated
- Eliminated
- Beginning balance (hour)

## Adjustment parameters

These parameters appear on the **Project management and accounting parameters** page on the **General** tab under the **Adjustment** group. They modify how the system processes adjustments.

| Parameter name | Description |
|----------------|-------------|
| Autoupdate field | If you enable this parameter, the system recalculates cost price and sales price. |
| Allow closed activities | Usually, you can't create transactions for closed activities. If you enable this parameter, you override that behavior. You can create adjustments for closed activities. |
| Max batch tasks for adjustment posting | When you perform adjustments in batch, the system splits the adjustment transactions into this many batch tasks. The number of transactions must exceed the number of tasks to be split. For example, if you set the parameter to six and adjust five transactions, the system processes them in a single batch task. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]