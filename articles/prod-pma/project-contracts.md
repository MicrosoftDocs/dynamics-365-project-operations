---
title: Project contracts
description: Learn how to create and manage project contracts in Dynamics 365 Finance, including invoicing methods, funding sources, and billing rules for various project types.
author: ryansandness
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: johnmichalak
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: ryansandness
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
---

# Project contracts

[!include [banner](../includes/banner.md)]

This article provides examples of the project contracts that you can create for various types of projects and funding sources. It also explains how you can manage contracts and invoice project customers.

The type of project that you create for a project contract determines the method used to invoice project customers. You can change a project contract and the related project, but you can't change the project type.

By using a project contract, you can invoice one or more projects at the same time. The project contract also helps guarantee a consistent invoicing procedure for every subproject in a project structure.

Every project that you invoice must be associated with a project contract. The settings for a project contract apply to all projects and subprojects that are associated with that project contract.

A project contract can specify one or more sources of funding. Therefore, you can split the billing among multiple funders, set up funding limits so that funding sources aren't billed more than a specified amount, and configure funding rules for charging expenditures.

## Funding for project contracts

Some project contracts specify that multiple parties share the responsibility for funding the project costs. Here are some examples:

- A large customer that has multiple divisions requests that funding of a project is split by division.
- Your company shares the costs of a large project with an external organization.
- A  road project is cofunded by two municipalities.
- A bridge project is funded by a government grant and a private corporation.

In Dynamics 365 Finance, you can split the billing for a single transaction or an entire project among multiple customers, grants, or organizations.

In projects that have multiple funders, all parties that contribute to the funding of an advanced funding project are called funding sources. After a customer, organization, or grant is defined as a funding source, you can assign it to one or more funding rules. Funding rules contain the criteria that determine how charges are allocated to the various funding sources for a project.

Because stocked items, such as those that appear on purchase requisitions and purchase orders, can't be split, the cost amount can't be split among multiple funding sources at the time of distribution. Therefore, the funding source value remains 0 (zero) until the inventory issue is posted. When you post the inventory issue, the cost amount is distributed according to the account distribution rules for the project.

Here are some steps that you can take to make it easier to split the billing among multiple funding sources:

- Specify that all transactions that you enter for a project use the same sales currency as the project contract.
- Set up funding limits, so that a funding source isn't invoiced more than a specified amount toward a project. For more information about funding limits, see [Project funding limits](./project-funding-limits.md).
- Configure funding rules and funding limits for each worker, item, category, category group, and transaction type (or for all transaction types).
- Select optional start and end dates to define the period when each funding rule is valid.
- Specify the percentage that each funding source is responsible for.
- Specify which funding source is responsible for rounding differences that are caused by funding allocation calculations.
- Set up rules that determine how project costs are invoiced to external customers and charged to internal organizations.
- Record transactions in an on-hold funding account until additional funding can be obtained, or until you decide to bear the costs internally.

To determine which tax group to associate with a transaction, the project is searched for a tax group assignment. If no tax group assignment exists at the project level, the project contract is searched.

### Example: Multiple funding sources (simple)

The following table provides scenarios for managing funding allocation among multiple funding sources. These scenarios are based on the following assumptions:

- Priority settings affect the allocation of funds before other funding rule criteria.
- No date range is specified to define the period when the funding rule is valid.

| Scenario | Funding source | Allocation percentage | Allocation priority |
|---|---|---|---|
| You want to allocate costs to one funding source until its funds are exhausted, allocate costs to a second funding source until its funds are exhausted, and finally allocate the remaining costs to a third funding source. | Funding source 1 <br> Funding source 2 <br> Funding source 3 | 100% <br> 100% <br> 100% | 1 <br> 2 <br> 3 |
| You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source. When either of those funding sources is exhausted, pay the remaining costs from a third funding source. | Funding source 1 <br> Funding source 2 <br> Funding source 3 | 75% <br> 25% <br> 100% | 1 <br> 1 <br> 2 |
| You want to allocate 75 percent of costs to one funding source and 25 percent to a second funding source. When either of those funding sources is exhausted, split the remaining costs between a third funding source and a fourth funding source. | Funding source 1 <br> Funding source 2 <br> Funding source 3 <br> Funding source 4 | 75% <br> 25% <br> 50% <br> 50% | 1 <br> 1 <br> 2 <br> 2 |
| You want to allocate the first 25 percent of costs to one funding source and the rest to a second funding source. | Funding source 1 <br> Funding source 2 | 25% <br> 100% | 1 <br> 2 |

### Example: Multiple funding sources (complex)

You have three funding sources that you want to use in the following order:

