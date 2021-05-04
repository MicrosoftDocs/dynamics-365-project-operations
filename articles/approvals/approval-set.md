---
title: Approval sets
description: This topic provides information about approval set, requests, and the subsets of those operations.
author: stsporen
manager: tfehr
ms.date: 5/04/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: stsporen
---

# Approval sets

Approval sets groups Approval requests together into smaller subsets of operations. This grouping allows Approvals to be processed in order by Project and allows for retrying and sequencing. Grouping improves the reliability and traceability of Approval processing for large volumes of Approvals.

Approval sets indicate the overall processing state of their related records. When aa Approval record is processed using an Approval set, the record moves from **Submitted** to **Approved**, and is unlinked from the Approval set. If a record fails when it is submitted for approval, the record remains in a status of **Submitted** and the Approval set is marked as failed. The Approval set logs the error message of the failure.

## Processing Approvals and Approval sets
Approvals that are queued for processing are visible in the **Processing Approvals** view. The system tries to process all the entries multiple times asynchronously, including retrying an Approval if previous attempts failed.
The **Approval Set Lifetime** field records the number of attempts left to process the set before it's marked as failed.

## Failed Approvals and Approval sets
The **Failed Approvals** view lists all Approvals that require user intervention. Open the associated Approval set logs to identify the cause of the failure.
Selecting **Retry** adds to the Approval set lifetime count, moves the Approval set back to a status of **Processing**, and attempts to process the remaining records.

## Configure Approval sets

###  Enable the Approval sets feature
Before you enable the Approval sets feature, verify that there are no Approvals currently being processed.

- Go to the **Project parameters** page and select **Feature Control** > **Enable Modern Approvals**.

### Turn off the Approval sets feature
Before you turn off the Approval sets feature, verify that there are no Approvals currently being processed.

- Go to the **Project Parameters** page and select **Feature Control** > **Disable Modern Approvals**.

### Configuring the Asynchronous threshold 
When Approval sets are created, processing moves to the background when the selected number of records for Approval exceeds the indicated threshold. Use the **Asynchronous Threshold** field to configure when approval processing should be run synchronously or asynchronously.
Valid values are:

  - Zero: All requests should be processed asynchronously. 
  - Numbers greater than zero: Approvals are processed asynchronously only when the submitted number of approvals exceeds this value.

