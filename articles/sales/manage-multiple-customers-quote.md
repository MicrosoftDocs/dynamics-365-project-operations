---
title: Manage multiple customers on a project-based quote
description: This article provides information about working on quotes that involve multiple customers who will fund the project.
author: poojafandan
ms.date: 02/25/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Manage multiple customers on a project-based quote

_**Applies To:** Project Operations Integrated with ERP_

Project-based quotes support the scenario where the proposal involves multiple customers who fund the deal. The **Summary** tab of the Quote has the **Potential customer** field, which identifies the primary customer of the deal. Set up other customers for the deal on the **Customers** tab of the project quote.

All quote customers on the **Customers** tab of the project quote default as quote line customers on any **new** project-based quote lines you create for the quote. Any existing project-based quote lines don't inherit new quote customer records you create after them.

You can add, update, or delete quote customers and quote line customers at any time before you win the quote. Set up a valid customer on the quote as a customer in the Owning company or Legal entity on the **Customers** page. You set up legal entities in the **Project management and accounting** module of Dynamics 365 Project Operations. The legal entities appear as Companies in the **Project sales and delivery** modules of Project Operations.

## Concept of a primary customer

The customer you list on the **Summary** tab of the project quote as the potential customer is the primary customer of the quote. If you try to delete the primary customer from the customers list on the quote, you receive an error that a primary customer record on a quote can't be deleted.

Don't update the primary customer from the customer list on the quote. However, you can influence the primary customer by changing the potential customer on the **Summary** tab of the quote. When you update this field on the **Quote Summary**, the newly selected potential customer is added as a new quote customer with the **Primary** flag set. The old potential customer remains a customer on the quote.

## Create, Update, or Delete a quote customer record

A quote customer can be created, updated, or deleted from the **Quote customers** tab on the **Quote** page. The fields listed in the following table are on the quote customer record of a project quote.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Account | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Lists all the active accounts. This field is locked after the record is created. If you want to update it, delete the record, and re-create it. If you have recorded any actuals, or if the quote customer record is a primary customer, you will be allowed to delete the record. | Quote customers are copied over as quote line customers when a quote line is created. Quote customers are also copied over to the project contract customers when a quote is won. |
| Billing split percent | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Represent the percentage of each unbilled sales transaction that will be attributed to this quote customer. | Copied over to new quote lines created and to project contract customers. |
| Bill to Contact Name | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This is a text field and should be used to identify the Invoice contact person for this customer. These are defaulted from the related account record | Copied over to project contract customers when a Quote is won and in turn to the Bill to Contract name field on the Invoice that is generated for this customer. |
| Bill to Name | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This text field should be used to identify the invoice contact person for this customer. | Copied to the project contract customers when a quote is won and in turn to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| Payment Terms | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This is an option set with values that default from the related account record. | Copied to the project contract customers when a quote is won and in turn to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| Is Rounding | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Indicates if this customer is a default rounding customer for this deal. | Copied to the project contract customers when a quote is won. |
| Owning Company | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | The Legal entity that this customer is set up with in the **Project management and accounting** module. This field is read-only and is set to the owning company of the quote itself. The list of customers to add in the **Account** field is already filtered to the list from this owning company in the **Project management and accounting** module of Project Operations. | The Owning company equates to the concept of Legal entity in the **Project management and accounting** module of Project Operations. All costs and revenue accruing from this project is accounted for in the General ledger of the owning company, |
| Not-to-exceed limit | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Indicates if there is a negotiated limit or cap to the overall amount that will be invoiced to this customer for this engagement. | Copied to the project contract customers when a quote is won. |

## Editing billing split percentages

You can edit the billing split percentages by using the in-line grid edit experience. When the billing split percentages don't total 100%, an error will occur. After you update the billing split percentages, refresh the page to remove the error.

You can also try selecting **Evenly Distribute** on the quote customers' subgrid. This action allocates billing splits to all quote customers. If there is any rounding factor, that will be added to the rounding customer. One of the quote customers is always tagged as the rounding customer. this means that the quote customer record has the **Rounding** flag set to **Yes**. Typically this is the primary customer of the quote, but that can be changed.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