1. Use funding source 2 and funding source 3 equally until funding source 2 is exhausted.
1. Continue to use funding source 3 until it's exhausted.
1. Use funding source 1 after funding source 3 is exhausted.

To accomplish this goal, complete the following steps:

- Set up funding limits for funding source 2 and funding source 3, for their respective amounts.
- Create the following funding rules:
  - Rule 1 (Priority 1): Allocate 50 percent of transactions to funding source 2 and 50 percent to funding source 3.
  - Rule 2 (Priority 2): Allocate 100 percent of transactions to funding source 3.
  - Rule 3 (Priority 3): Allocate 100 percent of transactions to funding source 1.

This setup works because transactions are checked against rules and limits to determine whether any of them apply to the transaction. If no specific rules or limits apply to the transaction, the All transactions rule applies. The All transactions rule matches all transactions.

If a rule matches a transaction, the percentage that the rule allocates is applied first. The system checks the matches against any limits that you set up. If the process meets a limit and a funding source's funds are exhausted, the system disregards the funding rule that's associated with the funding limit and checks for the next rule that applies.

In some cases, only part of a transaction can be allocated under a rule. This situation might happen because a limit is reached when the transaction is allocated. In this case, only a certain amount is allocated according to that rule, such as 50 percent to each funding source. This situation occurs in rule 1, which is described earlier in this section. The remainder is allocated according to the next rule in the sequence.

The following table examines this scenario in more detail.

| Focus | Details |
|---|---|
| Funding rules | Rule 1 (Priority 1): All transactions. Allocate funding source 2 at 50% and funding source 3 at 50%. <br> Rule 2 (Priority 2): All transactions. Allocate funding source 3 at 100%. <br> Rule 3 (Priority 2): All transactions. Allocate funding source 1 at 100%. |
| Funding limits | Funding source 1 limit = 10,000.00 <br> Funding source 2 limit = 500.00 <br> Funding source 3 limit = 750.00 |
| Transaction 1 | **Transaction amount:** 100.00 **Funding:** The transaction is paid according to rule 1 only, because the transaction is fully paid after rule 1 is applied. The transaction is funded equally between funding source 2 and funding source 3. <br> Funding source 2: 50.00 <br> Funding source 3: 50.00 |
| Transaction 2 | **Transaction amount:** 5,000.00 **Funding:** The transaction is paid according to all three rules. **Rule 1** <br> Funding source 2: 450.00 <br> Funding source 3: 450.00 <br> **Rule 2** <br> Funding source 3: 250.00 (= 750.00 – 50.00 – 450.00) <br> **Rule 3** <br> Funding source 1: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00) |
| Total funds that are distributed for each funding source | Funding source 1: 3,850.00 <br> Funding source 2: 500.00 <br> Funding source 3: 750.00 |

## Billing rules

When you negotiate a project contract with a customer, define how and when you can invoice the customer for work on a project. After you set up the project contract and the project, set up billing rules for the project. Billing rules are based on the project terms that you specify in the project contract. The billing rules that you can create depend on the terms of the project contract and the project type, such as Time and material or Fixed-price, that you associate with the billing rule. You can create more than one billing rule for a project contract. You can also assign a billing rule to multiple projects that are associated with the same project contract and have similar billing terms.

Set up the following types of billing rules:

- **Unit of delivery** – Invoice a customer when you complete a unit of delivery. You define the units of delivery in the contract.
- **Progress** – Invoice a customer when you complete a specified percentage of the project. You can set up a billing rule to automatically calculate the percentage of work completed, or you can manually calculate the percentage of work completed and the amount to invoice the customer.
- **Milestone** – Invoice a customer for the full amount of a project milestone when the milestone is reached.
- **Fee** – Invoice a customer for your services plus a management fee, which is typically a percentage of the cost of services.
- **Time and material** – Invoice a customer for the value of time and materials that are used on a project.

For all types of billing rules, specify a retention percentage that is deducted from customer invoices until a project reaches an agreed-upon stage. The project contract specifies the payment retention percentage. Calculate the amount based on, and subtract it from, the total value of the lines in a customer invoice.

For **Time and material** and **Progress** billing rules, assign chargeable categories. Chargeable categories indicate the transactions that should be included in customer invoices.

When you're ready to invoice the customer, the amount to invoice for the project is calculated based on the billing rules, and a project invoice proposal is generated.

The following sections provide examples that show how to set up and manage billing rules for a project.

### Example: Create a billing rule that is based on the number of units delivered

Your organization enters into an agreement to provide a total of five training sessions to a customer’s employees at a cost of $10,000 per training session. You invoice the customer after each training session.

When you set up the billing rules for the contract, use the following values:

