---
title: Project adjustments
description: This article provides information about project adjustments
author: ryansandness
ms.date: 10/25/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Project adjustments

_**Applies To:** Project Operations for stocked/production-based scenarios_

## Adjustments overview

You can configure Microsoft Dynamics 365 Project Operations so users can make changes to posted transactions. You can adjust project transactions individually or select multiple transactions from a list of all project transactions. Project adjustments are used, for example, to mass update the billable status, recalculate cost after a configuration change, or update funding sources.

Users can access the project adjustment functionality in several ways:

- Using the **Adjust transactions** form accessible from **Project Management and accounting** - > **Setup**.
- Using the **Adjustment** button within the **Posted project transactions** form accessible from **Project Management and accounting** - > **Transactions**.
- Using the **Adjustment** button within the **Posted project transactions** form within the context of a project, accessible from **Project Management and accounting** - > **All projects**.

To allow for adjustments you need to enable one or more transaction statuses within project management, and change accounting parameters to yes. For example, transaction statuses would be posted transactions, invoiced transactions, or eliminated transactions.

There is a configuration option that can be disabled to update the original transaction instead of creating new transactions during adjustment in a subset of scenarios. This option is available in **Project management and accounting** parameters and is named **Always create adjustment transaction**.
This parameter has been announced to be deprecated by March 1, 2023. After March 1, 2023 the system will behave as if the option is on.

## Adjustments process flow

The typical flow for processing adjustments is described below:

1. Open the **Project adjustments** form.
2. Select the **Select** button to search for transactions that meet the expected criteria for adjustment.
3. From the list of transactions, select all transactions or a subset of the transactions for adjustment.
4. Select **Adjust** and modify the attributes on the line or select to default values from the system defaults if the values were manually specified during transaction entry.
5. The list of transactions is returned and the **Pending adjustment** column is checked to indicate where changes were made. Any adjustments with pending changes are shown in the bottom half of the window where you can make additional detailed changes beyond what was shown in the previous screen.
6. Select the **Post** button to post the adjustment transactions.
7. Depending on the configuration, most often new transactions are created for the adjustment.
    - The original transaction is marked as **Invoice Status** = **Adjusted**.
    - A reversal transaction is created to reverse the original transaction with **Status** = **Adjusted**.
    - A new transaction is created with the changes made in the adjustment process.


### Multi-select posted project transactions for adjustments and credit notes

A new feature was introduced in the 10.0.30 release to allow for multi-selecting transactions to adjust from within the project posted transaction form.

Before you can use this feature, it must be enabled in your system. Admins can use the **Feature management** workspace to check the status of the feature and enable it if needed. From the **Feature management** workspace, search for and select **Multi-select posted project transactions for adjustments and credit notes**, and then select **Enable now**.

Key functionality enabled by this feature include:

- It is accessible from the posted transaction page within a project using the existing adjustment button.
- It enables a multi-select control from the **Posted project transactions** form. You can apply filters to the list page and select your records prior to beginning adjustments.
- Disables the **Adjustment** button if any single transaction can't be adjusted, or if you select a combination of credit notes and journals together rather than individually.
- With the addition of the multi-row select control, the **Committed cost** window is no longer disabled when multiple rows are selected.
- A warning message: **You have selected more than (selected number) records for adjustment. Proceeding with this action might take some time. Are you sure you would like to proceed with this action?**

This feature also removes step 2 from the process flow so that any transactions that were selected prior to opening **Adjustments** will be in the list to adjust, instead of needing to use the **Select** button.

> [!NOTE] Even with this feature disabled, multi-selection of records is now possible for adjustment. But if the feature is disabled, only a single record will remain selected, and users will see the select transactions dialog after immediately clicking to open adjustments.

## Adjustment transaction statuses that can be enabled or disabled for adjustments

These statuses can be enabled or disabled from the **General** tab of the **Project management and accounting parameters** form.

- Posted
- Invoice Proposal
- Invoiced
- Estimated
- Eliminated
- Beginning balance (hour)

## Adjustment Parameters

| Parameter Name  | Parameter Description  |
|----------------|-----------------------|
| Always create adjustment transaction     | The system will always create a new reversing entry and transaction when there is a financial or reporting impact. When this setting is disabled, it updates the original transaction instead of creating a new transaction for a scenario such as updating the transaction text.          |
| Autoupdate field     | This parameter has the system recalculate cost price and sales price.         |
| Use adjustment date as new project     | This feature is used to move transactions into a future fiscal period before the system supported this function. It isn't recommended as it changes the business date of the transaction and will be deprecated in a future release.          |
| Allow closed activities     | Normally transactions can't be created for closed activities. Enabling this setting will override that behavior and allow adjustments to be created for closed activities.          |

