---
# required metadata

title: Configure intercompany invoicing
description: This article provides information and examples on configuring intercompany invoicing for projects.
author:  sigitac
manager: tfehr
ms.date: 11/05/2020 
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: sigitac

---

Follow steps outlined below to configure intercompany invoicing:

1. **Configure intercompany accounting between legal entities.** Each pair of borrowing and lending legal entities must be configured in General Ledger [Intercompany accounting](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/intercompany-accounting-setup) form.

Example: Contoso Robotics USA (USPM) is borrowing legal entity and Contoso Robotics UK (GBPM) is lending legal entity. In Finance, navigate to General Ledger \&gt; Posting setup \&gt; Intercompany accounting and create the following record:

  - Originating company: GBPM
  - Destination company: USPM

2. **Configure trading relationship between legal entities.** Customer record representing borrowing legal entity must be created in lending legal entity. Vendor record representing lending legal entity must be created in borrowing legal entity.

Example: In Finance, select GBPM legal entity and create a customer representing USPM legal entity:

1. Navigate to Accounts receivable \&gt; Customer \&gt; All customers and create new.
2. Expand Name field and filter records by Type column Legal entities. Then find record Contoso Robotics USA (USPM) and select it
3. In the next form click Use match button
4. Select customer group and save.

Next, in Finance select USPM legal entity and create a vendor record representing GBPM legal entity:

1. Navigate to Accounts payable \&gt; Vendors \&gt; All vendors and create new.
2. Expand Name field and filter records by Type column Legal entities. Then find record Contoso Robotics UK (GBPM) and select it.
3. In the next form click Use match button
4. Select vendor group and save.
5. Navigate to General \&gt; Set up \&gt; Intercompany menu item in the saved vendor record
6. In Trading relationship tab set Active flag to Yes
7. Select Vendor company GBPM and set My account record to the customer created in step d

3. **Configure Intercompany settings in Project Management and Accounting Parameters.** Click Project management and accounting \&gt; Setup \&gt; Project management accounting parameters, and then click the Intercompany tab.

- In the borrowing legal entity, select the procurement category that should be used to match the vendor invoices, which are automatically generated.
- In the lending legal entity, for each borrowing entity, select a default project category for each transaction type. Project categories are used for tax configuration when the invoiced category in intercompany transactions exists only in the borrowing legal entity. You can choose to accrue revenue for intercompany transactions. This accrual is done when the transactions are posted through Project Operations Integration journal in lending legal entity, and it&#39;s then reversed when the intercompany invoice is posted.

Example: In Finance select borrowing legal entity USPM. Navigate to Project management and accounting \&gt; Setup \&gt; Project management accounting parameters, and then click the Intercompany tab. In Default category field select Intercompany resources.

Next, select lending legal entity GBPM. In Project Management parameters Intercompany tab select … under group When lending resources and click New. In the grid select:

  - Borrowing legal entity – GBPM
  - Accrue revenue – Yes
  - Default timesheet category – Default – Hour
  - Default expense category – Default – expense

4. **Set intercompany cost and revenue accounts in Ledger posting setup**. Intercompany revenue account is credited when posting Intercompany customer invoice in lending legal entity. Intercompany cost account is debited when posting matching Pending vendor invoice in borrowing legal entity. These accounts are set up in corresponding legal entities by navigating to Project Management and Accounting \&gt; Setup \&gt; Posting \&gt; Ledger posting setup.

Example: In Finance select borrowing legal entity USPM. Navigate to Project Management and Accounting \&gt; Setup \&gt; Posting \&gt; Ledger posting setup. In the Cost accounts tab select Ledger account type Intercompany cost and create a new record:

- Lending legal entity – GBPM
- Main account – select main account for intercompany cost.

Next, select lending legal entity GBPM. Navigate to Project Management and Accounting \&gt; Setup \&gt; Posting \&gt; Ledger posting setup. In the Revenue accounts tab select Ledger account type Intercompany revenue and create a new record:

- Borrowing legal entity – USPM
- Main account – select main account for intercompany revenue.

5. **Set up transfer pricing for labor**. Intercompany transfer pricing is configured in Project Operations on CDS. Configure [labor cost rates](https://docs.microsoft.com/en-us/dynamics365/project-operations/pricing-costing/set-up-labor-cost-rate#transfer-pricing-and-costs-for-resources-outside-of-your-division-or-legal-entity) and [labor bill rates](https://docs.microsoft.com/en-us/dynamics365/project-operations/pricing-costing/set-up-labor-bill-rate#transfer-pricing-or-set-up-bill-rates-for-resources-from-other-organizational-units-or-divisions) for intercompany invoicing. Note that transfer pricing is not supported for intercompany expense transactions, and inter-org unit sale price will always be set to the same value as resourcing unit cost price.

Example: Contoso Robotics UK Developer resource cost is 88 GBP per hour. Contoso Robotics UK will bill Contoso Robotics USA 120 USD per each hour this resource worked on US projects. Contoso Robotics USA will bill customer Adventure works 200 USD for work performed by Contoso Robotics UK resource.

1. In Project Operations on CDS create cost price list Contoso Robotics UK:
  1. Navigate to Sales \&gt; Price lists and create a cost price list called Contoso Robotics UK cost rates. In the cost price list create the following record:
    1. Role – Developer
    2. Cost – 88 GBP
  2. Navigate to Settings \&gt; Organizational units and attach this cost price list to Contoso Robotics UK organizational unit
2. In Project Operations on CDS create a cost price list Contoso Robotics USA:
  1. Navigate to Sales \&gt; Price lists and create a cost price list called Contoso Robotics USA cost rates. In the cost price list create the following record:
    1. Role – Developer
    2. Resourcing company – Contoso Robotics UK
    3. Cost – 120 USD
  2. Navigate to Settings \&gt; Organizational units and attach this cost price list to Contoso Robotics USA organizational unit.
3. In Project Operations on CDS create a sales price list for Adventure works project contract:
  1. Navigate to Sales \&gt; Price lists and create a sales price list called Adventure works bill rates. In the sales price list create the following record:
    1. Role – Developer
    2. Resourcing company – Contoso Robotics UK
    3. Bill rate – 200 USD
  2. Navigate to Sales \&gt; Project contracts and attach this bill price list to Adventure works project price list of the project contract.