- The unit of delivery is one training session.
- The unit price is $10,000 per training session.
- The total number of units is five training sessions.

When you complete one training session, you can create an invoice for $10,000, for the first unit that you delivered, and send the invoice to the customer.

### Example: Create a billing rule that is based on a specified percentage of project completion (manual calculation)

Your organization, a software consulting firm, enters into an agreement with a customer to develop part of a product that the customer is developing. Your organization agrees to deliver the software code over a period of six months. The customer agrees to pay your organization a total of $100,000 for the work. You create a billing rule to invoice the customer based on the percentage of work that is completed on the project, as specified in the contract.

- At the end of the first month, you meet with the customer to determine the percentage of work completed. After you and the customer review the project, you decide that the project is 15 percent completed.
- You create an invoice for $15,000 (15 percent of $100,000) and send it to the customer.

### Example: Create a billing rule that is based on a specified percentage of project completion (automatic calculation)

Your organization, a software development firm, agrees to develop a payroll accounting package for a customer for $30,000. The customer agrees to pay your organization based on the percentage of work completed. You estimate that the project costs are $20,000. The project contract specifies the categories of work that you use in the billing process. You set up billing rules that automatically calculate the invoice amounts for the percentage of work that is completed for each category. You set up a budget for each category:

- **Development** – Cost of $15,000 and revenue of $20,000
- **Installation** – Cost of $5,000 and revenue of $10,000

When you create a customer invoice for the first time, the invoice amount is automatically calculated based on the following information:

- After a month, the worker on the project submits a timesheet for the project. The cost of the worker’s hours is $5,000 for development and $1,000 for installation. The development work is 33 percent completed (5,000 actual cost, 15,000 budget cost), and the installation work is 20 percent completed (1,000 actual cost, 5,000 budget cost).
- The invoice amount of $8,667 is automatically calculated (33 percent of 20,000 + 20 percent of 10,000).
- You create an invoice for $8,667 and send it to the customer.

### Example: Create a billing rule that is based on agreed-upon milestones

Your organization, a management consulting firm, agrees to conduct market research for a consumer product that the customer plans to sell. The customer agrees to use your services for a period of three months, starting in March, and agrees to pay your organization $50,000. The project has three milestones:

- Milestone 1: Collect consumer data – March 31
- Milestone 2: Analyze consumer data – April 30
- Milestone 3: Present a product viability proposal – May 31

The customer agrees to pay your organization $10,000 for the first milestone, $20,000 for the second milestone, and $20,000 for the third milestone.

When you set up the project contract, you agree to bill the customer based on the milestone that you complete. The billing rule setup includes the following steps:

- Define the project milestones.
- Define the amount to invoice the customer when each milestone is completed.

When you complete the first milestone on March 31, you mark the milestone as completed, and then create an invoice for $10,000 and send it to the customer. You can't create an invoice for a milestone until you mark the milestone as completed.

### Example: Create a billing rule that is based on services plus a management fee

Your organization, a management consulting firm, agrees to conduct market research to evaluate the viability of a product that the customer, a retail company, is developing. The terms of the agreement specify that you provide the services of your top three management consultants, who conduct the research on a time-and-materials basis. The customer agrees to pay $100 per hour, plus a 10 percent management fee for the consulting hours that you charge to the project.

When you set up the project contract, create a billing rule to add a 10 percent management fee to the consulting hours that you charge to the project.

When you create an invoice for the customer, the customer is billed a 10 percent management fee plus the cost of the consulting hours. For example, if the three consultants worked a total of 200 hours on the project, an invoice for $22,000 is created based on the following calculation:

- 200 hours at $100 per hour = $20,000
- 10 percent management fee = $2,000
- Total invoice amount = $22,000

If fees are taxable to a customer, and you select a sales tax group in the project contract, the sales tax group is automatically entered in a billing rule for fees.

### Example: Create a billing rule for the value of time and materials

Your organization, a software consulting firm, agrees to provide five technical consultants to work on a software development project for a customer for the next six months. The customer agrees to pay $150 for each consulting hour, plus the cost of office supplies. Your organization sends an invoice to the customer at the end of each month.

When you set up the project contract, you agree to bill the customer each month for time and materials on the project. You create a billing rule that includes the following information:

- The contract period is six months.
- Consulting time is calculated at a rate of $150 per hour.
- Office supplies are invoiced at cost, and the total cost for the project must not exceed $10,000.
- You create a customer invoice at the end of each calendar month during the project.

During the first month, a total of 800 hours are recorded by the consultants on the project. The cost of office supplies that you charge to the project is $2,000. Therefore, at the end of the month, you create an invoice for $122,000, which is calculated as 800 hours at $150 per hour, plus $2,000 for office supplies.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
