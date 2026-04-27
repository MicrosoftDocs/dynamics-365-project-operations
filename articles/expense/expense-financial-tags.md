---
title: Use financial tags in Expense Management
description: Learn how financial tags can be used in the Expense management module to track expense transactions across the end-to-end accounting lifecycle without creating new financial dimensions.
author: ajitchandran
ms.author: ajitchandran
ms.date: 04/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Financial tags in Expense Management module (Preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_Applies To: Project Operations Integrated with ERP, Project Operations for manufacturing._

Financial tags in the Expense management module (Preview) enable organizations to capture and track user-defined financial attributes on expense transactions without creating extra financial dimensions. This capability helps track short-term or contextual initiatives, such as campaigns, pilots, or internal events, while keeping the chart of accounts clean and reusable.

When you enable financial tags for expense reports, you can capture tags at both the expense report header and expense line levels. The tags stay consistent through the complete expense processing lifecycle, from expense creation to voucher creation through ledger posting.

The **Enable financial tags for expense reports** feature extends financial tagging support across the entire expense report lifecycle in the **Expense management legacy experience** and the **Expense management reimagined experience**.

The system automatically propagates financial tags entered by users during posting into accounting distributions, subledger entries, and voucher transactions. This process ensures end-to-end traceability between operational expense data and downstream financial records, while providing consistent behavior across both user interfaces.

This feature is available from Dynamics 365 Finance version 10.0.47 or higher.

## Configuration and prerequisites

To use financial tags with expense reports, complete the following configurations.

### Enable required features

To enable the required features, follow these steps:

1. In **System administration > Feature management**:
1. Enable **(Preview)Enable financial tags for expense reports**.
1. When testing the reimagined UI, also enable **Expense reports re-imagined enhancements**.

### Configure financial tags

To configure financial tags, follow these steps:

1. Go to Finance, **General ledger**.
1. Go to **Chart of accounts > Financial tags**. Configure and activate the required financial tags in the applicable legal entities (for example, USMF and USSI).

> [!TIP]
> As a prerequisite, configure the financial tags delimiter. To set up the delimiter, follow these steps:
>
> 1. Go to **General ledger > Ledger setup > General ledger parameters**.
> 1. On the **Financial tags** tab, set the financial tag segment delimiter.
> 1. Enable the Financial tag field visibility in the respective field visibility settings under **Expense Management > Setup > General > Expense report fields / Expense fields visibility (Expense reports re-imagined)**.

### Financial tag controls on expense management workspace

You can enter financial tag fields in the following locations:

- **Expense Management workspace**
  - Creating a new expense report navigates to the **New expense report** form. Select **+New expense report** > under heading **(PREVIEW)FINANCIAL TAGS**.
  - Financial tag values appear in expense line details under the **(Preview) Financial tags** subheading.

## Additional information on financial tags functionality in expense management module

### Financial tags at header and line level

- Enter financial tags at:
  - Expense report header level
  - Individual expense line level
- When you create a new expense line, the system automatically defaults the header-level financial tags to the expense line, which reduces manual data entry.

### Adding unattached expenses

- When you add unattached expenses to an expense report, the system defaults financial tags from the expense report header to the attached expense lines.
- If an expense line already contains financial tag values, the system retains those values.

### Split line scenario (Legacy UI)

- When you split an expense line in **Expense reports (Old UI)**, the system copies financial tags from the original (parent) expense line to all split lines.
- This behavior applies only to the Legacy UI, as the split line capability isn't available in the reimagined experience.

### Itemization lines

- When you itemize an expense line, the system copies financial tags from the original expense line to all related itemization lines.

### Line removal behavior

- When you remove an expense line from an expense report, the system doesn't clear the financial tag values for that expense line.

### Posting and downstream propagation

During expense report posting:

- The system populates financial tags into the accounting distributions.
- The system propagates financial tags to:
  - Subledger entries
  - Voucher transactions

This process ensures complete financial traceability from expense entry to general ledger posting.

### Post-posting updates

- After posting, you can manually update financial tags by using the existing **Edit internal voucher data** functionality.
- Updates you make post-posting apply only at the voucher level and don't reflect back in the original expense report.
- This feature doesn't introduce a new post-posting maintenance experience.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
