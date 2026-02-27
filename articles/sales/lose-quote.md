---
title: Copy project quotes
description: This article provides information about how to copy project quotes in Project Operations.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Copy project quotes

_**Applies To:** Project Operations Core_

You can easily create a new project quote by copying an existing one. 

- To copy a project quote, on the **Project Quotes** list page or the **Project Quote** details page, select the project quote you want to copy, and then select **Copy**.

This action opens a dialog where you can enter the parameters for the copy. The following table lists the fields included in the dialog. Depending on the values you select, the copy process might change.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Topic | Enter the relevant topic, or name, of the target quote. When the dialog opens, the system sets it to the topic of the source quote with **-copy** appended to it. | |
| Potential Customer | Reference to the customer's company or account record. When the dialog opens, the system sets it to the account on the source quote. | This field is the primary customer on the quote. |
| Contracting Unit | The organization unit that's responsible for the delivery of the projects associated with this deal.
When the dialog opens, the system sets it to the contracting unit of the source quote. | Contracting unit is the division of the company that executes the projects after the deal is closed. Every contracting unit has a currency. The currency reports estimated and actual costs incurred during the execution of the project. |
| Currency | This is the currency for the deal. When the dialog opens, the system sets it to the currency of the source quote. You can modify this value. If you change it, the **Copy Pricing** field is always set to **No**. This change happens because the price lists on source quote are no longer relevant. | Currency defaults a price list, builds a financial estimate on the quote, and eventually invoices the customer when the deal is won. |
| Requested Delivery Date | This is the date of delivery requested by the customer. | This date is used as the end date when creating invoicing dates along a specific frequency. |
| Copy pricing | A Yes/No value that indicates whether the pricing on the quote should be copied from the source quote. | If **Yes** is selected, the project price list and product price list references are copied from the source quote to the target quote. If **No** is selected, price lists are re-defaulted based on the latest price lists that were set up on the account or project parameters. |

When you select **OK** on the dialog, the system creates a copy of the project quote based on the parameters you selected. The new project quote opens. 

> [!NOTE]
> The following information isn't copied from the source to the target quote:
>
> - Invoice schedules
> - Quote and quote line customers
> - Project reference on the project – based quote lines
> - Customer budget information
>
>Because this information is specific to each quote, the process doesn't copy these fields and records. The process copies quote lines for projects and products, estimates on quote line details, and not-to-exceed values at the quote level. Price and cost rate defaults depend on the **Copy pricing** option you select on the **Copy parameters** dialog.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
