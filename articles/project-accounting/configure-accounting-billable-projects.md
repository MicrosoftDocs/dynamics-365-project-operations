---
title: Configure accounting for billable projects
description: This article provides information about the accounting options for billable projects.
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure accounting for billable projects

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations supports various accounting options for billable projects that include time and material and fixed price transactions.

- **Time and material transactions**: These transactions are invoiced as the work progresses based on the consumption of hours, expenses, items, or fees on the project. These transaction costs can be matched with the revenue on each transaction and the project is invoiced as work progresses. Project revenue can be also accrued at the time when the transaction occurs. During invoicing, revenue is recognized and if applicable, accrued revenue is reversed.
- **Fixed-price transactions**: These transactions are invoiced according to a billing schedule that is based on the project contract. Revenue for fixed price transactions can be recognized at invoicing or calculated and posted periodically, according to the **Completed contract** or **Completed percentage** methods.

A project is considered billable when it's associated with one or more contract lines. A project contract line defines for itself which billing method and transaction types are allowed.

As an example, Fabrikam Robotics has won a project contract with Adatum corporation for equipment optimization. Adatum pays a fixed amount of $10.000 USD to cover incurred project expenses. This is a fixed price billing method. Project time and fees is billed per use. This is a time and material billing method. All of the work is tracked under a single project named, Adatum equipment optimization.

A project team member submits eight hours of work on the Adatum equipment optimization project. When the project manager approves this time, the system uses the time and material billing method to create actuals transactions, an invoice, and an account. This transaction isn't included in the fixed price revenue estimate calculation.

Another project team member submits a travel expense for $2000.00 USD against the Adatum equipment optimization project. When the project manager approves this submission, the system uses a fixed price billing method to create actuals transactions and an account for this project expense. The customer isn't invoiced based on this transaction. Instead, they are invoiced by using separately configured billing milestones. This expense transaction, along with expense estimates, is included in the fixed price revenue estimate calculation.

Accounting principles for project transactions are defined in project cost and revenue profiles. For every project transaction, the system determines the appropriate project cost and revenue profile by using the project cost and revenue profile rules that have been configured.

## Define project cost and revenue profiles 

Project cost and revenue profiles determine the accounting rules for project transactions. These profiles are configured in Project management and accounting. 

Complete the following steps to create a new project cost and revenue profile. 

