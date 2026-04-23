---
title: Use financial tags in Expense Management
description: Learn how financial tags can be used in the Expense management module to track expense transactions across the end-to-end accounting lifecycle without creating new financial dimensions.
author: ajitchandran
ms.author: ajitchandran
ms.topic: conceptual
ms.date: 04/22/2026
ms.service: dynamics-365-project-operations
ms.subservice: expense-management
---

# Financial tags in Expense Management module

_Applies To: Project Operations Integrated with ERP, Project Operations for manufacturing._

Financial tags in the Expense management module enable organizations to capture and track user-defined financial attributes on expense transactions without creating additional financial dimensions. This capability helps track short-term or contextual initiatives-such as campaigns, pilots, or internal events-while keeping the chart of accounts clean and reusable.

With financial tags enabled for expense reports, tags can be captured at both the expense report header and expense line levels and are carried consistently through the complete expense processing lifecycle, from expense creation to voucher creation through ledger posting.

## Overview

The **Enable financial tags for expense reports** feature extends financial tagging support across the entire expense report lifecycle in both the experiences- **Expense management legacy experience** and the **Expense management re-imagined experience** as well.

Financial tags entered by users are automatically propagated during posting into accounting distributions, subledger entries, and voucher transactions. This ensures end-to-end traceability between operational expense data and downstream financial records, while providing consistent behavior across both user interfaces.

This feature is available from **Finance & Operation version 10.0.47 or higher**

## Configuration and prerequisites

To use financial tags with expense reports, complete the following configurations.

### Enable required features

1. In **System administration > Feature management**:

- Enable **(Preview)Enable financial tags for expense reports**
- When testing the re-imagined UI, also enable **Expense reports re-imagined enhancements**

### Configure financial tags

In **General ledger**:

1. Go to **Chart of accounts > Financial tags**
   - Configure and activate required financial tags in the applicable legal entities (for example, USMF and USSI).

> [!TIP]
> As a pre-requisite, financial tags delimiter must be configured and can be done using
> 1. Go to **General ledger > Ledger setup > General ledger parameters**
> 1. On the **Financial tags** tab, set the financial tag segment delimiter.
> 1. Enable Financial tag field visibility in the respective field visibility settings under **Expense Management** > **Setup** > **General** >  ****Expense report fields / Expense fields visibility (Expense reports re-imagined)**

### Financial tag controls on expense management workspace

Financial tag fields are available for data entry in the following locations:
- **Expense Management workspace**
  - Creating a new expense report navigates to the New expense report form. Click **+New expense report** > under heading **FINANCIAL TAGS**
  - Financial tag values are displayed in expense line details under **Financial tags** subheading. 

## Additional information on financial tags functionality in expense management module

### Financial tags at header and line level

- Financial tags can be entered at:
  - Expense report header level
  - Individual expense line level
- When a new expense line is created, header-level financial tags are automatically defaulted to the expense line, reducing manual data entry.

### Adding unattached expenses

- When unattached expenses are added to an expense report, financial tags default from the expense report header to the attached expense lines.
- If an expense line already contains financial tag values, those values are retained.

### Split line scenario (Legacy UI)

- When an expense line is split in the **Expense reports (Old UI)**, financial tags from the original (parent) expense line are copied to all split lines.
- This behavior applies only to the Legacy UI, as the split line capability isn’t available in the re-imagined UI.

### Itemization lines

- When an expense line is itemized, financial tags from the original expense line are copied to all related itemization lines.

### Line removal behavior

- When an expense line is removed from an expense report, the financial tag values for that expense line aren’t cleared.

### Posting and downstream propagation

During expense report posting:

- Financial tags are populated into the accounting distributions.
- Financial tags are propagated to:
  - Subledger entries
  - Voucher transactions

This ensures complete financial traceability from expense entry to general ledger posting.

### Post-posting updates

- After posting, financial tags can be manually updated using the existing **Edit internal voucher data** functionality.
- Updates made post-posting apply only at the voucher level and aren’t reflected back in the original expense report.
- No new post-posting maintenance experience is introduced as part of this feature.
