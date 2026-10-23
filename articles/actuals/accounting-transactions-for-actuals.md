---
title: Accounting transactions for project actuals
description: Learn how Microsoft Dynamics 365 Project Operations displays accounting details for project actuals in the ledger accounting currency.
author: abriccetti
ms.author: abriccetti
ms.date: 10/16/2026
ms.topic: concept-article
ms.custom:
  - bap-template
ms.reviewer: johnmichalak
---

# Accounting transactions for project actuals

[!INCLUDE [banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP_

Accounting transactions are available starting with Microsoft Dynamics 365 Project Operations version 4.171.X.X. After you complete the feature enablement and dual-write setup, accounting amounts for an actual display in the accounting currency of the owning company's ledger. The actual continues to use the transaction currency of the original project transaction.

For example, an actual can show the original project transaction in euros while its accounting details show the amount recorded in US dollars for the owning company's ledger.

## Enable the feature

The end-to-end experience requires both the accounting-transactions dual-write map and the Dataverse **Accounting transactions** feature. There's no separate **Feature management** switch to enable for this feature in Dynamics 365 Finance.

### Configure dual-write in Finance

To configure dual-write in Finance, follow these steps:

1. In Finance, go to **Data management** > **Dual-write**.
1. If the accounting-transactions map isn't available, apply or update the **Dynamics 365 Project Operations dual-write Entity Maps** solution.
1. Activate version **1.0.0.0** of the **Project Operations integration actuals (msdyn_accountingtransactions)** map, and select **Run**.

This map synchronizes accounting transaction records in one direction, from Finance to Dataverse. It's an additional map, not a replacement for **Project Operations integration actuals (msdyn_actuals)**. Keep the existing actuals map running.

### Enable accounting transactions in Dataverse

> [!IMPORTANT]
> After you enable the **Accounting transactions** feature, you can't disable it.

To enable accounting transactions in Dataverse, follow these steps:

1. In Project Operations, go to **Settings** > **Parameters**, and open the parameter record.
1. Select **Feature control** > **Accounting transactions**.
1. In the confirmation dialog, select **Enable**.

The Dataverse feature controls the display of accounting details on the **Actual** form. Enabling it doesn't activate the dual-write map or synchronize accounting transaction records.

## What changes

In earlier versions, transaction amounts and accounting amounts were stored on the same actual and used the same currency. With the feature enabled and its dual-write map running, the accounting details are stored in a related **Accounting transaction** record. As a result, the transaction and accounting amounts can use different currencies.

Project transactions continue to be posted and accounted for in Dynamics 365 Finance through existing accounting processes. After posting, the accounting-transactions dual-write map synchronizes the resulting accounting details from Finance to Project Operations in Microsoft Dataverse. This synchronization creates and populates the related accounting transaction record and associates it with the corresponding actual. The record includes:

- Accounting amount
- Accounting tax amount
- Account exchange rate
- Accounting date
- Voucher number

The related Accounting transaction record uses the accounting currency of the owning company's ledger. The Actual record retains the transaction currency.

> [!IMPORTANT]
> You don't create or maintain Accounting transaction records manually in Project Operations.

## View accounting details

When you enable the feature and synchronized accounting details are available, the **Actual** form displays them in the owning company's ledger accounting currency. The form doesn't display duplicate accounting fields.

The standard **Actual** views continue to show **Accounting amount** and **Accounting tax amount**. Older actuals and actuals that don't have synchronized accounting details continue to show the existing accounting fields.

## Customization considerations

Custom forms, views, reports, exports, and integrations that use accounting details should use the values from the related **Accounting transaction** record when an **Actual** record has one. In particular, use these values when reporting in accounting currency because the transaction currency on the **Actual** record might differ.

Customizations should also account for older **Actual** records and records that don't have synchronized accounting details. For these records, the existing accounting fields on the **Actual** record might still be shown.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
