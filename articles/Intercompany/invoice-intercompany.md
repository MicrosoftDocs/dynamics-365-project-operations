---
# required metadata

title: Create intercompany customer and vendor invoices
description: This article provides information and examples on creating intercompany customer and vendor invoices.
author:  sigitac
manager: tfehr
ms.date: 11/05/2020 
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: sigitac

---

A project accountant in a lending legal entity can create an intercompany customer invoice for the project costs that are being transferred to the borrowing entity. After the intercompany customer invoice is approved and posted, the lending legal entity can send the intercompany invoice to the borrowing legal entity.

The project accountant for the lending legal entity can also set up a batch process to generate intercompany invoices on a recurring basis. The project accountant can select criteria such as specific projects to create intercompany invoices in a batch.

## Create an intercompany customer invoice for selected project transactions manually

Use this procedure to create an intercompany customer invoice for project transactions manually. Select criteria to search for hours that were posted by workers on projects in borrowing legal entities, and for expenses that were incurred by your legal entity on behalf of borrowing legal entities. You can search by legal entity name, project contract number, project number, date range, or any combination of these options. In the search results, select the transactions to add to an intercompany invoice.

1. In Finance navigate to **Project management and accounting**  \&gt;   **Project invoices**  \&gt;  **Intercompany customer invoices**. On the  **Intercompany customer invoices**  list page, on the  **Action Pane** , click  **New.**
2. In the  **Create intercompany invoice**  form, in the  **Legal entity**  field, select a borrowing legal entity.
3. Optional: Enter a specific project contract and project number.
4. Narrow the search by selecting a date range. Enter specific dates in the  **Start date**  and  **End date**  fields. Only intercompany transactions that are posted within this date range are displayed in the search results.
5. Set **Project advanced journal line parameter** to Yes.
6. Click  **Search**.
7. In the search results, select the transactions to include in an intercompany invoice proposal, and then click  **OK**.
8. In the  **Intercompany customer invoice**  form the intercompany project transactions that you selected from the search results are displayed. To modify the transactions before you send the invoice to the borrowing legal entity, do the following:
  - Open the  **Create invoice proposal**  form and select additional intercompany transactions for the current invoice, click  **Add line**.
  - Delete a line, by selecting it, and then click  **Remove**.
  - View comments, reasons, financial dimensions, and other information about a selected line on the tabs on the  **Invoice lines**  FastTab.
9. To post the intercompany customer invoice, on the  **Action Pane** , click  **Post**.

>> **Note**
>> If your organization requires that intercompany invoices be reviewed before they are posted, a system administrator might set up a workflow for intercompany invoices. If a workflow is not set up for intercompany invoices, you can post the intercompany invoice.

## Create a batch job for intercompany invoices

You can create multiple intercompany invoices at the same time by selecting filters to search for intercompany transactions for all borrowing legal entities. For example, you can search for projects that are managed by other legal entities for all transactions that are posted by borrowed workers, and then create an intercompany invoice for each borrowing legal entity for the transactions that are displayed in the search results.

1. Click  **Project management and accounting**  \&gt;  **Periodic**  \&gt;  **Project invoices**  \&gt;  **Create intercompany customer invoices**.
2. In the  **Create intercompany customer invoices**  form, in the  **Company**  field, select a legal entity to invoice. If you don&#39;t select a company, all transactions that meet the search criteria are displayed for all borrowing legal entities.
3. In the  **Create one invoice per**  field, select whether to create an invoice for intercompany transactions based on a project or based on a borrowing legal entity.
4. Optional: To select a specific project and project contract for which to create intercompany invoices, click  **Select**. In the  **Inquiry**  form, in the  **Criteria**  field, select the project contract, project number, or both, and then click  **OK**.
5. On the  **Batch**  tab, set up a batch process to create intercompany invoices on a recurring basis. For more information, see [Submit a batch processing job from a form](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/submit-a-batch-processing-job-from-a-form).
6. To post the intercompany invoices, on the  **Action Pane** , click  **Post**.

>>**!Note**
>> If your organization requires that intercompany invoices be reviewed before they are posted, a system administrator might set up a workflow for intercompany invoices. If a workflow is not set up for intercompany invoices, you can post the intercompany invoices.

## Post the intercompany vendor invoice

A project accountant in a borrowing legal entity can review intercompany pending vendor invoices as soon as corresponding intercompany customer invoice is posted. In Finance, open borrowing legal entity and navigate to Accounts payable \&gt; Invoices \&gt; Pending vendor invoice. Created pending number invoice number will match intercompany customer invoice number. Review the invoice for correctness and post. Posting intercompany vendor invoice will create project subledger and general ledger transaction reflecting transactions cost in borrowing legal entity.
