---
title: Project adjustments
description: This article provides information about project adjustments.
author: ryansandness
ms.author: ryansandness
ms.date: 03/20/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project adjustments

_**Applies To:** Project Operations for manufacturing-based scenarios_

## Adjustments overview

You can configure Microsoft Dynamics 365 Project Operations so that users can make changes to posted transactions. You can adjust project transactions individually, or you can select multiple transactions at a time in a list of all project transactions. Project adjustments are used, for example, to mass-update the billable status, recalculate cost after a configuration change, or update funding sources.

Users can access the project adjustment functionality in several ways:

- Using the **Adjust transactions** page that can be accessed from **Project Management and accounting** \> **Setup**.
- Using the **Adjustment** button on the **Posted project transactions** page that can be accessed from **Project Management and accounting** \> **Transactions**.
- Using the **Adjustment** button on the **Posted project transactions** page in the context of a project. This page can be accessed from **Project Management and accounting** \> **All projects**.

To allow for adjustments, you must enable one or more transaction statuses from **Project Management and accounting** \> **Project Management and accounting parameters** on the **General** tab under the section **Allow adjustment of transaction status**. Examples of transaction statuses include posted transactions, invoiced transactions, or eliminated transactions. Any transaction status that is set to **No** has transactions in that status that doesn't appear within the adjustment process as selectable for adjustment.

## Adjustments process flow

The following steps show the typical flow for processing adjustments.

1. Open the **Project adjustments** page.
2. Select **Select** to search for transactions that meet the expected criteria for adjustment.
3. In the list of transactions, select all transactions or a subset of the transactions for adjustment.
4. Select **Adjust**, and modify the attributes on the line. Alternatively, if the values were manually specified during transaction entry, you can select to enter default system values.
5. The list of transactions is returned, and a check mark appears in the **Pending adjustment** column to indicate where changes were made. Any adjustments that have pending changes are shown in the lower half of the page. There, you can make more detailed changes beyond what was shown on the previous page.
6. Select **Post** to post the adjustment transactions.

Depending on the configuration, new transactions are typically created for the adjustment.

- The **Invoice Status** field of the original transaction is set to **Adjusted**.
- A reversal transaction is created to reverse the original transaction, and the **Status** field is set to **Adjusted**.
- A new transaction is created that has the changes that were made during the adjustment process.

### Select multiple posted project transactions at a time for adjustments and credit notes

A new feature that was introduced in the 10.0.30 release enables the selection of multiple transactions for adjustment at a time from the **Posted project transactions** page.

Before you can use this feature, it must be enabled in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if necessary. In the **Feature management** workspace, search for and select **Multi-select posted project transactions for adjustments and credit notes**, and then select **Enable now**.

This feature enables the following key functionality:

- It can be accessed from the posted transaction page within a project by using the existing **Adjustment** button.
- It enables a multi-row select control on the **Posted project transactions** page. You can apply filters to the list page and select your records before you begin adjustments.
- It disables the **Adjustment** button if any single transaction can't be adjusted, or if you select a combination of credit notes and journals together instead of individually.
- Because of the addition of the multi-row select control, the **Committed cost** link in the ribbon is no longer disabled if multiple rows are selected.
- It adds the following warning message: "You selected more than (selected number) records for adjustment. Proceeding with this action might take some time. Are you sure you would like to proceed with this action?"

This feature also removes step 2 from the process flow that was described earlier in this article. Therefore, any transactions that were selected before the **Adjust transactions** page was opened are included in the list of transactions for adjustment. You don't have to use the **Select** button to search for them.

> [!NOTE] 
> Even if this feature is disabled, you can still select multiple records for adjustment. However, only one record *remains selected*, and the **Select transactions** dialog box appears immediately after you select to open adjustments.

## Adjustment performance improvement

In the 10.0.45 release, a new feature is available that changes how adjustments are processed and improves performance.

Before you can use this feature, it must be enabled in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if necessary. In the **Feature management** workspace, search for and select **Project adjustment posting performance improvements**, and then select **Enable now**.

There are a few different improvements enabled under this feature:

1. This feature changes changes behavior so that project transactions are processed individually, rather than all together. With this change, individual vouchers and journals are created instead of processing all transactions together in a single voucher. This change prevents any adjustment failures from blocking the adjustment of other unrelated transactions. The change also limits the amount of data in a single general ledger journal and voucher which improves reporting and analysis of individual transactions.

