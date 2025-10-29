---
title: Create intercompany customer and vendor invoices
description: This article provides information about how to create intercompany customer and vendor invoices.
author:  ryansandness
ms.author: ryansandness
ms.date: 10/29/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create intercompany customer and vendor invoices

_**Applies To:** Project Operations Integrated with ERP_

A project accountant in a lending legal entity creates an intercompany customer invoice for the project costs that are being transferred to the borrowing entity. After the intercompany customer invoice is approved and posted, the lending legal entity sends the intercompany invoice to the borrowing legal entity.

The project accountant for the lending legal entity can set up a batch process to generate intercompany invoices on a recurring basis. The project accountant specifies the criteria, such as specific projects, to create intercompany invoices in a batch.

## Manually create an intercompany customer invoice for project transactions 

Use this procedure to manually create an intercompany customer invoice for project transactions. Search for hours that were posted by workers on projects in the borrowing legal entities and for expenses that were incurred by your legal entity on behalf of borrowing legal entities. You can search by legal entity name, project contract number, project number, date range, or any combination of these options. In the search results, select the transactions to add to an intercompany invoice. 

The following steps must be performed in the lending legal entity. 

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Project invoices** > **Intercompany customer invoices**. On the **Intercompany customer invoices**  list page, on the Action Pane, select **New.**
2. On the **Create intercompany invoice** page, in the **Legal entity** field, select a borrowing legal entity.
3. Optional: Enter a specific project contract and project number.
4. Narrow the search by selecting a date range. Enter specific dates in the **Start date** and **End date** fields. Only intercompany transactions that are posted within this date range are displayed in the search results.
5. Set **Project advanced journal line parameter** to **Yes** and select **Search**.
6. In the search results, select the transactions to include in the intercompany invoice proposal, and then select **OK**.
7. On the **Intercompany customer invoice** page, the intercompany project transactions that you selected from the search results are displayed. To modify the transactions before you send the invoice to the borrowing legal entity, do the following:
  
    1. On the **Intercompany customer invoice** page, open the invoice details, and then select **Add line**.
    2. To remove a line, select it, and then select **Remove**.
    3. View comments, reasons, financial dimensions, and other information about a selected line on the invoice line details.
    
8. To post the intercompany customer invoice, on the Action Pane, select **Post**.

> [!NOTE]
> If your organization requires that intercompany invoices be reviewed before they are posted, a system administrator might set up a workflow for intercompany invoices. If a workflow is not set up for intercompany invoices, you can post the intercompany invoice.

## Create a batch job for intercompany invoices

You can create multiple intercompany invoices at the same time for all borrowing legal entities. Using search functionality, you can for example, search for all transactions that are posted by borrowed workers and related to projects that are managed by other legal entities. Then, for each borrowing legal entity, you can create an intercompany invoice for the transactions provided in the search results.

1. Go to **Project management and accounting** > **Periodic** > **Project invoices** > **Create intercompany customer invoices**.
2. On the **Create intercompany customer invoices** page, in the **Company**  field, select a legal entity to invoice. 
3. In **Create one invoice per**, select whether to create an invoice for intercompany transactions based on a project or based on a borrowing legal entity.
4. Optional: To select a specific project and project contract to create intercompany invoices for, click **Select**. On the **Inquiry** page, in the **Criteria** field, select the project contract, project number, or both, and then select **OK**.
5. On the **Batch** tab, set up a batch process to create intercompany invoices on a recurring basis. For more information, see [Submit a batch processing job from a form](/dynamicsax-2012/appuser-itpro/submit-a-batch-processing-job-from-a-form).
6. To post the intercompany invoices, on the Action Pane, select **Post**.

> [!NOTE]
> If your organization requires intercompany invoices be reviewed before they are posted, a system administrator might set up a workflow for intercompany invoices. If a workflow is not set up for intercompany invoices, you can post the intercompany invoices.

## Post the intercompany vendor invoice

A project accountant in the borrowing legal entity can review intercompany pending vendor invoices when the corresponding intercompany customer invoice is posted. In Finance, in the borrowing legal entity, go to **Accounts payable** > **Invoices** > **Pending vendor invoice**. The pending invoice number will match the intercompany customer invoice number. Verify that the invoice is correct and then post the invoice. Posting intercompany vendor invoice creates a project subledger and a general ledger transaction that reflects the transaction costs in the borrowing legal entity.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
