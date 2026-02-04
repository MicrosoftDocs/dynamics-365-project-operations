---
title: Manage project invoice proposals
description: This article provides details about processing customer-facing invoices with Project Operations Integrated with ERP
author: ryansandness
ms.author: ryansandness
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage project invoice proposals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

Your billing department can process project invoice proposals when the following three conditions are met:

- The project manager confirms the proforma invoice in Microsoft Dataverse.
- You post all time and material unbilled sales transactions that the proforma invoice includes by using the Dynamics 365 **Project Operations Integration** journal.
- The **Import from staging table** periodic process completes for both unbilled and billed sales lines.

Use the following steps to complete a project invoice proposal in Dynamics 365 Finance.

1. Review billing information for time and material transactions and post the **Project Operations Integration** journal.
1. Review billing information for fixed price billing milestones.
1. Review and format a project invoice proposal.
1. Post and print project invoices.

## Manage billing information in the Project Operations Integration journal

The project accountant reviews and posts project actuals created in Dataverse in Finance. For more information about working with the Integration journal, see [Integration journal in Project Operations](../project-accounting/project-operations-integration-journal.md).

You add cost actuals and unbilled sales actuals to the Integration journal as separate lines:

- The project actual cost transaction in Dataverse provides the unit cost price and cost amount on the Cost actual default.
- The project actual unbilled sales transaction in Dataverse provides the unit sales price and sales amount on the Unbilled sales transaction defaults.

### Billing sales tax

Sales tax calculation for billing is determined by the combination of the **Billing sales tax group** and **Billing item sales tax group** fields on an unbilled sales record in the **Project Operations Integration** journal line. The system sets these field values by default based on the settings on the **Financials** tab of the **Project management and accounting parameters** page.

- **Sales tax group method** determines the billing sales tax group defaulting logic:
  
  - **Project**: Always defaults the billing sales tax group from the project. You can review or change the default billing sales tax group on a project by selecting **Show default accounting** on the **All Projects** page.
  - **Project contract**: Always defaults the billing sales tax group from the project contract. You can review or change the default sales tax group on a project contract by selecting **Show default accounting** on the **Project contracts** page.
  - **Customer**: Always defaults the billing sales tax group from the customer.
  - **Search**: Searches across all the preceding entities and selects the first value available. Search starts with the **Project** entity, then the **Project contract** entity, and finally the **Customer** entity.

- **Item sales tax group method** determines the billing item sales tax group defaulting logic:
  
  - For time, expense, and fee transaction types, the billing item sales tax group always defaults from the **Project category** entity.
  - For material transaction types, the billing item sales tax group defaults based on the **Item sales tax group method** setting in **Project management and accounting parameters**. The item number defaults the item sales tax group from the **Released product** entity. The category defaults the item sales tax group from the **Project category** entity.

### Financial dimensions in the integration journal

The financial dimensions for unbilled sales records in the **Project Operations Integration** journal default from the **Project** entity. You can review and adjust financial dimensions by selecting **Distribute Amounts**. If you need to change the financial dimensions of the unbilled sales record after the Integration journal is posted but before the Proforma invoice is confirmed, go to **All Projects** > **Manage** > **Posted transactions**, select the transaction, and then select **Process** > **Adjust accounting**.

### Exchange rates

Dataverse uses the unbilled transaction currency as the transaction currency in Finance. Finance converts this currency to the company's accounting currency by using the exchange rates you define.

A project contract might require that a constant (fixed) exchange rate is used for the life of the agreement. In some cases, you might need a fixed rate agreement to meet contractual or regulatory requirements. You apply the fixed exchange rate when you convert any sales amounts in the configured currency into the revenue entries for the company's accounting currency.

#### Overview of the fixed exchange rate feature

Starting with the 10.0.41 release, the **Enable the use of Project fixed exchange rate agreements for Project Operations Integrated with ERP deployments** feature supports this requirement. After you enable this feature, the Action Pane on the **Project contracts** page in the finance and operations architecture includes a button that you can use to set up a fixed rate agreement. You can enter a sales currency, an exchange rate, and an optional reference agreement number to enable a fixed rate agreement.

By default, if you don't configure a fixed rate agreement for a given project contract, the system uses the exchange rate that is configured for the legal entity.

You can use the following documents with fixed rate agreements:

- Journals
- Time entries
- Material usage logs
- Milestones and retainers
- Expenses
- Expense reports
- Vendor invoices
- Estimates such as hours, time, and materials

> [!NOTE]
> If you enable a fixed exchange rate in a project that has existing transactions, existing draft integration journal lines or pending project invoices begin to use the new rate.

##### Example scenario

Contoso is based in the United States and uses the US dollar (USD) as its accounting currency. It's delivering a project for Coho Winery, which is based in the United Kingdom. The British pound (GBP) is used as the contract sales currency. GBP-to-USD exchange rates regularly fluctuate between 1.2 and 1.4. Therefore, the companies agreed to a fixed rate of 1.25 for their business dealings for the life of the contract and project.

