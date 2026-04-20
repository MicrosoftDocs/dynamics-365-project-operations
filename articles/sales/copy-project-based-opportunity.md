---
title: Copy project opportunities
description: Learn how to copy project-based opportunities in Project Operations with step-by-step instructions. Simplify opportunity management and streamline your workflow.
author: poojafandan
ms.date: 02/05/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Copy project opportunities

[!include [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You can easily copy project opportunities to create new project opportunities.

1. Go to the **Project Opportunities** list page and select an opportunity from the list. Or, open the details page of a specific opportunity.
1. From either page, select **Copy**. A dialog opens that contains the following field information. Depending on the values you select in this dialog, the copy process might change.

    | **Field** | **Description** | **Downstream impact** |
    | --- | --- | --- |
    | Topic | Enter the relevant topic of the target opportunity. When the dialog opens, the system sets it to the topic of the source opportunity with **copy** appended to it. | There's no downstream impact for this field. |
    | Owning Company | The company that's responsible for delivery of the projects that are associated with this deal. When the dialog opens, the system sets the field to the owning company of the source opportunity. You can change the owning company to an alternate company. | The owning company is the legal entity that executes the project after the deal is closed. The currency of the owning company must match the currency of the contracting unit. |
   | Account | References the customer's company or account record. When the dialog opens, the system sets it to the account on the source opportunity. | This field is the primary customer on the opportunity. |
    | Contracting Unit | The organization unit responsible for the delivery of the projects associated with this deal. When the dialog opens, the system sets it to the contracting unit of the source opportunity. | The contracting unit is the division of the company that executes the projects after the deal is closed. Every contracting unit has a currency, and this currency reports estimated and actual costs incurred during the project. |
    | Currency | The currency that the deal is transacted in. When the dialog opens, the system sets it to the currency of the source opportunity. | Currency defaults a price list and builds financial estimates on the quote. Eventually, the currency invoices the customer when the deal is won. |
    | Copy pricing | A Yes/No value that indicates if the pricing on the opportunity should be copied from the source opportunity. | If **Yes** is selected, price lists are copied from the source to the target opportunity. If **No** is selected, price lists default based on the latest price lists that you set up. If the target Owning company is different Owning company, the Copy pricing defaults to **No**. |

1. Select **OK**. The system creates a copy of the project opportunity based on the selected parameters and opens the new project opportunity.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
