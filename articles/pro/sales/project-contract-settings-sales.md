---
title:  Header details for project contracts
description: This article provides information about the fields and the information about project contracts in Project Operations.
author: poojafandan
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Header details for project contracts

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core_

This article provides information about fields that apply to the entire project contract, including settings that impact all contract lines. It also includes information about the contract that is summarized across all the line items to drive KPIs of the project contract.

The following table lists the fields on a project contract that are unique to Dynamics 365 Project Operations or have some important changes in behavior from sales orders in Dynamics 365 Sales.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Type | **Summary** tab (hidden) | This field is an option set with the following options:</br>- **Work-based** (Available only when Project Operations is installed)</br>- **Item-based** (Available only when Project Operations and Sales are installed)</br>- **Service Maintenance-based** (Available when Dynamics 365 Field Service is installed) | In Project Operations, the value of this field defaults to**Work-based** and classifies the contract as a project-based contract. A contract should be project-based to enable all project-specific extensions and functionality. |
| Potential Customer | **Summary** tab | The reference to the customer's company or account record. When you create a contract from a quote, this field is copied from the corresponding field on the quote record. | The currency on the project contract defaults based on the currency of the customer. You can change this currency before saving the contract. |
| Account Manager | **Summary** tab | The name of the Account Manager for this deal. When you create a contract from a quote, this field is copied from the corresponding field on the quote record. | The Account Manager is responsible for managing the relationship with the customer through the completion of the project. Based on the bookable resource record tied to the Account Manager, the contracting unit defaults on the project contract. |
| Contracting Unit | **Summary** tab | The organization unit responsible for the delivery of the projects associated with this contract. When you create a contract from a quote, this field is copied from the corresponding field on the quote record. | The contracting unit is the division of the company that executes the projects. Every contracting unit has a currency, and this currency is used to report estimated and actual costs incurred during the project. |
| Product Price List | **Summary** tab | This price list defaults prices on product-based contract lines. The list of drop-down options for this field shows a list of price lists where the price list currency matches the currency on the contract. When you create a contract from a quote, this field is copied from the corresponding field on the quote record. On the project contract, this field is defaulted from the account record but can be changed. | There is no downstream relevance for this field. |
| Currency | **Summary** tab | The currency used to report the value of this deal and the currency in which the customer is invoiced. When you create a contract from a quote, this field is copied from the corresponding field on the quote record. On the project contract, this field defaults from the account record but can be changed. | After you save a contract, this field is no longer editable. This field defaults the product and project price lists on the contract. The currency on the contract is used to match the currency on the price list. |
| Not-to-Exceed Limit | **Summary** tab | This field indicates the negotiated cap on the final value that the customer agrees to for this deal. | The cap is evaluated during execution and is applicable across all line items and projects associated with this deal. |
| Requested Delivery Date | **Summary** tab | When you create a contract from a project quote, this field is copied from the corresponding field on the project quote. | This date is used as the end date to generate invoice schedules. |

The following KPIs are available on the **Contract Performance** tab of a project contract. 

> [!NOTE]
> All amounts on the **Contract Performance** tab are expressed in the default currency of the environment.

| Field | Location | Description |
| --- | --- | --- |
| Contract Value | Overall contract | The total value of the project contract.|
| Billed Amount | Overall contract | The sum of the amounts on all invoices against this contract.|
| Cost Incurred | Overall contract | The sum of all cost actuals logged on all projects that are mapped to the contract. |
| Gross Margin | Overall contract | Billed amount - Cost incurred till date / Billed amount |
| Expected Margin | Overall contract | (Contract value - Estimated costs) / Contract valueEstimated costs = The sum of all estimated costs on all projects mapped to the contract.|
| Contract Value | Project-based lines | The value of the contract line. |
| Billed amount | Project-based lines | For fixed price contract line: The sum of the amounts on all billed sales milestone actuals against this contract line on various invoices created for this contract. For time and material contract line: The sum of the amounts on all chargeable billed sales actuals against this contract line on various invoices created for this contract. |
| Cost Incurred | Project-based lines | The sum of all cost actuals logged on all projects mapped to the contract line. |
| Gross Margin | Project-based lines | (Billed amount - Cost incurred till date) / Billed amount |
| Expected Margin | Project-based lines | (Contract line amount in base currency - Estimated costs for the contract line in base currency) / Contract line amount in base currency |
| Cost Incurred | Detail of a project-based line | Time: The sum of the amount on time cost actuals logged for this role on the project mapped to the contract line. Expenses: The sum of the amount on all expense cost actuals logged for this category on the project mapped to the contract line. |
| Logged Quantity | Detail of a project-based line | Time: The quantity on total time cost actuals for a role on the project that is mapped to this contract line. Expenses: All quantities for this expense category on the expense cost actuals on the project are mapped to this contract line. |
| Billed Amount | Detail of a project-based line | For a fixed price contract line, this field is left blank on the detail level and is only shown at the contract line level. For a time and material contract line, calculations are completed at the details level. The details show the sum of the amount on all the billed revenue lines against this contract line that are chargeable. |
| Billed Quantity | Detail of a project-based line | For a fixed price contract line, this field is left blank on the detail level and is only shown at the contract line level. For a time and material contract line, calculations are completed at the details level for time and expenses. Time: The sum of the hours on all the billed revenue lines for this role against this contract line that are chargeable. Expenses: All quantities for this expense category on the expense cost actuals on the project are mapped to this contract line. |
| Contract Value | Product-based lines | The contract line value of this product-based contract line. |
| Billed Amount | Product-based lines | The sum of the amounts on all invoice lines against this product-based contract line on various invoices that are created for this contract. |
| Cost Incurred | Product-based lines | The sum of all cost actuals logged for the product-based contract line. |
| Gross Margin | Project-based lines | Billed amount - Cost incurred till date / Billed amount |
| Expected Margin | Product-based lines | (Contract line value - Estimated costs for the contract line) / Contract line value |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
