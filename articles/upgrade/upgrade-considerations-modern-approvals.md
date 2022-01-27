---
title: Upgrade considerations for Modern Approvals
description: The topic covers the considerations an administrator should follow when enablding Modern approvals functionality.
author: stsporen
ms.date: 01/27/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---

# Upgrade considersations for Modern Approvals 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

As part of the April 2022 Wave 1 Release, the Modern Approvals capabilities will be enabled by default. Modern approvals functionality improves the reliability of the approval logic and ensures that you can determine the reason behind when the approval logic fails.

As part of this change, the status changes of a project approval are updated to move directly from **submitted** to **Approved**. **Pending** is no longer a status for the approvals. To determine if an approval is in a pending state, verify that the approval is part of an approval set and the check the state of the attached approval set.

## Before you upgrade 
Before you upgrade to Modern Approvals, ensure that you have no pending approvals. Modern Approvals doesn't use the **Pending** state and any approvals still marked as **Pending** after upgrade won't be processed.

## After you upgrade
After you upgrade to Modern Approvals, an administrator must complete the following steps to validate that the Cloud Flow, which processes the approvals, has been enabled.

1. Login to [flow.microsoft.com](https://flow.microsoft.com)
2. In the top right of the page, switch your environment to the environment you have upgraded.
3. Select **Solutions** to list the solutions installed on the environment.
4. Select **Project Operations** or **Project Service** from the solutions list.
5. Change the filter from **All** to **Cloud Flows**.
6. Verify that **Project Service – Recurrently Schedule Project Approval Sets** is set to **On**. If it's not, select the flow and then select **Turn on**. 
7. Verify that processing is happening every five mintues by reviewing the **System Jobs** in the environment settings.

## Short term rollback 
If you are unable to update the changes, or you encounter a severe issue with this feature, you can revert back to the original approval flow. First, ensure that there are no pending approvals, and then turn off the **Feature Control | Modern Approvals**. 

## Removing the feature flag
In the October 2022 Wave 2 update, the ability to turn this feature off will be removed.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
