---
title: Project Operations Regional and Localization Support
description: This topic provides information on the regions supported and localization support for Project Operations
author: stsporen
manager: gurkans
ms.date: 4/29/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: stsporen
---

# Approval Sets
Approval Sets is a feature that groups together Approval requests into smaller subsets of operations. We do this to allow for the processing of Approvals to be ordered by Project and to allow for retrying and sequencing. This improves reliability and traceability of the Approval processing when approving large volumes of Approvals.

Approval Sets hold the overall state of the processing of their related records. When a Approval record is processed using a Approval Set, it will move directly from the Submitted state to the Approved state and the record will be unlinked from the Approval Set. The record will remain in Submitted status with the Approval Set being marked as failed when the record has failed, with the Approval Set logging the error message of the failure.


## Processing Approvals and Approval Sets
Approvals that have been queued for processing are visible under the Processing Approvals view. The system will attempt to process all the entries multiple times asynchronously including retrying the Approval if a prior attempt failed.
The Approval Set Lifetime field records the number of attempts left for processing the set before being marked as failed.

## Failed Approvals and Approval Sets
The Failed Approvals view lists all Approvals that require user intervention. Open the associated Approval Set Logs to identify the cause of the failure.
Pressing Retry will add to the Approval Set Lifetime which will move the Approval Set back to Processing and attempt to process the remaining records.

## Configuring Approval Sets

### Requirements
Approval Sets is in a new feature that was released as part of [Update Release 32](https://docs.microsoft.com/en-us/dynamics365/project-operations/psa/whats-new-ur-32).

###  Enabling the Approval Sets feature
In order to enable this feature, perform the following steps:
1.	Ensure there are no Approvals being processed.
2.	Open Project Parameters.
3.	From the ribbon menu select Feature Control | Enable Modern Approvals.

### Disabling the Approval Sets feature
1.	Ensure there are no Approvals being processed.
2.	Open Project Parameters.
3.	From the ribbon menu select Feature Control | Disable Modern Approvals.


### Configuring the Asynchronous threshold
Approval Sets are created and processing is moved to the background when the selected number of records for Approval being approved exceeds this threshold. Use the field to configure when approval processing should be executed synchronously or asynchronously.
Valid values are 0 (process all requests asynchronously) or numbers greater than 0 (process the approval asynchronously only when the submitted number of approvals exceeds this value).