2. To assist with fixing configuration issues that can cause adjustment failures, a new form has been introduced to track failures. Once the configuration issue has been resolved, users can select the transaction for adjustment from the list of failures, make the proposed change and see it succeed and removed from the list. If there is a reason the adjustment can't proceed, such as no available funding limit, users can delete the failed adjustment to remove it from the list.

In **Project management and accounting**, navigate to **Periodic**, and **Transactions**. Open **Adjust transaction status**.

This page will give you insight into the failed adjustment and the error text in the reason column.

The **Adjust transaction** button in the ribbon enables you to easily perform the adjustment again. However the form does not remember what change you made, so you will need to apply those changes again in the adjutment process.

3. Multithreading has been enabled to allow the new smaller transaction size to be run in parallel. So intead of waiting for 1000 invidividual lines to run sequentially, we can now use multiple batch tasks to run these lines in parallel, according to the configuration of how many threads to use.

A new parameter in the **Project management and accounting parameters** form has been added in the **General** tab for Max batch tasks for adjustment tasks. The default value is 0, which indicates 4 batch tasks will be used.

With this change it is important to use batch processing in adjustments whenever processing more than a few lines. Because of the increased overhead in creating more journals and vouchers users may see a slight decrease in performance when adjusting without the use of batch, but will see a significant increase in performance when running in batch.

## Adjust dates

When performing an adjustment, you're prompted for an **adjustment date**. This date represents the ledger date or voucher date that can impact the financial date of the transaction. The **adjustment date** defaults to the current date. In some cases, you need to adjust the date when the transaction took place, which is often represented as the **project date**. When you adjust a transaction, the system assumes that you're only adjusting the ledger date and that no edits to the **project date** are necessary. 

A new feature introduced in the 10.0.42 release enables the ability to edit the **project date** or default from the **adjustment date**. This feature is especially useful with timesheets when you log time for the wrong day and don’t catch the error before approval and posting. 

In the **Feature management** workspace, the **Enable editing of project date for project adjustments** feature can be enabled to allow for edits to **project date**. 

When the **Adjust transactions** form opens, a new default values toggle is available to **Set project date from adjustment date**. When this option is selected, the **project date** defaults from the **adjustment date** provided. 

In the **Adjustments** form, the bottom grid where edits can be made also now lets you make manual changes to the **Project date** where previously it was ready only. 

## Troubleshooting when transactions are missing from **Adjust transactions**

You may encounter an issue where you want to adjust a transaction but it doesn't appear within **Adjust transactions**. If an adjustment is started but interrupted by closing the browser window or from your session timing out, then the transaction may be locked in the adjustment cache. You can clear the cache and make the transaction available again by running the periodic process. Use the **Clear adjustments posting cache** page that can be accessed from **Project Management and accounting** \> **Periodic** \> **Transactions** to resolve this issue.

## Scenarios where transactions are unavailable for adjustment

| Scenario Overview               | Configuration Details | Description |
|---------------------------------|-----------------------|-------------|
| Stocked product with multiple funding sources | When a sales order includes a stocked product, has multiple funding sources on the project contract, and the Enable packing slip cancellation for item requirements cancellation feature is enabled.| Item requirements can't be split into multiple sales records.|

## Adjustment transaction statuses that can be enabled or disabled for adjustments

The following statuses can be enabled or disabled on the **General** tab of the **Project management and accounting parameters** page:

- Posted
- Invoice Proposal
- Invoiced
- Estimated
- Eliminated
- Beginning balance (hour)

## Adjustment parameters

These parameters are listed on the **Project management and accounting parameters** page on the **General** tab under the **Adjustment** group and modify behavior for how adjustments are processed.

| Parameter name | Description |
|----------------|-------------|
| Autoupdate field | If this parameter is enabled, the system recalculates cost price and sales price. |
| Allow closed activities | Usually, transactions can't be created for closed activities. If this parameter is enabled, that behavior is overridden. Therefore, adjustments can be created for closed activities. |
| Max batch tasks for adjustment posting | When performing adjustments in batch, the adjustment transactions will be split into this many batch tasks. The number of transactions needs to be larger than the number of tasks in order to be split. For example, if the paramater is set to 6, if 5 transactions are adjusted they will be processed in a single batch task. |
