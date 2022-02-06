---
# required metadata

title: Create and confirm Entry journals
description: This topic provides information about how to create and confirm a entry journals in Project Operations.
author: rumant
ms.date: 09/18/2020
ms.topic: article
ms.prod: 
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: tonyafehr
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.author: rumant
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Create and confirm Entry Journals

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_


Use entry journals in Project Operations to record actuals directly into Project Operations. Using entry journals is designed to help bypass entering Time, Expenses and Material usage logs in Project Operations and record actuals directly. Please Note:

A single **entry** journal will allow you to create multiple journal lines. When the journal is confirmed, **Entry** journal line will record the actual for

- cost or revenue depending on the transaction type selected
- in the selected class of transaction from the available classes of material, fee, time, expense, milestone, or retainer
- n the project and/or a task selected on that journal line.

Use the following process to create an Entry journal in Project Operations:

1. Navigate to **Sales**->**Transactions** -> **Journals**
2. The Entry journals list page opens. Click **+New** from the command bar to create a new journal.
3. The new journal page opens.
4. On the New journal page, give a **Description** for the Journal. Make sure that the Journal Type is set to **Entry** and Click on **Save**
5. The new entry journal is saved. Once it is saved, you should see the tab for **Journal lines** on the Journal page.
6. Click on this tab. The journal lines grid will be shown. From this grid tool bar, click on **New** to create a new Entry journal line.
7. A Quick create page for creating a new Entry journal line will open.
8. The following table gives a description of fields on the Entry journal line page and how these field values should be set for creating journal lines.

| **Field** | **Description** | **Functional Impact** |
| --- | --- | --- |
| Transaction Class | Classifies this journal line into one of the 6 different transaction classes: Time, Expense, Material, Retainer, Milestone and Tax | Of the available options, Tax transaction class has been deprecated in Project Operations. Creating a Tax transaction class will not be processed by invoicing or in cost or revenue calculations.Milestone is a revenue-only transaction class. Retainer represents an advance received from a customer and should always be created as a pair of Billed Sales and Unbilled sales journal lines |
| Transaction Type | Of the available options Cost, Interorg Sales and Resourcing unit cost are transaction types that should be used for recording cost. Unbilled Sales and Billed Sales should be used for recording revenue. | Retainer transaction class only works with Unbilled sales and Billed Sales transaction types. Milestone transaction class only works with Billed Sales transaction type. Interorg Sales and Resourcing unit cost are only applicable for Time transaction class |
| Select Product | When transaction class selected is Material, this field will allow the user to specify whether the material transaction they are creating the journal line for is an Existing product or a Write in Product | If write – in product is the value selected, then the user will have the ability to type a name of the |
| Product | A reference to the product from the catalog | |
| Description | Description of the journal line to help with easy identification | For unbilled sales journal lines, this will be used as the description when creating the Invoice line details |
| External description | Description of the journal line to help that can be used for sharing with external stakeholders | For unbilled sales journal lines, this will be used as the external description when creating the Invoice line details and may be used to display on invoice sent to the customer |
| Billing Type | Indicates whether this journal line would be counted as chargeable, complimentary, or non-chargeable component on the project | In a typical flow, billing type would be derived based on what is agreed on by the contractual terms setup on the contract. However, when recording a journal line, you can input a value into this field |
| Document date | Use a date on which the transaction occurred | |
| Start Date | Use the date on which the transaction occurred | Will be used for comparing with date of invoice creation for unbilled sales type of transactions. This will help to decide whether this transaction is future-dated or past-dated and only past-dated transactions will be added to the invoice. |
| End Date | Use the date on which the transaction occurred | |
| Accounting Date | Use the date on which the accounting impact will be recorded.| |
| Contract line customer | Will be defaulted on save of the journal line to the customer on the contract line if the contract line has only one customer.If the contract line has multiple customers, make sure to pick the correct contract line customer. | If the system is unable to determine the contract line customer on the journal line and if it is blank on the unbilled sales type of actual that is created from the journal line, the actual will not be invoiced. |
| Project | Pick the project on which you want to record the actual. | Based on the project, transaction class and the task selected, the system will try to determine the contract, contract line and contract line customer. |
| Task | Pick the project on which you want to record the actual. | If you have associated tasks to contract lines during contract setup, along with project and transaction class, the task selected will also be used by the system to determine the contract, contract line and contract line customer. |
| Transaction Category | Pick the category on which you want to record the actual. | For Expenses, the transaction category selected will determine which price will default on the journal line on save |
| Role | Relevant for Time journal lines. Pick the role played by the resource who spent time on the project and / or task | For Time journal lines, the Role selected in coordination with Resourcing unit will determine which price will default on the journal line on save. This is when you use out-of-the-box configuration for resource cost and bill rate defaulting. If you have a custom configuration for price defaulting, you should check that configuration to see if Role is being used for price defaulting or not. |
| Subcontract | If the journal line represents subcontracted capacity or subcontracted expenses or materials, select the relevant subcontract | When recording cost journal lines, the subcontract selected will determine the price list used for defaulting the unit cost. |
| Subcontract line | If the journal line represents subcontracted capacity or subcontracted expenses or materials, select the relevant subcontract line. | When recording cost journal lines, the subcontract line selected will ensure that the available capacity calculations on the subcontract line are correctly calculated. |
| Amount Method | Defaults to Multiply Quantity By price. When this method is used, Amount will be calculated as Quantity \* PriceThe other method supported is Fixed Price. When this method is used, Price will default to Amount without using Quantity in the calculation.| |
| Unit Schedule and Unit | Unit schedule and unit together will identify the unit of the quantity | The combination of Unit and Transaction category is used for price defaulting for ExpensesThe combination of Unit, Role and Resourcing Unit is used for price defaulting in default configuration of Project operations for Price defaulting for Time. If you have custom configuration for price defaulting, those will be used in conjunction with Unit.The product and unit combination will used for price defaulting for Materials |
| Quantity | Enter the quantity | |
| Price | Price is defaulted using the relevant values depending on the Transaction Class if left empty during creation. If the user entered a price value during creation of the journal line, then the user entered price will be used | |
| Tax | Enter the tax amount, if any | Depending on the tax amount entered, the Extended amount will be calculated as Amount + Tax. |

