---
# required metadata

title: Create intercompany transactions
description: This article provides information about how to create intercompany transactions.
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create intercompany transactions

_**Applies To:** Project Operations Integrated with ERP_

Intercompany transactions are time and expense transactions from a project contract that belong to one company or organizational unit, while the resources on the project contract are part of a different company or organizational unit.

When an intercompany transaction is approved, the following actual transactions are created

| **Transaction type** | **Price list applied** | **Transaction currency** |
| --- | --- | --- |
| Cost | Contracting unit cost price list | Currency on the price line |
| Unbilled sales. These are created only for actuals that are associated with a contract line with the billing type, time, and material. | Contract project sales price list | Contract currency |
| Resourcing unit cost | Resourcing unit cost price list | Currency on the price line |
| Inter-organizational unit sales | Contracting unit cost price list | Currency on the price line |

Cost, resourcing unit cost, and inter-organizational unit sales transaction pricing and currency is driven by **organizational unit**. This is important to remember when deciding how to structure companies and organizational units in your implementation.

When you create opportunity, quote, project contract, and project records, the system verifies that the contracting unit's currency matches the contracting company's accounting currency. When they aren't the same, these records can't be created. The organizational unit currency is defined in Dynamics 365 Project Operations by going to **Dataverse** > **Settings** > **Organizational units**. A company's accounting currency is defined in Dynamics 365 Finance by going to **General ledger** > **Ledger setup** > **Ledger**. The currency is synchronized to your Dataverse environment using Ledgers Dual Write map.

The system creates resourcing unit cost and inter-organizational unit sales actuals  in the following situations:

  - When the resourcing unit differs from the contracting unit
  - When the resourcing company differs from contracting company

However, only transactions that have a different resourcing company from the contracting company will be transferred to the Dynamics 365 Finance environment for additional accounting.

Accounting for project actuals is recorded in the Project Operations integration journal in Finance. The system creates the following journal lines.

| **Transaction type** | **Legal entity** | **Creates project transaction on posting** | **Financial dimensions default from** | **Default billing sales tax group and billing item sales tax group** |
| --- | --- | --- | --- | --- |
| Cost | Doesn't get added to the integration journal | N\A | N\A | N\A |
| Unbilled sales | The borrowing legal entity integration journal | Yes | Project | **Billing sales tax group**: Based on the **contract customer** <br/> **Billing item sales tax group**: From the current legal entity project category on the journal line |
| Resourcing unit cost | Lending legal entity integration journal | No | Intercompany customer | **Billing sales tax group**: Based on the **intercompany customer** <br/> **Billing item sales tax group**: From the current legal entity project category on the journal line |
| Inter-organizational sales | Lending legal entity integration journal | No | Intercompany customer | **Billing sales tax group**: Based on the **intercompany customer** <br/> **Billing item sales tax group**: From the current legal entity project category on the journal line |

### Example: Intercompany transactions

Molly Clark, developer employed in GBPM records 10 hours of work against a USPM Adventure Works project, which is approved by the project manager. Developer cost in GBPM is 88 GBP per hour. GBPM will bill USPM 120 USD per developer hour. USPM will bill the customer Adventure Works, 200 USD for work done by the GBPM resource. For more information, see [Configure intercompany invoicing](configure-intercompany-invoicing.md).

1. In Project Operations, go to **Resources**, and select **Molly Clark** from the list. On the **Scheduling** tab, in the **Company** field, select **GBPM**.
2. Go to **Sales** > **Customers**, and select **New** to create a new customer record for Adventure Works.
    1. Set the company to **USPM**.
    2. Set **Relationship type** to **Customer**.
    3. Select **Customer group 10 – Domestic**.
    4. Set currency to **USD**.
    5. Save the record.
3. Go to **Sales** > **Project Contracts** and create a new project contract for Adventure Works.
    1. Set the owning company to **USPM** and the contracting unit to **Contoso Robotics US**.
    2. Select Adventure Works as the customer.
    3. Select a product price list and save the record.
    4. On the **Contract Lines** tab, create a new contract line. Set any name, and select **Time and Materials** as the billing method.
    5. Create a new project and associate it with this contract line.
4. Sign in as the resource, **Molly Clark**. Go to **Projects** > **Time entries**, and create a time entry for the Adventure Works project.
5. Sign in as the Project manager. Go to **Projects** > **Approvals**, and approve the time entry transaction logged by Molly Clark.
6. Navigate to the Adventure Works project and select **Related** > **Actuals**. The following actuals transactions are created.

| **Transaction type** | **Price** | **Transaction currency** | **Amount** |
| --- | --- | --- | --- |
| Cost | 120 | USD | 1200 |
| Unbilled sales | 200 | USD | 2000 |
| Resourcing unit cost | 88 | GBP | 880 |
| Inter-org unit sales | 120 | USD | 1200 |

7. Sign in as a USPM accountant. Open the Finance instance of Project Operations, and select the company **USPM**. 
8. Go to **Project management and accounting** > **Periodic** > **Project Operations on Customer Engagement** > **Import from staging** and select to run the periodic process. This periodic process will fill in Project Operations Integration journal.
9. Go to **Project management and accounting** > **Journals** > **Project Operations integration journal** and review the journal lines. The system creates the following line.

    | **Transaction type** | **Price** | **Transaction currency** | **Amount** |
    | --- | --- | --- | --- |
    | Unbilled sales | 200 | USD | 2000 |

    If the system is set up to accrue revenue for this project, the following is posted:

    - Debit: Project – WIP sales value 200 USD
    - Credit: Project – Accrued Revenue 200 USD

    This unbilled sale is now ready for invoicing. The invoice for the customer Adventure Works can be financially posted when needed.

10. Sign in as the **GBPM** accountant. Open the Finance instance of Project Operations, and open the company, **GBPM**. 
11. Go to **Project management and accounting** > **Periodic** > **Project Operations integration** > **Import from staging table** and run the periodic process to  fill in Project Operations Integration journal.
12. Go to **Project management and accounting** > **Journals** > **Project Operations integration journal** and review the lines. The system creates the following lines.

    | **Transaction type** | **Price** | **Transaction currency** | **Amount** |
    | --- | --- | --- | --- |
    | Resourcing unit cost | 88 | GBP | 880 |
    | Inter-org unit sales | 120 | USD | 1200 |

    Posting these records result in the following voucher transactions:

    - Debit: Project cost 88 GBP
    - Credit: Payroll allocation 88 GBP

    If system is set up to accrue intercompany revenue, the following is posted:

    - Debit: Project – WIP sales value 120 USD
    - Credit: Project – Accrued Revenue 120 USD

    The system is now ready to create an intercompany customer invoice.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
