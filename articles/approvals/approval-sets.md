---
title: Approval sets
description: This article explains how to work with approval sets, requests, and the subsets of those operations.
author: suvaidya
ms.date: 01/23/2026

ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Approval sets

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Approval sets group approval requests into smaller subsets of operations. This grouping allows you to process approvals by project, in a specific order, and it supports retrying and sequencing. Grouping the approval requests together improves the reliability and traceability of approval processing for large volumes of approvals.

Approval sets indicate the overall processing state of their related records. When an approval set processes an approval record, the record moves from **Submitted** to **Approved**, and the record is no longer linked to the approval set. If a record fails when you submit it for approval, the record stays in a status of **Submitted** and the approval set is marked as failed. The approval set logs the error message of the failure.

## Processing approvals and approval sets

You can see approvals that are queued for processing in the **Processing Approvals** view. The system processes all the entries multiple times asynchronously, including retrying an approval if previous attempts failed.

The **Approval Set Lifetime** field records the number of attempts remaining to process the set before it's marked as failed.

Periodic activation processes approval sets based on a **Cloud Flow** named **Project Service - Recurrently Schedule Project Approval Sets**. You can find this flow in the **Solution** named **Project Operations**.

Make sure that you activate that flow by completing the following steps.

1. As the administrator, sign in to [flow.microsoft.com](https://powerautomate.microsoft.com).
1. In the upper-right corner, switch to the environment that you use for Dynamics 365 Project Operations.
1. Select **Solutions** to list the solutions that are installed in the environment.
1. In the solution list, select **Project Operations**.
1. Change the filter from **All** to **Cloud Flows**.
1. Verify that the **Project Service – Recurrently Schedule Project Approval Sets** flow is set to **On**. If it isn't, select the flow, and then select **Turn on**.
1. Verify that processing occurs every five minutes by reviewing the **System Jobs** list in the **Settings** area within your Project Operations Dataverse environment.

## Failed approvals and approval sets

The **Failed Approvals** view lists all of the approvals that require user intervention. Open the associated approval set logs to identify the cause of the failure.
Selecting **Retry** adds to the approval set lifetime count, moves the approval set back to a status of **Processing**, and attempts to process the remaining records.

## Configuring the asynchronous threshold for approval sets

When you create approval sets, processing moves to the background when the selected number of records for approval exceeds the indicated threshold. Use the **Asynchronous Threshold** field to configure when approval processing should run synchronously or asynchronously. Select one of the following values:

- Zero: Process all requests asynchronously.
- Numbers greater than zero: Process approvals asynchronously only when the submitted number of approvals exceeds this value.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
