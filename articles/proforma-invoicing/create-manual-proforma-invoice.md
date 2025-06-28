---
title: Proforma invoices
description: This article provides information about proforma invoices in Project Operations.
author: suvaidya
ms.date: 06/10/2024
ms.topic: how-to
ms.custom: 
  - bap-template 
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Proforma invoices

_**Applies To:** Project Operations Integrated with ERP_

Proforma invoicing gives project managers a second level of approval before they create invoices for customers. The first level of approval is completed when time, expense, and material entries that project team members submit are approved. Confirmed proforma invoices are available in the Project Accounting module of Project Operations. Project accountants can perform additional updates such as sales tax, accounting, and invoice layout.


## Creating project invoices

Project invoices can be created one at a time or in bulk. You can create them manually, or they can be configured so that they are generated in automated runs.

### Manually create project invoices 

From the **Project Contracts** list page, you can create project invoices separately for each project contract, or you can create invoices in bulk for multiple project contracts.

Follow this step to create an invoice for a specific project contract.

- On the **Project Contracts** list page, open a project contract, and then select **Create Invoice**.

    An invoice is generated for all transactions for the selected project contract that have a status of **Ready to Invoice**. These transactions include time, expenses, materials, milestones, and other unbilled sales journal lines.

Follow these steps to create invoices in bulk.

1. On the **Project Contracts** list page, select one or more project contracts that you must create an invoice for, and then select **Create Project Invoices**.

    A warning message informs you that there might be a delay before invoices are created. The process is also shown.

2. Select **OK** to close the message box.

    An invoice is generated for all transactions on a contract line that have a status of **Ready to Invoice**. These transactions include time, expenses, materials, milestones, and other unbilled sales journal lines.

3. To view the invoices that are generated, go to **Sales** \> **Billing** \> **Invoices**. You will see one invoice for each project contract.

### Set up automated creation of project invoices 

Follow these steps to configure an automated invoice run.

1. Go to **Settings** \> **Batch jobs**.
2. Create a batch job, and name it **Project Operations Create Invoices**. The name of the batch job must include the term "Create Invoices."
3. In the **Job type** field, select **None**. By default, the **Frequency Daily** and **Is Active** options are set to **Yes**.
4. Select **Run Workflow**. In the **Look Up Record** dialog box, you will see three workflows:

    - ProcessRunCaller
    - ProcessRunner
    - UpdateRoleUtilization

5. Select **ProcessRunCaller**, and then select **Add**.
6. In the next dialog box, select **OK**. A **Sleep** workflow is followed by a **Process** workflow.

    You can also select **ProcessRunner** in step 5. Then, when you select **OK**, a **Process** workflow is followed by a **Sleep** workflow.

The **ProcessRunCaller** and **ProcessRunner** workflows create invoices. **ProcessRunCaller** calls **ProcessRunner**. **ProcessRunner** is the workflow that actually creates the invoices. It goes through all the contract lines that invoices must be created for, and it creates invoices for those lines. To determine the contract lines that invoices must be created for, the job looks at invoice run dates for the contract lines. If contract lines that belong to one contract have the same invoice run date, the transactions are combined into one invoice that has two invoice lines. If there are no transactions to create invoices for, the job skips invoice creation.

After **ProcessRunner** has finished running, it calls **ProcessRunCaller**, provides the end time, and is closed. **ProcessRunCaller** then starts a timer that runs for 24 hours from the specified end time. At the end of the timer, **ProcessRunCaller** is closed.

The batch process job for creating invoices is a recurrent job. If this batch process is run many times, multiple instances of the job are created and cause errors. Therefore, you should start the batch process only one time, and you should restart it only if it stops running.

> [!NOTE]
> Batch invoicing only runs for project contract lines that are configured by invoice schedules. A contract line with a fixed price billing method must have milestones configured. A project contract line with a time and material billing method will need a date-based invoice schedule set up. The same applies to a project-based contract line.      
 
### Edit a draft invoice

When you create a draft project invoice, all unbilled sales transactions that were created when the time, expense, and material usage entries were approved are pulled onto the invoice. You can make the following adjustments while the invoice is still in a draft stage:

- Delete or edit invoice line details.
- Edit and adjust the quantity and billing type.

Select **Confirm** to confirm an invoice. The Confirm action is a one-way action. When you select **Confirm**, the system makes the invoice read-only and creates billed sales actuals from each invoice line detail for each invoice line. If the invoice line detail references an unbilled sales actual, the system also reverses the unbilled sales actual. (Any invoice line detail that was created from a time or expense entry will reference an unbilled sales actual.) General ledger integration systems can use this reversal to reverse project work in progress (WIP) for accounting purposes.

> [!NOTE]
> Confirmed proforma invoices and related records like invoice lines and invoice line details cannot be edited or deleted. 

### Correct a confirmed invoice

Confirmed invoices can be edited (corrected). When you correct a confirmed invoice, a new draft corrective invoice is created. Because the assumption is that you want to reverse all the transactions and quantities from the original invoice, this corrective invoice includes all the transactions from the original invoice, and all the quantities on it are 0 (zero).

If any transactions don't require correction, you can remove them from the draft corrective invoice. If you want to reverse or return only a partial quantity, you can edit the **Quantity** field on the line detail. If you open the invoice line detail, you can see the original invoice quantity. You can then edit the current invoice quantity so that it's less than or more than the original invoice quantity.

When you confirm a corrective invoice, the original billed sales actual is reversed, and a new billed sales actual is created. If the quantity was reduced, the difference will cause a new unbilled sales actual to be created too. For example, if the original billed sale was for eight hours, and the corrective invoice line detail has a reduced quantity of six hours, the original billed sales line is reversed and two new actuals are created:

- A billed sales actual for six hours.
- An unbilled sales actual for the remaining two hours. This transaction can either be billed later or marked as non-chargeable, depending on the negotiations with the customer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
