--- 
title: Configure intercompany project invoicing
description: This article shows how to set up project invoicing between two companies in your organization. 
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: how-to 
ms.custom: 
  - bap-template  
ms.reviewer: johnmichalak

---
# Configure intercompany project invoicing

[!INCLUDE [banner](../../includes/banner.md)]

This article shows how to set up project invoicing between two companies in your organization. This task uses the USSI data set.

1. In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.
1. In the **All vendors** list, find and select the desired record.
1. On the Action Pane, select **General**.
1. Select **Intercompany**.
1. Set **Active** to **Yes** to enable intercompany trading.
1. In the **Customer company** field, enter or select a value.
1. In the **My account** field, enter or select a value.
1. Select **Save**.
1. Close the pages to return to the home page.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.
1. Select the **Intercompany** tab.
1. Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.
1. In the list, mark the selected row.
1. Select **New**.
1. In the **Borrowing legal entity** field, enter or select a value.
1. Select the **Accrue revenue** check box.
1. In the **Default timesheet category** field, enter or select a value.
1. In the **Default expense category** field, enter or select a value.
1. Select **Save**.
1. Close the page.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.
1. In the **Ledger account types** field, select an option.
1. Select **New**.
1. In the **Main account** field of the new row, specify the desired values.
1. Select **Save**.
1. Close the page.
1. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.
1. Select **New**.
1. In the **Effective date** field, enter a date.
1. In the **Borrowing legal entity** field, enter or select a value.
1. In the **Transfer price model** field, select an option.
1. In the **Pricing** field, enter a number.
1. Select **Save**.



[!INCLUDE [footer-include](../../includes/footer-banner.md)]