In Project Operations, a project contract is established. For this project contract, a fixed rate agreement is configured that uses the GBP currency and an exchange rate of 1.25. Contoso set up a Time and Material project with time and expenses that accrue revenue to generate work in progress (WIP) financial entries.

On the project, tasks are created to plan for the various project stages. Julia Funderburk completes the first task, requirement gathering. This task has an estimated duration of seven hours. You can open the **All projects** page in the finance and operations infrastructure, select the project, and then select **Hour forecasts** on the **Plan** tab of the Action Pane. The page shows the entry for the seven-hour forecast. Select **General ledger preview**, The **Overview** tab shows the estimated costs and a line for 2,187.50 GBP of revenue for the **Project - invoiced revenue** posting type. Select the **General** tab to view the breakdown of sales. This breakdown shows seven hours of effort and the sales price of 250. The total sales amount of 1,750 is calculated by using an exchange rate of 125.

Contoso's revenue in its accounting currency is calculated in the following way:

7 hours &times; 250 GBP price &times; 1.25 exchange rate = 2,187.50 USD

After the project begins work, Julia logs her time for the first four hours of work on the first project invoice. On August 27, she creates a time entry for four hours against the requirement gathering task. After that entry is approved, it's created as an integration journal during the next processing of **import from staging table**. The integration journal shows two lines: one for cost and one for sales. The following table shows what these lines look like.

| Document type | Resource name    | Hours | Cost amount | Sales amount | Sales currency | Price exchange rate |
|---------------|------------------|-------|-------------|--------------|----------------|----------------------|
| Usage         | Julia Funderburk | 4     | 480         | 0            | USD            | 100                  |
| Usage         | Julia Funderburk | 4     | 0           | 1,000        | GBP            | 125                  |

For the cost line, the cost remains in the company currency (USD). Therefore, no exchange rate is applied. For the sales line, the price exchange rate reflects the fixed exchange rate.

Posting of the integration journal results in the following items:

- Posting of the project cost
- Entry to Project – WIP – Sales Value
- Entry to Project Accrued Revenue for the WIP by using the fixed exchange rate

| Account | Name                    | Amount in transaction currency | Amount in accounting currency | Exchange rate | Posting type                 |
|---------|-------------------------|--------------------------------|-------------------------------|---------------|------------------------------|
| 600300  | Payroll allocation      | -480                           | -480                          | 1             | Project - payroll allocation |
| 540100  | Cost of Project - Labor | 480                            | 480                           | 1             | Project - cost               |
| 161300  | WIP - Sales Value       | 1,000                          | 1,250                          | 1.25          | Project - WIP - sales value  |
| 420200  | Accrued revenue         | -1,000                         | -1,250                         | 1.25          | Project - accrued revenue    |

When you generate the invoice proposal, it contains a single line for the four hours at a sales price of 250, for a total sales amount of 1,000 GBP. The customer invoice is in GBP.

When you post the invoice proposal, it creates a customer invoice with the following items:

- Reversal to Project – WIP – Sales Value
- Reversal to Project Accrued Revenue for the WIP by using the fixed exchange rate
- Entry for Invoiced Revenue by using the fixed exchange rate
- Entry for Customer Balance by using the fixed exchange rate

4 hours × 250 GBP price × 1.25 exchange rate = 1,250 GBP

| Account | Name                | Amount in transaction currency | Amount in accounting currency | Exchange rate | Posting type                |
|---------|---------------------|--------------------------------|-------------------------------|---------------|-----------------------------|
| 161300  | WIP - Sales Value   | -1,000                         | -1,250                        | 1.25          | Project - WIP - sales value |
| 420200  | Accrued revenue     | 1,000                          | 1,250                         | 1.25          | Project - accrued revenue   |
| 411100  | Revenue - Labor     | -1,000                         | -1,250                        | 1.25          | Project - invoiced Revenue  |
| 130100  | Accounts Receivable | 1,000                          | 1,250                         | 1.25          | Customer balance            |

## Manage the financial attributes of billing milestones

