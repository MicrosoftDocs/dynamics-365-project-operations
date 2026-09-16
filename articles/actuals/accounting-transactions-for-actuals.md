---
title: Accounting transactions for project actuals
description: Learn how Microsoft Dynamics 365 Project Operations displays accounting details for project actuals in the ledger accounting currency.
author: abriccetti
ms.author: abriccetti
ms.date: 09/16/2026
ms.topic: concept-article
ms.custom:
  - bap-template
ms.reviewer: johnmichalak
---

# Accounting transactions for project actuals

[!INCLUDE [banner](../includes/banner.md)]

_**Applies to:** Project Operations Integrated with ERP_

Starting with Microsoft Dynamics 365 Project Operations version 4.171.X.X, accounting amounts for an actual display in the accounting currency of the owning company's ledger. The actual continues to use the transaction currency of the original project transaction.

For example, an actual can show the original project transaction in euros while its accounting details show the amount recorded in US dollars for the owning company's ledger.

## What changes

In earlier versions, transaction amounts and accounting amounts were stored on the same actual and used the same currency. Starting with version 4.171.X.X, the accounting details are stored in a related **Accounting transaction** record. As a result, the transaction and accounting amounts can use different currencies.

Project transactions are posted and accounted for in Dynamics 365 Finance. After posting, dual-write synchronizes the resulting accounting details from Finance to Project Operations in Microsoft Dataverse. This synchronization creates and populates the related accounting transaction record and associates it with the corresponding actual. The record includes:

- Accounting amount
- Accounting tax amount
- Account exchange rate
- Accounting date
- Voucher number

The related Accounting transaction record uses the accounting currency of the owning company's ledger. The Actual record retains the transaction currency.

> [!IMPORTANT]
> You don't create or maintain Accounting transaction records manually in Project Operations.

## View accounting details

When synchronized accounting details are available, the **Actual** form displays them in the owning company's ledger accounting currency. The form doesn't display duplicate accounting fields.

The standard **Actual** views continue to show **Accounting amount** and **Accounting tax amount**. Older actuals and actuals that don't have synchronized accounting details continue to show the existing accounting fields.

## Customization considerations

Custom forms, views, reports, exports, and integrations that use accounting details should use the values from the related **Accounting transaction** record when an **Actual** record has one. In particular, use these values when reporting in accounting currency because the transaction currency on the **Actual** record might differ.

Customizations should also account for older **Actual** records and records that don't have synchronized accounting details. For these records, the existing accounting fields on the **Actual** record might still be shown.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