## Confirm an Entry journal

Once you have entered all the journal lines on an entry journal, you can confirm the journal. This process will record each of the journal lines as Actuals on the respective projects.

Once a journal is confirmed, you will no longer be able to edit the journal or any of its lines.

## Actuals created by Entry journal confirmation

There are few key differences between actuals created by Entry journal confirmation versus those created during Time, Expense,Material usage log approvals and invoice confirmation in Project Operations:

1. Entry journals do not link the cost actual to the unbilled sales actual using transaction connections. The actuals created on approval of Time, Expense and Material usage log always link the cost and unbilled sales actuals using Transaction connections.
2. Entry journals do not link the cost actual and the unbilled sales actuals to any originating record using transaction origins. The actuals created on approval of Time, Expense and Material usage log always link the cost and unbilled sales actuals to the originating Time entry using Transaction origins.
3. When unbilled sales actuals created by Entry journal confirmation are invoiced, the billed sales actuals created during Invoice confirmation are linked to the unbilled sales actuals similar to the unbilled sales actuals created on approval of Time, Expense and Material usage logs
4. Entry journal lines created for Time entered by inter-organizational resources does not result in the automatic creation of Resourcing Unit cost and Interorg Sales actuals. These would have to be created manually. This is different from Time entries recorded by inter-organizational resources where on time approval, the application automatically creates Cost actuals on the project, Resourcing Unit cost and Interorg Sales actuals on the Employee&#39;s owning division and links these together to using Transaction connections and links them to the originating Time entry using Transaction Origins.
5. When entry journals are confirmed, they create Actuals. But these Actuals cannot be corrected using Correction journals. This is different from actuals created on approval of Time, Expense and Material usage log where the application allows you to correct these actuals using correction journals for any errors if those actuals have not been invoiced. If these are invoiced, you can still correct these actuals if you process a full credit of that actual to the customer.

> [!NOTE]
> Entry journals do not enforce strict defaulting rules. So, use these minimally and exercise caution and care to ensure that you are not creating corrupt financial data in your system. Use Time, Expense, Material usage logs, milestone and retainer setup on Project contracts and Project invoice confirmation process where possible to create actuals instead of entry journals



[!INCLUDE[footer-include](../includes/footer-banner.md)]

