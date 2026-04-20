---
title: Manage multiple customers on project quotes
description: Learn how to manage project quotes involving multiple customers, set up billing splits, and handle primary customer records effectively in Project Operations.
author: poojafandan
ms.date: 01/30/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Manage multiple customers on project quotes

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

Project quotes support the scenario where the proposal involves multiple customers who fund the deal. The **Summary** tab of the Quote has the **Potential customer** field that identifies the primary customer of the deal. Set up other customers for the deal on the **Customers** tab of the project quote.

All quote customers on the **Customers** tab of the project quote default as quote line customers on any **new** project-based quote lines you create for the quote. Any existing project-based quote lines don't inherit new quote customer records.

Product-based quote lines automatically associate to the primary customer who is also the customer in the **Potential Customer** field on the **Summary** tab of the quote.

Add, update, or delete quote customers and quote line customers at any time before you win the quote.

## Concept of a primary customer

The customer on the summary tab of the project quote as the potential customer is the primary customer of the quote. When you try to delete the primary customer from customers list on quote, you see an error that a primary customer record on a quote can't be deleted.

Don't update the primary customer from the customer list on the quote. However, you can influence the primary customer by changing the potential customer on the **Summary** tab of the quote. When you update this field on the **Quote Summary**, the newly selected potential customer is added as a new quote customer with the **Primary** flag set. The old potential customer is still a customer on the quote.

## Create, update, or delete a quote customer record

You can create, update, or delete a quote customer from the **Quote customers** tab on the **Quote** page. The fields listed in the following table are on the quote customer record of a project quote.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Account | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Lists all the active accounts. This field is locked after the record is created. To update it, delete the record, and re-create it. If you record any actuals, or if the quote customer record is a primary customer, you can't delete the record. | Quote customers are copied over as quote line customers when a quote line is created. Quote customers are also copied over to the project contract customers when a quote is won. |
| Billing split percent | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Represent the percentage of each unbilled sales transaction that you attribute to this quote customer. | Copied over to new quote lines and to project contract customers. |
| Bill to Contact Name | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This is a text field and should be used to identify the Invoice contact person for this customer. These are defaulted from the related account record | Copied over to project contract customers when a Quote is won and in turn to the Bill to Contract name field on the Invoice that is generated for this customer. |
| Bill to Name | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This text field should be used to identify the invoice contact person for this customer. | Copied to the project contract customers when a quote is won and in turn to the **Bill to Contract Name** field on the invoice that is generated for this customer. |
| Payment Terms | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | This is an option set with values that default from the related account record. | Copied to the project contract customers when a quote is won and in turn, to the **Bill to Contract Name** field on the invoice that is generated for this customer, |
| Is Rounding | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Indicates if this customer is a default rounding customer for this deal. | Copied to the project contract customers when a quote is won. |
| Not-to-exceed limit | Editable grid on the **Quote Customers** tab and the **Main** and **Quick Create** forms for a quote customer. | Indicates if there's a negotiated limit or cap to the overall amount that you invoice to this customer for this engagement | Copied to the project contract customers when a quote is won. |

## Editing billing split percentages

You can edit the billing split percentages by using the in-line grid edit experience. When the billing split percentages don't total 100%, an error occurs. After you update the billing split percentages, refresh the page to remove the error.

You can also try selecting **Evenly Distribute** on the quote customers' subgrid. This action allocates billing splits to all quote customers. If there's any rounding factor, add it to the rounding customer. One of the quote customers is always tagged as the rounding customer. This means that the quote customer record has the **Rounding** flag set to **Yes**. Typically this is the primary customer of the quote, but you can change that.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