Project contract lines that use the fixed price billing method are invoiced through [Fixed price milestones](../sales/invoice-schedule-contract-line.md#create-a-fixed-price-invoice-schedule-for-a-contract-line). The project accountant can review billing milestones in Finance by going to **Project management and accounting** > **All projects** > **Manage** > **On-account transactions**.

### Billing sales tax of billing milestones

The **Sales tax group** and **Item sales tax group** values default from the settings when you create a new billing milestone in Dataverse. The system defaults the values to these fields based on settings on the **Financial** tab on the **Project management and accounting parameters** page.

- **Sales tax group method** determines the defaulting logic of the **Billing sales tax group**:

  - **Project** always defaults the billing sales tax group from the project. You can review or change the default sales tax group on a project by selecting **Show default accounting** on the **All Projects** page.
  - **Project contract** always defaults the billing sales tax group from the project contract. You can review or change the default sales tax group on a project contract by selecting **Show default accounting** on the **Project contracts** page.
  - **Customer** always defaults the billing sales tax group from the customer.
  - **Search** searches across all the entities in this list and selects the first value available. Search starts with the **Project** entity, then the **Project contract** entity, and then the **Customer** entity.

- **Fixed price milestone item sales tax group** is used as the default value in the **Item sales tax group** field for the billing milestone. The accountant can review and modify this value on the **On-account transactions** page. The system uses the value from the on-account transaction when creating a project invoice proposal line.

### Financial dimensions of milestones

You set default financial dimensions for the fixed price billing milestone on Project contract lines. Go to **Project contracts** > **Show default accounting**. On the **Contract lines** tab, select **price contract line**, and then set the financial dimension values that you want to use as the default.

The project accountant can edit the sales tax and financial dimensions information on invoice milestones up until the Project invoice proposal is created.

## Import from staging

To import the billed sales lines into the project invoice proposal, run the **Import from staging table** periodic process. If any unbilled sales lines weren't previously posted, the invoice lines don't populate in the invoice proposal.

### Selective import from staging

Starting with version 10.0.47, the **Feature management** workspace includes a new preview feature called "Project Operations selective import from staging". When you use this feature, project accountants can complete the import from staging process from the context of a selected invoice proposal. This functionality streamlines the ability to immediately create the invoice proposal for situations where you want to immediately complete the invoice instead of waiting for the periodic process scheduled run or for unrelated transactions to be processed.

## Create project invoice proposals

You can review project invoice proposals in the **Project management and accounting** module by going to **Project invoices** > **Project invoice proposals**.

When you confirm the Proforma invoice in Dataverse, the system creates the Project invoice proposal header in Finance. For easier reconciliation, the system sets the Project invoice proposal number in Finance to the same number as the Proforma invoice ID in Dataverse. Because users don't necessarily confirm Proforma invoices in the same order they create them, the Project invoice proposal number sequence in Finance must allow for changes to lower and higher numbers. Configure number sequences by using the following steps:

1. In Finance, go to **Organization Administration** > **Number sequences** > **Number sequences**.
1. In the **Area** filter, select **Projects**.
1. In the **Reference** filter, select **Invoice proposal**.
1. Use the **Company** field to filter each legal entity with Project Operations Dataverse integration enabled.
1. Open **Number Sequence details**. On the **General** tab, set the following values:

    - **Allow user changes: To a lower number** = **Yes**
    - **Allow user changes: To a higher number** = **Yes**

The system adds Project invoice proposal lines by using the periodic process **Import from staging table** (**Project management and accounting** > **Periodic** > **Project Operations integration** > **Import from staging table**). You can run this process manually or by using a periodic schedule. The system doesn't add lines to the invoice proposal document until all the lines are ready to be invoiced. Time and material transactions are ready to be invoiced only when you post them by using the **Project Operations Integration** journal.

## Format and print invoice proposals

The project accountant can customize a project invoice printout by using the **Format invoice proposal** page and print management capabilities.

### Format invoice proposals

The **Format invoice proposals** page enables you to group transactions for display in the customer project invoice.

1. On the **Project invoice proposal** page, select **Print** > **Format invoice proposal**.
1. Select **New** to create a new grouping for the project invoice printout.
1. In the **Detail/Summary** field, select options for this grouping:

    - Select **Detail** to print the transaction details of the customer invoice.
    - Select **Summary** to print the transaction summary of the customer invoice.

> [!NOTE]
> The selection in the **Detail/Summary** field on the **Format invoice proposal** page overrides the option selected in the **Invoice format** field on the **Invoice proposals** page to print a detailed invoice or a summarized invoice.

- Select the transaction lines to include in this section on the **Available transactions** tab and select **Include transactions** to move them to the **Selected transactions** tab.
- Select **Move up** and **Move down** to change the order of the sections.
- Select **Print preview** to preview formatted invoice.

### Print management

Print management uses different report files to print, specify destinations, and customize footer text for the invoice. Set up print management at the module level, but you can override these settings for a specific customer, contract, or invoice proposal. To access this function on the **Project invoice proposal** page, select **Print** > **Print management**.

Print management setup is displayed as a tree view, where each node level displays the available documents to adjust. You can assign custom printouts at the module, customer, contract, or invoice proposal document level. To modify the original document printout, expand the desired node and select **Original item**. In the **Report format** field, select the report format to use for printing. You can use custom report formats by using [Business Document Management framework](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management).

## Post invoice proposals

After you review and edit the invoice, and you're satisfied with the invoice proposal lines, check the invoice totals and sales tax. In the **Details** group, select **Totals** and then select **Post** to post the invoice.

To view the invoice before posting, clear the **Posting** check box. **Pro forma** prints on the invoice to signify it's a sample invoice. To print the invoice, select the **Print invoice** check box.

In addition to the **Invoice proposal** page, you can also post invoice proposals by running the periodic job, **Post invoice proposals**. To find this job, go to **Project management and accounting** > **Periodic** > **Project invoices** > **Post invoice proposals**.

This page shows all the invoice proposals that are ready for posting. You can schedule posting invoice proposals by selecting **Batch**. Set the **Batch processing parameter** to **Yes** and set the recurrence of batch processing by selecting **Recurrence**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
