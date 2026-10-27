---
title: Create intercompany customer and vendor invoices
description: This article provides information about how to create intercompany customer and vendor invoices.
author: ryansandness
ms.author: ryansandness
ms.date: 10/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create intercompany customer and vendor invoices

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

A project accountant in a lending legal entity creates an intercompany customer invoice for the project costs that are transferred to the borrowing entity. After the intercompany customer invoice is approved and posted, the lending legal entity sends the intercompany invoice to the borrowing legal entity.

The project accountant for the lending legal entity can set up a batch process to generate intercompany invoices on a recurring basis. The project accountant specifies the criteria, such as specific projects, to create intercompany invoices in a batch.

## Enhanced filtering and transaction details

The **Enhance intercompany invoicing filters and details** feature adds selection, filtering, and traceability capabilities to intercompany invoicing. This feature is newly available with the 10.0.50 release. An administrator can enable or disable the feature in the **Feature management** workspace.

When the feature is enabled, you can:

- Use start and end dates in periodic processing, matching the date criteria already available during manual processing.
- Use **Invoicing method** to select transactions by amount. The default value is **Both**, which is the original behavior. Options for selection include:
  - **Both** includes positive and negative transactions under the normal invoice grouping.
  - **Invoices** includes transactions whose amount is zero or greater.
  - **Credit notes** includes transactions whose amount is less than zero.
  - **Both but Separate** includes positive and negative transactions in separate invoice groupings.
- **Original transaction** has been added to the **Line details** on each line to give you the document number for the originating transaction. You no longer have to navigate by using the button of the same name to get this document number detail. 
- The bookable resource name appears in the new **Resource** field to identify when work such as expenses or time were logged for a specific worker. The displayed value depends on whether the **Use employment default dimensions on integration journals** feature and related setup is completed for the worker.
- Traceability from the original intercompany invoice to a credit or correction intercompany invoice is possible. The original intercompany invoice number is shown and links back to the original intercompany invoice.
- Creation of intercompany invoices now defaults **Project advanced journal line** as enabled by default.

## Manually create an intercompany customer invoice for project transactions

Follow these steps to manually create an intercompany customer invoice for project transactions.

Perform the following steps in the lending legal entity.

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Project invoices** > **Intercompany customer invoices**. On the **Intercompany customer invoices** list page, on the Action Pane, select **New**.
1. On the **Create intercompany invoice** page, in the **Legal entity** field, select one or more borrowing legal entities.
1. Optionally, enter a specific project contract and project number.
1. To limit the results by posting date, enter dates in the **Start date** and **End date** fields. Only eligible intercompany transactions within the specified range appear in the results.
1. Optionally, set **Invoicing method** to filter the lines based on balance instead of the default value of **Both**.
1. Select the transactions to invoice, or select **Select all** to invoice all the transactions in the list, and then select **OK**.
1. Select **Search**.
1. In the search results, select the transactions to include in the intercompany invoice proposal, and then select **OK**. On the **Intercompany customer invoice** page, you can add or remove lines and review line details before posting:
    1. On the **Intercompany customer invoice** page, open the invoice details, and then select **Add line**.
    1. To remove a line, select it, and then select **Remove**.
    1. Review comments, reasons, financial dimensions, and other information about a selected line in the invoice line details.
1. To post the intercompany customer invoice, on the Action Pane, select **Post**.

> [!NOTE]
> If your organization requires that intercompany invoices be reviewed before they're posted, a system administrator might set up a workflow for intercompany invoices. If a workflow isn't set up for intercompany invoices, you can post the intercompany invoice.

## Create a batch job for intercompany invoices

Create multiple intercompany invoices at the same time for all borrowing legal entities. By using the search functionality, you can, for example, search for all transactions that are posted by borrowed workers and related to projects that other legal entities manage. Then, for each borrowing legal entity, create an intercompany invoice for the transactions provided in the search results.

1. Go to **Project management and accounting** > **Periodic** > **Project invoices** > **Create intercompany customer invoices**.
1. On the **Create intercompany customer invoices** page, in the **Company** field, select one or more legal entities to invoice.
1. In **Create one invoice per**, select whether to create an invoice for intercompany transactions based on a project or based on a borrowing legal entity.
1. Enter the **Start date** and **End date**, and optionally, set **Invoicing method** to filter the lines based on balance instead of the default value of **Both**.
1. Optional: To filter by project contract, project, or other available criteria, select **Select**. On the **Inquiry** page, enter the criteria, and then select **OK**.
1. On the **Batch** tab, set up a batch process to create intercompany invoices on a recurring basis. The start and end dates are saved as batch criteria. Select **OK** to run or submit the process. For more information, see [Submit a batch processing job from a form](/dynamicsax-2012/appuser-itpro/submit-a-batch-processing-job-from-a-form).
1. After the process generates the intercompany invoices, select the invoices to post. On the **Action** pane, select **Post**.

> [!NOTE]
> If your organization requires that intercompany invoices be reviewed before they're posted, a system administrator might set up a workflow for intercompany invoices. If a workflow isn't set up for intercompany invoices, you can post the intercompany invoices.

## Review source and original invoice details

On an intercompany customer invoice, select a line. Select the **Line details** tab and navigate to **Intercompany project**.

- For a Project advanced journal line, use **Resource name** to identify the resource.
- The **Original invoice** field identifies the original intercompany customer invoice.

## Post the intercompany vendor invoice

A project accountant in the borrowing legal entity can review intercompany pending vendor invoices when the corresponding intercompany customer invoice is posted. In Finance, in the borrowing legal entity, go to **Accounts payable** > **Invoices** > **Pending vendor invoice**. The pending invoice number matches the intercompany customer invoice number. Verify that the invoice is correct and then post the invoice. Posting the intercompany vendor invoice creates a project subledger and a general ledger transaction that reflects the transaction costs in the borrowing legal entity.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