1. Go to **Project management and accounting** > **Setup** > **Posting** > **Project cost and revenue profiles**. 
2. Select **New** to create a new project cost and revenue profile.
3. In the **Name** field, enter the name and a brief description of the profile.
4. In the **Billing method** field, select **Time and material** or **Fixed price**.
5. Expand the **Ledger** FastTab. The fields on this tab define the accounting principles that are used when project transactions are journalized using the Project Operations integration journal and then invoiced through the Project invoice proposal.
6. Select the appropriate information in the following fields on the **Ledger** FastTab:

    - **Post costs – hour**:

       - *No Ledger*: The cost for time transactions isn't posted to the Ledger when the Project Operations integration journal is posted. However, the accountant can post costs using the Post costs function at a later time.
       - **Balance**: The cost for time transactions is debited to the Ledger account type, *WIP - Cost value* and credited to the *Payroll allocation account* in Ledger posting setup. The accountant uses the Post costs function to move this cost from a Balance account to a Profit and loss account on a periodic basis.
       - **Profit and loss**: When posting the Project Operations integration journal, the time transaction cost is debited to the Ledger account type *Cost*, and credited to the *Payroll allocation account* defined on the **Cost** tab on the **Ledger posting setup** page (**Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**). This is most common setup for time and material transactions.
        - *Never Ledger*: The cost for time transactions are never posted to the Ledger.

    - **Post costs – expense**:

         - **Balance**: When posting the Project Operations integration journal, the expense transaction cost is debited to the Ledger account type *WIP - Cost value* as defined on the **Cost** tab on the **Ledger posting setup** page and credited to the offset account on the journal line. Default offset accounts for expense are defined in **Project management and accounting** > **Setup** \> **Posting** \> **Default offset account for expenses**. The accountant uses the **Post costs** function to move this cost from the balance account to the profit and loss account on a periodic basis.
        - **Profit and loss**: When posting the Project Operations integration journal, the expense transaction cost is debited to the Ledger account type *Cost* as defined on the **Cost** tab on the **Ledger posting setup** page and credited to the offset account on the journal line. Default offset accounts for expense are defined in **Project management and accounting** \> **Setup** \> **Posting** \> **Default offset account for expenses**.
      
    - **Post costs – item**:

         - **Balance**: When posting the Project Operations Integration journal, the item transaction cost is debited to the Ledger account type *WIP - Cost value - item* as defined on the **Cost** tab on the **Ledger posting setup** page and credited to the following:
    
              - For document type usage: **Cost - item** account on the **Ledger posting setup**.  
              - For document type purchase: **Procurement integration account** on the **Project Management and accounting parameters**.
           The accountant uses the **Post costs** function to move this cost from the balance account to the profit and loss account on a periodic basis.
        - **Profit and loss**: When posting the Project Operations Integration journal, the item transaction cost is debited to the Ledger account type *Cost* as defined on the **Cost** tab on the **Ledger posting setup** page and credited to the following:
         
             - For document type usage: **Cost - item** account on the **Ledger posting setup**.  
             - For document type purchase: **Procurement integration account** on the **Project Management and accounting parameters**.
       
    - **On account invoicing**:

        - **Balance**: When posting the Project invoice proposal, an on-account transaction (billing milestone) is credited to the Ledger account type *WIP Invoiced - on account* as defined on the **Revenue** tab on the **Ledger posting setup** page, and debited to the Customer balance account.
         - **Profit and loss**: When posting the Project invoice proposal, an on-account transaction (billing milestone) is credited to the Ledger account type *Invoiced revenue- on account* as defined on the **Revenue** tab on the **Ledger posting setup** page, and debited to the Customer balance account. Customer balance accounts are defined in **Accounts receivable** \> **Setup** \> **Customer posting profiles**.

   When you define the posting profiles for Time and material billing methods, you have the option to accrue revenue per transaction type (hour, expense, item, and fee). If the **Accrue revenue** option is set to **Yes**, unbilled sales transactions in the Project Operations Integration journal is recorded to the general ledger. The sales value is debited to the **WIP - sales value account** and credited to the **Accrued revenue - sales value** account that was set up on the **Ledger posting setup** page on the **Revenue** tab. 
  
  > [!NOTE]
  > The option, **Accrue revenue** is available only when the respective transaction type **Cost** is posted to the profit and loss account.
    
7. Expand the **Estimate** FastTab. The fields on this tab define the calculation settings for fixed price revenue estimates. The fields on this tab only apply to Project cost and revenue profiles with a billing method of **Fixed–price**.
8. Select the appropriate information in the following fields on the **Estimate** FastTab:

    - **Principle used for project completion calculations**:

        - **Completed contract**: Cost matching and revenue recognition doesn't occur until the end of the project. Costs reflect as WIP in the balance until the project is complete.
        - **Completed percentage**: Accrued revenue is calculated and posted to the ledger every period based on the project completion percentage. There are multiple methods available to calculate percentage completion. These methods can be automatic based on configuration, or manual.
        - **No WIP**: This setup is used for fixed price projects with a short time span and where the invoice and the costs occur in the same period. In this case, the **On-account invoicing** field value on the **Ledger** FastTab is automatically set to **Profit and loss** to ensure revenue is recognized at invoicing. The Revenue estimation process isn't used for this project cost and revenue profile.

    - **Matching principle**: This field determines how the calculated sales value (accrued revenue) is posted to the ledger.

        - Using the **Sales value** principle, the system calculates the sales value by matching costs and revenue and then posting it as a single amount.
        - Using the **Production and profit** principle, the system splits the sales value into realized costs and calculated profit. These are posted separately.

    - **Cost templates**: Allow project transactions to be grouped based on transaction type and project category and define percentage completion calculation rules for these groups.
    - **Period codes**: Define the frequency with which revenue estimates are calculated for a given Project cost and revenue profile.
    - **Categories for estimate**: Used for sales value (accrued revenue) posting to Project transactions. First, configure the dedicated project category for a **Fee** transaction type and then set the flag, **Estimate** for this project category. Next, depending on selected matching principle, pick this project category in the **Sales** value or the **Profit** field in the Project cost and revenue profile.

