---
title: Project adjustments
description: This article provides information about project adjustments.
author: ryansandness
ms.author: ryansandness
ms.date: 10/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project adjustments

_**Applies To:** Project Operations for stocked/production-based scenarios_

## Adjustments overview

You can configure Microsoft Dynamics 365 Project Operations so that users can make changes to posted transactions. You can adjust project transactions individually, or you can select multiple transactions at a time in a list of all project transactions. Project adjustments are used, for example, to mass-update the billable status, recalculate cost after a configuration change, or update funding sources.

Users can access the project adjustment functionality in several ways:

- By using the **Adjust transactions** page that can be accessed from **Project Management and accounting** \> **Setup**.
- By using the **Adjustment** button on the **Posted project transactions** page that can be accessed from **Project Management and accounting** \> **Transactions**.
- By using the **Adjustment** button on the **Posted project transactions** page in the context of a project. This page can be accessed from **Project Management and accounting** \> **All projects**.

To allow for adjustments you must enable one or more transaction statuses from **Project Management and accounting** \> **Project Management and accounting paramaters** on the **General** tab under the section **Allow adjustment of transaction status**. Examples of transaction statuses include posted transactions, invoiced transactions, or eliminated transactions. Any transaction status that is set to **No** will have transactions in that status that won't appear within the adjustment process as selectable for adjustment.

A configuration option that is named **Always create adjustment transaction** is currently available in Project management and accounting parameters. You can disable this option to update the original transaction instead of creating new transactions during adjustment in a subset of scenarios. It has been announced that this parameter will be deprecated by March 1, 2023. After March 1, 2023, the system will always behave as if the option is enabled.

## Adjustments process flow

The following steps show the typical flow for processing adjustments.

1. Open the **Project adjustments** page.
2. Select **Select** to search for transactions that meet the expected criteria for adjustment.
3. In the list of transactions, select all transactions or a subset of the transactions for adjustment.
4. Select **Adjust**, and modify the attributes on the line. Alternatively, if the values were manually specified during transaction entry, you can select to enter default system values.
5. The list of transactions is returned, and a check mark appears in the **Pending adjustment** column to indicate where changes were made. Any adjustments that have pending changes are shown in the lower half of the page. There, you can make additional detailed changes beyond what was shown on the previous page.
6. Select **Post** to post the adjustment transactions.

Depending on the configuration, new transactions are typically created for the adjustment.

- The **Invoice Status** field of the original transaction is set to **Adjusted**.
- A reversal transaction is created to reverse the original transaction, and the **Status** field is set to **Adjusted**.
- A new transaction is created that has the changes that were made during the adjustment process.

### Selecting multiple posted project transactions at a time for adjustments and credit notes

A new feature that was introduced in the 10.0.30 release enables the selection of multiple transactions for adjustment at a time from the **Posted project transactions** page.

Before you can use this feature, it must be enabled in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if it's required. In the **Feature management** workspace, search for and select **Multi-select posted project transactions for adjustments and credit notes**, and then select **Enable now**.

This feature enables the following key functionality:

- It can be accessed from the posted transaction page within a project by using the existing **Adjustment** button.
- It enables a multi-row select control on the **Posted project transactions** page. You can apply filters to the list page and select your records before you begin adjustments.
- It disables the **Adjustment** button if any single transaction can't be adjusted, or if you select a combination of credit notes and journals together instead of individually.
- Because of the addition of the multi-row select control, the **Committed cost** link in the ribbon is no longer disabled if multiple rows are selected.
- It adds the following warning message: "You have selected more than (selected number) records for adjustment. Proceeding with this action might take some time. Are you sure you would like to proceed with this action?"

This feature also removes step 2 from the process flow that was described earlier in this article. Therefore, any transactions that were selected before the **Adjust transactions** page was opened will be included in the list of transactions for adjustment. You don't have to use the **Select** button to search for them.

> [!NOTE] 
> Even if this feature is disabled, you can still select multiple records for adjustment. However, only one record will *remain selected*, and the **Select transactions** dialog box will appear immediately after you select to open adjustments.

## Adjusting dates

When performing an adjustment, you will be prompted for **adjustment date**. This date will represent the ledger date or voucher date which can impact the financial date of the transaction. The **adjustment date** will default to the current date. In some cases you will need to adjust the date when the transaction took place, which is often represented as the **project date**. When adjusting a transaction, it will assume that you are only adjusting the ledger date, and that no edits to the **project date** are necessary. 

A new feature that was introduced in the 10.0.42 release enables the ability to edit the **project date** or default from the **adjustment date**. This is especially useful in the case of timesheets where time was logged for the wrong day, and it wasn't caught before approval and posting. 

In the **Feature management** workspace, the **Enable editing of project date for project adjustments** feature can be enabled to allow for edits to **project date**. 

When the **Adjust transactions** form opens, a new default values toggle is available to **Set project date from adjustment date**. When this option is selected, the **project date** will default from the **adjustment date** provided. 

In the **Adjustments** form, the bottom grid where edits can be made will also now let you make manual changes to the **Project date** where previously it was ready only. 

## Adjustment transaction statuses that can be enabled or disabled for adjustments

The following statuses can be enabled or disabled on the **General** tab of the **Project management and accounting parameters** page:

- Posted
- Invoice Proposal
- Invoiced
- Estimated
- Eliminated
- Beginning balance (hour)

## Adjustment parameters

These parameters are listed on the **Project management and accounting parameters** page on the **General** tab under the **Adjustment** group and will modify behavior for how adjustments are processed. 

| Parameter name | Description |
|----------------|-------------
| Always create adjustment transaction | If this parameter is enabled, the adjustment process will always create a new reversing transaction and new adjusted transaction when there is a financial or reporting impact. If the parameter is disabled, the adjustment process will update the original transaction instead of creating a reversal and new transaction for a scenario such as an update of the transaction text. |
| Autoupdate field | If this parameter is enabled, the system will recalculate cost price and sales price. |
| Use adjustment date as new project | This parameter is used to move transactions into a future fiscal period before the system supported this function. We don't recommend that you use it, because it changes the business date of the transaction and will be deprecated in a future release. |
| Allow closed activities | Usually, transactions can't be created for closed activities. If this parameter is enabled, that behavior is overridden. Therefore, adjustments can be created for closed activities. |
