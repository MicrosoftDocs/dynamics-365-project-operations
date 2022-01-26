---
title: Upgrade considerations for Modern Approvals
description: The topic covers additional considerations an administrator should follow when enablding modern approvals as part of Wave 1 2022
author: stsporen
ms.date: 11/09/2020
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---

# Upgrade Considersations for Modern Approvals in Project Operations and Project Service Automation

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

As part of our April 2022 Wave Release, we will be enabling by default our Modern Approvals Capabilities. Modern Approval improves the reliability of our approval logic and ensures that end customer is able to determine the reason for failure should a failure occur.

As part of this change the state changes that a project approval will transition have been updated to move directly from **submitted** to **approved**, no longer going through **pending**. In order to determine if an approval is in a pending state, validate the approval is part of an approval set and check the state of the attached approval set.

## Required prior to upgrade steps
Please ensure that you have no pending approvals, Modern Approvals does not use “Pending” state and in process “Pending” project approvals will not be procced by Modern Approvals.

## Required post upgrade steps
Please validate that the Cloud Flow which processes the approvals has been enabled.

As the administrastor confirm as follows:

1.	Login to [flow.microsoft.com](https://flow.microsoft.com)
2.	Switch your **environment** to the environment you have upgraded (select on the top right)
3.	Select **Solutions** to list the installed solutions in the environment
4.	Select **roject Operations** or **Project Service** from the solutions list
5.	Change the filter from **All** to **Cloud Flows**
6.	Verify**Project Service – Recurrently Schedule Project Approval Sets** is **On** 
7.	If it is not marked as **On**, select the flow and press **Turn on** in the menu.
8.	Validate that processing is happening every 5 mintues by reviewing the **System Jobs** within the environment settings.

## Short Term Rollback 
If you find you are not able to update the changes or encounter a severe issue with this feature you are able to revert back to the original approval flow, first be ensuring there are no pending approvals and adjusting the **Feature Control | Modern Approvals** to off. 

## Deprecation of Feature Flag
In the Octover 2022 Wave 2 update we will be removing the ability to turn this feature off.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
