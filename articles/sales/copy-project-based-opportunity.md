---
title: Copy project opportunities
description: This article provides information about copying project-based opportunities in Project Operations.
author: poojafandan
ms.date: 03/01/2024
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Copy project opportunities

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Project opportunities can easily be copied to create new project opportunities. 

1. Go to the **Project Opportunities** list page and select an opportunity from the list. Or, open the details page of a specific opportunity. 
2. From either page, select **Copy**. A dialog page will open that contains the following field information. Depending on the values selected in this dialog, the copy process may change.

    | **Field** | **Description** | **Downstream impact** |
    | --- | --- | --- |
    | Topic | Enter the relevant topic of the target opportunity. When the dialog opens, the system will set it to the topic of the source opportunity with **copy** appended to it. | There's no downstream impact for this field. |
    | Owning Company | The company that is responsible for delivery of the projects that are associated with this deal. When the dialog box is opened, the system sets the field to the owning company of the source opportunity. You can change the owning company to an alternate company. | The owning company is the legal entity that will be executing the project after the deal is closed. The currency of the owning company must match the currency of the contracting unit. |
   | Account | References the customer's company or account record. Wen the dialog opens, the system will set it to the account on the source opportunity. | This field is the primary customer on the opportunity. |
    | Contracting Unit | The organization unit responsible for the delivery of the projects associated with this deal. When the dialog opens, the system will set it to the contracting unit of the source opportunity. | The contracting unit is the division of the company that executes the projects after the deal is closed. Every contracting unit has a currency, and this currency is used to report estimated and actual costs incurred during the project. |
    | Currency | The currency that the deal is transacted in. When the dialog page opens, the system will set it to the currency of the source opportunity. | Currency is used to default a price list and build financial estimates on the quote. Eventually, the currency is used to invoice the customer when the deal is won. |
    | Copy pricing | A Yes/No value that indicates if the pricing on the opportunity should be copied from the source opportunity. | If **Yes** is selected, price lists are copied from the source to the target opportunity. If **No** is selected, price lists are defaulted based on the latest price lists that were set up.If the target Owning company is different Owning company, the Copy pricing will be defaulted to **No**. |

4. Select **OK**. The system creates a copy of the project opportunity based on the selected parameters and the new project opportunity is opened.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
