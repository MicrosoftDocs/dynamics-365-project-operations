---
title: Header details for project quotes
description: This article provides information about the information and settings that apply to and impact project quotes. (Sales)
author: rumant
ms.date: 12/03/2022
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Header details for project quotes

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

This article explains the information that applies to a project quote. This includes the settings that impact all quote lines, and information about the quote that is summarized across all the line items to drive the KPIs of the project quote.

The following table lists the summary information fields on a project quote that are unique to Dynamics 365 Project Operations or have some important changes in behavior from Dynamics 365 Sales quotes.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Type | Summary tab (hidden) | This option set field hash the following options:</br>- Work-based (available only when Project Operations is installed)</br>- Item-based (available only when Project Operations and Sales are installed)</br>- Service maintenance-based (available when Dynamics 365 Field Service is installed) | When you use the Project Operations application, the value of this field is automatically set to **Work-based**. This classifies the quote as a project-based quote. A quote should be project-based to enable all project-specific extensions and functionality. |
| Potential Customer | Summary tab | Reference to the customer's company or account record. When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. | The currency on the project quote is defaulted based on the currency of the customer. This can, however, be changed before the quote is saved. |
| Account Manager | Summary tab | The name of the account Manager for this deal. When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. | The Account manager is responsible for managing the relationship with the customer through the completion of this project. Based on the bookable resource record tied to the Account manager, the contracting unit defaults on the project quote. |
| Contracting Unit | Summary tab | The organization unit that is responsible for the delivery of the project or projects associated with this quote. When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. | The contracting unit is the division of the company that will be executing the projects after the deal is closed. Every contracting unit has a currency, and this currency is used to report estimated and actual costs incurred during the execution of the project. |
| Product price list | Summary tab | This is the price list that is used to default prices on the product-based quote lines. The list of options for this field shows a list of price lists where the price list currency matches the currency on the quote. When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. This field on the opportunity is defaulted from the account record but can be changed. | When a quote is won, the field value is copied to the project contract that is created. |
| Currency | Summary tab | This indicates the currency that will be used for reporting the value of this deal. This is also the currency in which the customer will be invoiced if the deal is won. When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. This field on the opportunity defaults from the account record but can be changed by the user. | After a quote is saved, this field is no longer editable. This is used to default the product and project price lists on the quote. The currency on the quote is used to match the currency on the price list. |
| Not-to-exceed limit | Summary tab | This indicates the negotiated cap on the final value that the customer is agreeing to for this deal. | This cap is evaluated during execution and is applicable across all line items and projects associated with this deal. |
| Requested delivery date | Summary tab | When a quote is created from an opportunity, this field is copied from the corresponding field on the opportunity. | This date is used as the end date for generating invoice schedules. |

Below are the tabs and KPIs available on a project quote that are unique to Project Operations or have some important changes in behavior from Sales quotes:

| **Field** | **Location** | **Description** |
| --- | --- | --- |
| Profitability analysis | Tab on the Quote | The tab shows the following metrics:</br>- Total chargeable cost</br></br>- Total non-chargeable cost</br>- Total revenue</br>- Total revenue (base)</br>- Gross margin</br>- Adjusted gross margin|
| Comparison to Customer Expectations | Tab on the Quote | This tab shows the following metrics:</br>- Estimated completion</br>- Requested completion</br>- Customer budget</br>- Quote value |
| Quote analysis | Tab on the Quote | This tab summarizes the following top KPIs for a project quote</br>- Comparison to customer expectations for budget and schedule</br>- Gross margin</br>- Adjusted gross margin |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
