---
title: Set up automatic invoice creation 
description: This article provides information about how to set up and configure automatic creation of proforma invoices.
author: suvaidya
ms.author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up automatic invoice creation 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

You can configure automatic invoice creation in Dynamics 365 Project Operations. The system creates a draft proforma invoice based on the invoice schedule for each project contract and contract line. Invoice schedules are configured at the contract line level. Each line on a contract can have a distinct invoice schedule, or the same invoice schedule can be included on every line of the contract.

When you create an invoice, the system always creates at least one invoice per project contract. In some cases, there may be multiple invoices created. For example, if the contract has multiple customers, the same number of invoices are created as the number of customers that have billable transactions to invoice on that project contract.

## Understand how transactions are included on an invoice 

Sometimes, each project-based contract line specifies a separate invoice schedule. For example, implementation services for the Adatum contract have the following contract lines:

- Prototype work that is a fixed price with two manually created milestones.
- Implementation work that includes Time and is billed bi-weekly on Mondays.
- Expenses incurred that need to be billed monthly on the first Monday of each month.

Invoice schedules defined on each of these two line items look like the following table:

| Contract line | Invoice run date | Transaction cut-off date | Milestone date | Milestone amount |
| --- | --- | --- | --- | --- |
| Prototype work | October 5, Monday | - | October 5, Monday | 5,000 USD |
| - | November 3, Tuesday | - | November 3, Tuesday | 12,000 USD |
| Implementation work | October 5, Monday | October 4, Sunday | - | - |
| - | October 19, Monday | October 18, Sunday | - | - |
| - | November 2, Monday | November 1, Sunday | - | - |
| - | November 16, Monday | November 15, Sunday | - | - |
| Expenses incurred | October 5, Monday | October 4, Sunday | - | - |
| - | November 2, Monday | November 1, Sunday | - | - |

In this example when the automatic invoicing runs on:

- **October 4 or any date before**: No invoice is generated for this contract because the **Invoice Schedule** table for each of these contract lines doesn't call out October 4, Sunday as an invoice run date.
- **October 5 Monday**: One invoice is generated for:

    - Prototype work that includes the milestone, that's marked as **Ready to Invoice**.
    - Implementation work that includes all Time transactions created before the transaction cut-off date of October 4, Sunday, that's marked as **Ready to Invoice**.
    - Expense incurred that includes all Expense transactions created before the transaction cut-off date of October 4, Sunday, that's marked as **Ready to Invoice**.
  
- **On October 6 or any date before October 19**: No invoice is generated for this contract since the **Invoice Schedule** table for each of these contract lines doesn't call out October 6 or any date before October 19 as an invoice run date.
- **October 19, Monday**: One invoice is generated for implementation work that includes all Time transactions created before the transaction cut-off date of October 18, Sunday, that is marked as **Ready to Invoice**.
- **November 2 Monday**: One invoice is generated for:

    - Implementation work that includes all Time transactions created before the transaction cut-off date of November 1, Sunday, that'is marked as **Ready to Invoice**.
    - Expense incurred that includes all Expense transactions created before the transaction cut-off date of November 1, Sunday, that's marked as **Ready to Invoice**.

- **November 3, Tuesday**: One invoice is generated for prototype work that includes the milestone for 12,000 USD, that's marked as **Ready to Invoice**.

## Configure automatic invoicing

Complete the following steps to configure an automated invoice run.

1. In **Project Operations**, go to **Settings** > **Recurring Invoice Setup**.
2. Create a batch job, and name it **Project Operations Create Invoices**. The name of the batch job must include the words, "create invoices".
3. In the **Job Type** field, select **None**. By default, the **Frequency Daily** and **Is Active** fields are set to **Yes**.
4. Select **Run Workflow**. In the **Look Up Record** dialog box, you see three workflows:

- ProcessRunCaller
- ProcessRunner
- UpdateRoleUtilization

5. Select **ProcessRunCaller**, and then select **Add**.
6. In the next dialog box, select **OK**. A **Sleep** workflow is followed by a **Process** workflow. 

> [!NOTE]
> You can also select **ProcessRunner** in step 5. Then, when you select **OK**, a **Process** workflow is followed by a **Sleep** workflow.

The **ProcessRunCaller** and **ProcessRunner** workflows create invoices. **ProcessRunCaller** calls **ProcessRunner**. **ProcessRunner** is the workflow that actually creates the invoices. The workflow goes through all the contract lines that invoices must be created for, and creates invoices for those lines. To determine the contract lines that invoices must be created for, the job looks at invoice run dates for the contract lines. If contract lines that belong to one contract have the same invoice run date, the transactions are combined into one invoice that has two invoice lines. If there are no transactions to create invoices for, the job skips creating an invoice.

After **ProcessRunner** has finished running, it calls **ProcessRunCaller**, provides the end time, and is closed. **ProcessRunCaller** then starts a timer that runs for 24-hours from the specified end time. At the end of the timer, **ProcessRunCaller** is closed.

The batch process job for creating invoices is a recurrent job. If this batch process is run many times, multiple instances of the job are created and causes errors. Therefore, you should start the batch process only one time, and then restart only if it stops running.

> [!NOTE]
> Batch invoicing in Project Operations only runs for project contract lines that are configured by invoice schedules. A contract line with a fixed price billing method must have milestones configured. A project contract line with a time and material billing method needs a date-based invoice schedule set up.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