### Sample configurations for Project cost and revenue profiles

Time and materials – no WIP

![Cost and revenue profile: Time and materials - no WIP.](media/time-material-no-wip.png)

Time and materials – WIP (revenue)

![Cost and revenue profile: Time and materials - WIP.](media/time-material-with-wip.png)

Fixed Price – No WIP

![Cost and revenue profile: Fixed price - no WIP.](media/fixed-price-no-wip.png)

Fixed Price – completed contract

![Cost and revenue profile: Fixed price - completed contract.](media/fixed-price-completed-contract.png)

Fixed Price – percentage completion

![Cost and revenue profile: Fixed price - percentage completion.](media/fixed-price-completed-percentage.png)


## Accounting event examples for sample Project cost and revenue profiles.

| Accounting Event                  | Time and Material - No WIP                       | Time and Material - WIP                                                                                           | Fixed price – no WIP                                            | Fixed price – Completed contract                                                                            | Fixed Price – Completed percentage                             |
|-----------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| Journalizing time transactions    | Debit – Cost <br>Credit –Payroll allocation          | Debit - Cost <br>Credit –Payroll Allocation <br>Debit –WIP Sales value <br>Credit –Accrued Revenue Sales Value                | Debit – Cost <br>Credit –Payroll allocation                         | Debit – Cost <br>Credit – Payroll allocation                                                                    | Debit – Cost <br>Credit – Payroll allocation                       |
| Journalizing expense transactions | Debit – Cost <br>Credit – Offset account for expense | Debit – Cost <br>Credit – Offset account for expense <br>Debit – WIP Sales value <br>Credit –Accrued Revenue Sales Value      | Debit –Cost <br>Credit – Offset account for expense                 | Debit – Cost<br> Credit – Offset account for expense                                                            | Debit – Cost <br>Credit – Offset account for expense               |
| Invoicing customer                | Debit –Customer balance <br>Credit –Invoiced revenue | Debit – Customer balance <br>Credit – Invoiced revenue <br>Credit – WIP Sales value Debit – Accrued Revenue Sales Value | Debit – Customer balance <br>Credit – Invoiced revenue - on account | Debit –Customer balance <br>Credit – WIP – Invoiced on account                                                  | Debit – Customer balance <br>Credit – WIP - Invoiced on account    |
| Post Revenue Estimate             | Not applicable                                   | Not applicable                                                                                                    | Not Applicable                                                  | Debit – WIP Cost Value <br>Credit –Cost                                                                         | Debit - WIP - Sales value <br>Credit – Accrued revenue Sales value |
| Eliminate                         | Not applicable                                   | Not applicable                                                                                                    | Not Applicable                                                  | Credit – WIP Cost Value <br>Debit – Cost <br>Credit – Accrued Revenue - Sales value <br>Debit – WIP Invoiced on account | Debit – WIP – Invoiced on account <br>Credit – WIP Sales value     |

## Configure Project cost and revenue profile rules

Project cost and revenue profile rules determine the Project cost and revenue profile that must be used when processing any billable project transactions. Define the rules by going to **Project management and accounting** \> **Setup** \> **Posting** \> **Project cost and revenue profile rules**.

Rules can be defined by project contract, project group, or by a specific project. The system always picks the highest granularity rule first.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
