---
title: Post costs between balance sheet and profit and loss accounts (Preview)
description: Learn how the Post costs feature moves project costs between balance sheet and profit and loss accounts 
author: ryansandness
ms.author: ryansandness
ms.reviewer: johnmichalak
ms.search.form:
ms.topic: concept-article
ms.date: 08/18/2026
ms.custom:
  - bap-template
---

# Post costs overview (Preview)

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

The **Post costs** feature in Dynamics 365 Project Operations lets project accountants manually move project costs between balance sheet (work in progress, or WIP) accounts and profit and loss (P&L) accounts. This feature helps ensure costs are recognized in the same period as the related revenue. **Post costs** moves only cost transactions; revenue is posted separately at invoicing.

## Typical project accounting flows

Most organizations use one of the following approaches to manage how project costs move between balance sheet and the profit and loss statement (P&L):

- **P&L only** – Projects are configured to post directly to P&L. Costs are recognized immediately, and no balance sheet posting occurs.
- **Balance sheet, with manual P&L posting** – Projects are configured to post costs to the balance sheet. Project accountants use **Post costs** to manually move costs to P&L when recognition is appropriate.
- **Balance sheet, with invoice-driven P&L posting** – Projects are configured to post costs to the balance sheet. When the customer is invoiced, costs automatically move from the balance sheet to P&L and revenue is recognized.

  > [!NOTE]
  > Balance sheet costs don't automatically move from the balance sheet when invoiced. **Post costs** can manually move these balances.

- **Balance sheet holding** – Sometimes, costs that are currently on P&L need to move back to the balance sheet. For example, when exploratory work changes into a research and development project.

The accounting flow is determined by a combination of the **Cost and revenue profile**, **Cost and revenue profile rule**, and **line property** capitalization setting.

## Supported project types

**Post costs** applies only to the following project types or contract lines:

- Projects with time and material (T&M) contract lines
- Internal projects

**Post costs** doesn't apply to fixed price projects or investment projects. For those types, the revenue recognition process moves costs as needed.

## Feature details

The following changes are included in the **Post costs** feature for Project Operations Integrated with ERP deployments.

- Enable using the Feature management entry
- Work with integrated project transactions with split cost and revenue records
- Support transaction posting to the balance sheet for internal projects

### Enable using the Feature management entry

A new entry in the **Feature management** workspace turns on the **Post costs** menu item for integrated deployments. The menu item wasn't previously available for this deployment type.

To enable the **Post costs** feature, follow these steps:

1. Go to **System administration** \> **Workspaces** \> **Feature management**.
1. Search for **Enable posting costs from the balance sheet to the income statement**.
1. Select the feature, and then select **Enable now**.

### Work with integrated project transactions with split cost and revenue records

In integrated deployments, you track cost and revenue as separate transaction records. The **Post costs** process includes logic to check the corresponding revenue record before it allows a cost to move from profit and loss (P&L) to the balance sheet. If revenue is already accrued or the transaction is invoiced, the cost isn't eligible to move. You don't see these records in the selection window for **Post costs**.

### Support transaction posting to the balance sheet for internal projects

As part of this feature, internal projects now support transactions posting directly to the balance sheet when you configure the **Cost and revenue profile**. Previously, there was no way to move costs out of the balance sheet, but now **Post costs** enables this flow.

## Related information

- [Configure accounting for billable projects](configure-accounting-billable-projects.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
