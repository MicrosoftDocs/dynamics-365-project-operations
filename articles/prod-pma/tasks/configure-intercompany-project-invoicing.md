--- 
title: Configure intercompany project invoicing
description: This article shows how to set up project invoicing between two companies in your organization. 
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: how-to 
ms.custom: 
  - bap-template  
ms.reviewer: johnmichalak

---
# Configure intercompany project invoicing

[!include [banner](../../includes/banner.md)]

This article shows how to set up project invoicing between two companies in your organization. This task uses the USSI data set.

1. In the navigation pane, go to **Modules > Accounts payable > Vendors > All vendors**.
2. In the **All vendors** list, find and select the desired record.
3. On the Action Pane, select **General**.
4. Select **Intercompany**.
5. Set **Active** to **Yes** to enable intercompany trading.
6. In the **Customer company** field, enter or select a value.
7. In the **My account** field, enter or select a value.
8. Select **Save**.
9. Close the pages to return to the home page.
10. In the navigation pane, go to **Modules > Project management and accounting > Setup > Project management and accounting parameters**.
11. Select the **Intercompany** tab.
12. Move the slider to **Yes** to enable intercompany resource scheduling and timesheets.
13. In the list, mark the selected row.
14. Select **New**.
15. In the **Borrowing legal entity** field, enter or select a value.
16. Select the **Accrue revenue** check box.
17. In the **Default timesheet category** field, enter or select a value.
18. In the **Default expense category** field, enter or select a value.
19. Select **Save**.
20. Close the page.
21. In the navigation pane, go to **Modules > Project management and accounting > Setup > Posting > Ledger posting setup**.
22. In the **Ledger account types** field, select an option.
23. Select **New**.
24. In the **Main account** field of the new row, specify the desired values.
25. Select **Save**.
26. Close the page.
27. In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Transfer price**.
28. Select **New**.
29. In the **Effective date** field, enter a date.
30. In the **Borrowing legal entity** field, enter or select a value.
31. In the **Transfer price model** field, select an option.
32. In the **Pricing** field, enter a number.
33. Select **Save**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
