---
title: Approval sets in Project Operations
description: This topic explains how to work with approval sets, requests, and the subsets of those operations.
author: stsporen
manager: tfehr
ms.date: 08/10/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: stsporen
---

# Approval sets in Project Operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Approval sets group approval requests together into smaller subsets of operations. This grouping allows approvals to be processed by project, in a specific order and allows for retrying and sequencing. Grouping the approval requests together improves the reliability and traceability of approval processing for large volumes of approvals.

Approval sets indicate the overall processing state of their related records. When an approval record is processed using an approval set, the record moves from **Submitted** to **Approved**, and is no longer linked to the approval set. If a record fails when it is submitted for approval, the record remains in a status of **Submitted** and the approval set is marked as failed. The approval set logs the error message of the failure.

## Processing approvals and approval sets
Approvals that are queued for processing are visible in the **Processing Approvals** view. The system proccesses all the entries multiple times asynchronously, including retrying an approval if previous attempts failed.

The **Approval Set Lifetime** field records the number of attempts left to process the set before it's marked as failed.

## Failed approvals and approval sets
The **Failed Approvals** view lists all of the approvals that require user intervention. Open the associated approval set logs to identify the cause of the failure.
Selecting **Retry** adds to the approval set lifetime count, moves the approval set back to a status of **Processing**, and attempts to process the remaining records.

## Configure approval sets

### Enable the Approval sets feature
Before you enable the Approval sets feature, verify that there are no approvals currently being processed.

- Go to the **Project parameters** page and select **Feature Control** > **Enable Modern Approvals**.

### Turn off the Approval sets feature
Before you turn off the Approval sets feature, verify that there are no approvals currently being processed.

- Go to the **Project Parameters** page and select **Feature Control** > **Disable Modern Approvals**.

### Configuring the asynchronous threshold 
When approval sets are created, processing moves to the background when the selected number of records for approval exceeds the indicated threshold. Use the **Asynchronous Threshold** field to configure when approval processing should be run synchronously or asynchronously. Select one of the following values:

  - Zero: All requests should be processed asynchronously. 
  - Numbers greater than zero: Approvals are processed asynchronously only when the submitted number of approvals exceeds this value.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
