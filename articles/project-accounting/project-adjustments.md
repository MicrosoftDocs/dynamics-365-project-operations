---
title: Project adjustments
description: This article provides information about project adjustments
author: ryansandness
ms.date: 10/03/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: ryansandness
---

# Project adjustments

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

## Adjustments overview

You can configure Project Operations so users can make changes to posted transactions. You can adjust project transactions individually or select multiple transactions from a list of all project transactions. Project adjustments are used frequently for situations such as mass updating the billable status, recalculating cost after a configuration change, or updating funding sources to name a few.

Users can adjust transactions by using the Adjust Transactions form, the Posted project transactions form, and the Posted transactions link from within a Project.
To allow for adjustments you will need to enable one or more transaction types within project management and accounting parameters to yes. Available options include:

- Posted
- Invoice Proposal
- Invoiced
- Estimated
- Eliminated
- Beginning balance (hour)

There is a configuration option that can be disabled to update the original transaction instead of creating new transactions during adjustment in a subset of scenarios. This parameter is available in project management and accounting parameters and is named Always create adjustment transaction.
This parameter has been announced to be deprecated by March 1, 2023 and afterward the system will behave as if the option is on.

### Multi-select posted project transactions for adjustments and credit notes

A new feature was introduced in the 10.0.30 release to allow for multi-selecting transactions to adjust from within the project posted transaction form.

Before you can use this feature, it must be turned on in your system. Admins can use the Feature management workspace to check the status of the feature and turn it on if it's required. In the Feature management workspace, find and select the feature that's named Multi-select posted project transactions for adjustments and credit notes, and then click the Enable now button.

Key functionality enabled by this feature include:

- This feature is accessible from the posted transaction page within a project using the existing adjustment button.
- This feature enables a multi-select control from the posted project transactions form. You can apply filters to the list page and select your records prior to beginning adjustments.
- This feature will disable the adjustment button if any single transaction can not be adjusted or if you select a combination of credit notes and journals together rather than individually.
- With the addition of the multi-row select control, the Committed cost window is no longer disabled with multiple rows selected.
- A warning message is added telling users this may take a long time if more than 1,000 records were selected. Users will see “You have selected more than %1 records for adjustment. Proceeding with this action might take some time. Are you sure you would like to proceed with this action?”
