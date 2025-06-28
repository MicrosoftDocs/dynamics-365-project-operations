---
title: Copy project quotes
description: This article provides information about how to copy project quotes in Project Operations.
author: poojafandan
ms.author: poojafandan
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Copy project quotes

_**Applies To:** Core deployment - deal to proforma invoicing_

You can easily create a new Project quote by copying an existing one. 

- To copy a Project quote, on the **Project Quotes** list page or the **Project Quote** details page, select the Project quote you want to copy, and then select **Copy**.

This will open a dialog page where you can enter the parameters of the copy. The following table lists the fields that are included in the dialog page. Depending on the values you select, the copy process may change.

| **Field** | **Description** | **Downstream impact** |
| --- | --- | --- |
| Topic | Enter the relevant topic, or name, of the target quote. When the dialog opens, the system will set it to the topic of the source quote with **-copy** appended to it. | |
| Potential Customer | Reference to the customer's company or account record. When the dialog opens, the system will set it to the account on the source quote. | This field is the primary customer on the quote. |
| Contracting Unit | The organization unit that is responsible for the delivery of the project(s) associated with this deal.
When the dialog opens, the system will set it to the contracting unit of the source quote. | Contracting unit is the division of the company that will execute the projects after the deal is closed. Every contracting unit has a currency. The currency is used to report estimated and actual costs incurred during the execution of the project. |
| Currency | This is the currency that the deal is transacted in. When the dialog opens, the system will set it to the currency of the source quote. This can be modified and if it is change, the **Copy Pricing** field is always set to **No**. This is because the price lists on source quote are no longer relevant. | Currency is used to default a price list, to build a financial estimate on the quote,  and eventually to invoice the customer when the deal is won. |
| Requested Delivery Date | This is the date of delivery requested by the customer. | This is used as the end date when creating invoicing dates along a specific frequency. |
| Copy pricing | A Yes/No value indicates whether the pricing on the quote should be copied from the source quote. | If **Yes** is selected, the project price list and product price list references are copied from the source quote to the target quote. If **No** is selected, price lists are re-defaulted based on the latest price lists that were set up on the account or project parameters. |

When you select **OK** on the dialog page, the system creates a copy of the project quote based on the parameters selected in the dialog. The new project quote opens. 

> [!NOTE]
> The following information is not copied from the Source to the Target quote:
>
> - Invoice schedules
> - Quote and quote line customers
> - Project reference on the project – based quote lines
> -Customer budget information
>
>Because this information is very specific to each quote, these fields and records are not copied. Quote lines for projects and products, estimates on quote line details, and not-to-exceed values at the quote level are copied. Price and cost rate defaults depend on the **Copy pricing** option selected on the **Copy parameters** dialog page.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
