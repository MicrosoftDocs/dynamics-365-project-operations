---
title: Upgrade considerations for Modern Approvals
description: The article covers the points that administrators should consider when they enable Modern Approvals functionality.
author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Upgrade considerations for Modern Approvals 

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

As part of the April 2022 Wave 1 Release, the Modern Approvals functionality is enabled by default. This functionality improves the reliability of the approval logic and ensures that you can determine the reason if the approval logic fails.

As part of this change, status changes for project approvals are updated. The status now goes directly from **Submitted** to **Approved**. **Pending** is no longer a status for approvals. To determine whether an approval is pending, verify that the approval is part of an approval set, and the review the state of the attached approval set.

## Before you upgrade

Before you upgrade to Modern Approvals, make sure that you have no pending approvals. Modern Approvals doesn't use the **Pending** status. Therefore, any approvals that are still marked as **Pending** after upgrade won't process.

## After you upgrade

After you upgrade to Modern Approvals, an administrator must validate that the cloud flow that processes approvals has been enabled.

1. Sign in to [flow.microsoft.com](https://flow.microsoft.com)
1. In the upper right of the page, switch your environment to the environment that you've upgraded.
1. Select **Solutions** to list the solutions that are installed in the environment.
1. In the solution list, select **Project Operations** or **Project Service**.
1. Change the filter from **All** to **Cloud Flows**.
1. Verify that the **Project Service – Recurrently Schedule Project Approval Sets** option is set to **On**. If it isn't, select the flow, and then select **Turn on**.
1. Verify that processing is occurring every five minutes by reviewing the **System Jobs** list in the **Settings** area.

## Short-term rollback

If you can't uptake the changes, or if you encounter a severe issue with this feature, you can temporarily revert to the original approval flow by performing the following steps:
1. Sign-in to your environment and verify that there are no pending approvals.
1. Go to **Settings** > **Project Parameters**.
1. Select **Feature Control** and then select **Modern Approvals** to turn off feature.

## Removing the feature flag

In the October 2022 Wave 2 update, the ability to turn off this feature is removed. All customers must enable this feature without the ability to disable.

## How to manage in-flight approvals while having the Modern Approvals feature enabled

If you have in-flight approvals that were submitted with the old logic and now have the feature enabled, you will need to resubmit these entries.

To resubmit in-flight approvals after the Administrator has enabled Modern Approvals, or the update has forced the enablement of Modern Approvals, follow these steps.

1. The Resource who submitted the time entry, should recall the time entry. Recalling the time entry removes any **Pending** approvals and the system changes them back to a pre-submission state.
1. The Resource should submit the entry again. This creates a new approval using Modern Approvals and an associated Approval Set.
1. The Approver is able to approve the entries from grid using Modern Approval.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
