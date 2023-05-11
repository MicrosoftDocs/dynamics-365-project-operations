---
title: Upgrade considerations for Modern Approvals
description: The article covers the points that administrators should consider when they enable Modern Approvals functionality.
author: stsporen
ms.date: 01/31/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Upgrade considerations for Modern Approvals 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

As part of the April 2022 Wave 1 Release, the Modern Approvals functionality will be enabled by default. This functionality improves the reliability of the approval logic and ensures that you can determine the reason if the approval logic fails.

As part of this change, status changes for project approvals are updated. The status now goes directly from **Submitted** to **Approved**. **Pending** is no longer a status for approvals. To determine whether an approval is pending, verify that the approval is part of an approval set, and the review the state of the attached approval set.

## Before you upgrade

Before you upgrade to Modern Approvals, make sure that you have no pending approvals. Modern Approvals doesn't use the **Pending** status. Therefore, any approvals that are still marked as **Pending** after upgrade won't be processed.

## After you upgrade

After you upgrade to Modern Approvals, an administrator must validate that the cloud flow that processes approvals has been enabled.

1. Sign in to [flow.microsoft.com](https://flow.microsoft.com)
2. In the upper right of the page, switch your environment to the environment that you've upgraded.
3. Select **Solutions** to list the solutions that are installed in the environment.
4. In the solution list, select **Project Operations** or **Project Service**.
5. Change the filter from **All** to **Cloud Flows**.
6. Verify that the **Project Service – Recurrently Schedule Project Approval Sets** option is set to **On**. If it isn't, select the flow, and then select **Turn on**.
7. Verify that processing is occurring every five minutes by reviewing the **System Jobs** list in the **Settings** area.

## Short-term rollback

If you can't uptake the changes, or if you encounter a severe issue with this feature, you can temporarily revert to the original approval flow by performing the following steps:
1. Sign-in to your environment and verify that there are no pending approvals.
2. Go to **Settings** > **Project Parameters**.
3. Select **Feature Control** and then select **Modern Approvals** to turn off feature.

## Removing the feature flag

In the October 2022 Wave 2 update, the ability to turn this feature off will be removed. All customers will now have this feature enabled without the ability to disable.

## Dealing with in-flight approvals while having the modern approvals feature enabled

If you have inflight approvals that were submitted with the old logic and now have the feature enabled, please perform the following steps to resubmit these entries.
1. The Administrator has enabled modern approvals, or the update has forced the enablement of Modern Approvals.
2. The Resource who submitted the time entry, should recall the time entry. This will cause any Pending Approvals to be deleted and the system to roll back into a pre-submission state.
3. The Resource should submit the entry again. This will create a new approval within Modern Approvals and an associated Approval Set.
4. The Approver will be able to approve the entries from grid using Modern Approval.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
