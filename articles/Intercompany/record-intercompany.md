---
# required metadata

title: Create intercompany transactions
description: This article provides information and examples on creating intercompany transactions.
author:  sigitac
manager: tfehr
ms.date: 11/05/2020 
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: sigitac

---

Intercompany transactions are time and expense transactions where project contract belongs to one company or organizational unit and resource belongs to a different company or organizational unit.

When intercompany transaction gets approved, system creates the following actual transactions:

| **Transaction Type** | **Pricelist applied** | **Transaction currency** |
| --- | --- | --- |
| Cost | Contracting unit cost price list | Currency on the price line |
| Unbilled sales(created only for actuals associated with contract line using time and material billing type) | Contract project sales price list | Contract currency |
| Resourcing unit cost | Resourcing unit cost price list | Currency on the price line |
| Inter-org unit sales | Contracting unit cost price list | Currency on the price line |

Cost, resourcing unit cost and inter-org unit sales transaction pricing and currency is driven by _ **organizational unit.** _ Keep this in consideration when deciding the structure of companies and organizational units in your implementation.

When creating opportunities, quotes, project contracts and projects, system will check contracting unit currency matches contracting company accounting currency and will prevent creating records where these are not the same. Organizational unit currency is defined in Project Operations on CDS \&gt; Settings \&gt; Organizational units. Company&#39;s accounting currency is defined in Dynamics 365 Finance \&gt; General ledger \&gt; Ledger setup \&gt; Ledger and is synced to Project Operations on CDS using Ledgers Dual Write map.

System will create Resourcing unit cost and Inter-org unit sales actuals both when resourcing unit differs from contracting unit or/and resourcing company differs from contracting company, however only transactions where resourcing company differs from contracting company will be transferred to Dynamics 365 Finance for further accounting.

Accounting for Project Actuals is recorded in Finance, Project Operations integration journal. System creates the following journal lines:

| **Transaction Type** | **Legal entity** | **Creates project transaction on posting** | **Financial dimensions default from** | **Billing sales tax group, billing item sales tax group defaults from** |
| --- | --- | --- | --- | --- |
| Cost | Does not get added to integration journal | N\A | N\A | N\A |
| Unbilled sales | Borrowing legal entity integration journal | Yes | Project | Billing sales tax group - based on **contract customer** , billing item sales tax group - from current Legal entity project category on the journal line. |
| Resourcing Unit cost | Lending Legal entity integration journal | No | Intercompany customer | Billing sales tax group - based on **intercompany customer** , billing item sales tax group - from current Legal entity project category on the journal line. |
| Inter-Org Sales | Lending Legal entity integration journal | No | Intercompany customer | Billing sales tax group - based on **intercompany customer** , Billing item sales tax group - from current Legal Entity project category on the journal line. |

Example:

Molly Clark, developer employed in GBPM logs 10 hours of work against USPM Adventure Works project which gets approved by project manager. Developer cost in GBPM is 88 GBP per hour. GBPM will bill USPM 120 USD per developer hour. USPM will bill customer Adventure works 200 USD for work performed by GBPM resource (See Configure Intercompany Invoicing topic for price setup example).

1. In Project Operations on CDS Resources select Molly Clark resource and navigate to Scheduling tab. Set field Company value to GBPM.
2. Create Adventure Works customer in Project Operations on CDS (customer can also be created in Finance):
  1. Sales \&gt; Customers create a new record:
    1. Set company to USPM.
    2. Set Relationship type to Customer.
    3. Select Customer group 10 – Domestic.
    4. Set currency to USD and save the record.
3. Create Adventure works project contract and project:
  1. Sales \&gt; Project Contracts create a new record:
    1. Set Owning company to USPM and contracting unit as Contoso Robotics US.
    2. Set Customer to Adventure Works.
    3. Select product price list and save the record.
    4. In Contract lines tab create a new contract line. Set any name, select Billing Method Time and Materials. Create a new project and associate it with this contract line.
4. As Molly Clark resource, navigate to Projects \&gt; Time entries and create a time entry for Adventure works project.
5. As Project Manager approve hour transaction logged by Molly Clark in Projects \&gt; Approvals.
6. Navigate to Adventure works project and open Related \&gt; Actuals. System has created the following actual transactions:

| **Transaction Type** | **Price** | **Transaction currency** | **Amount** |
| --- | --- | --- | --- |
| Cost | 120 | USD | 1200 |
| Unbilled sales
 | 200 | USD | 2000 |
| Resourcing unit cost | 88 | GBP | 880 |
| Inter-org unit sales | 120 | USD | 1200 |

1. As USPM accountant, navigate to Project Operations Finance and open USPM company. Run periodic process Import from staging (Projects Management and Accounting \&gt; Periodic \&gt; Project Operations on Customer Engagement\&gt; Import from staging). This periodic process will fill in Project Operations Integration journal.
2. Navigate to Project Operations Integration Journal (Projects Management and Accounting \&gt; Journals \&gt; Project Operations integration journal) and review the lines. System creates the following line:

| **Transaction Type** | **Price** | **Transaction currency** | **Amount** |
| --- | --- | --- | --- |
| Unbilled sales | 200 | USD | 2000 |

If system is set up to accrue revenue for this project, system also posts the following:

Debit: Project – WIP sales value 200 USD

Credit: Project – Accrued Revenue 200 USD

This unbilled sale is now ready for invoicing and invoice for Adventure works customer can be financially posted when needed.

1. As GBPM accountant, navigate to Project Operations Finance and open GBPM company. Run periodic process Import from staging (Projects Management and Accounting \&gt; Periodic \&gt; Project Operations on Customer Engagement\&gt; Import from staging). This periodic process will fill in Project Operations Integration journal.
2. Navigate to Project Operations Integration Journal (Projects Management and Accounting \&gt; Journals \&gt; Project Operations integration journal) and review the lines. System creates the following lines:

| **Transaction Type** | **Price** | **Transaction currency** | **Amount** |
| --- | --- | --- | --- |
| Resourcing unit cost | 88 | GBP | 880 |
| Inter-org unit sales | 120 | USD | 1200 |

Posting these records result in the following voucher transactions:

Debit: Project cost 88 GBP

Credit: Payroll allocation 88 GBP

If system is set up to accrue intercompany revenue, system also posts the following:

Debit: Project – WIP sales value 120 USD

Credit: Project – Accrued Revenue 120 USD

System is now ready to create intercompany customer invoice.
