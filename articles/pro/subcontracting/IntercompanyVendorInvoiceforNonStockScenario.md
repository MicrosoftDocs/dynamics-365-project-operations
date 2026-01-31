---
title: Intercompany vendor invoice
description: Learn how to create and post intercompany vendor invoices in Microsoft Dynamics 365 Project Operations for resource-based and non-stocked scenarios.
author: mukumarm
ms.date: 01/30/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: mukumarm
ms.custom: bap-template
---

# Intercompany vendor invoice

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Project Operations Integrated with ERP_

To use the capabilities described in this article, activate the following features in the Feature Management workspace.

- **Enable subcontract actuals processing with Project Operations for resource-based scenarios**.
- **Enable Intercompany Vendor invoices for resource-based/non-stocked scenarios**.

## Minimum version required

To use this feature for Microsoft Dynamics 365 Project Operations non-stocked/resource-based scenarios, the following versions are required:

- **Project Operations Dataverse** version 4.88.0.0 or later.
- **Dynamics 365 Finance** version 10.0.38 or later.

## Run dual-write maps for the vendor invoice lines

Make sure that the mapping for Project Operations integration **project vendor invoice line export entity** and **msdyn_projectvendorinvoicelines** use version **1.0.0.6** or later.

The following screenshot shows the dual-write entity map that's used for vendor invoice lines.

:::image type="content" source="../media/MKVendorInvoiceLinesDualWrite.png" alt-text="Screenshot of the dual-write entity map with Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) highlighted.":::

The following screenshot shows the dual-write field mapping that's used for vendor invoices lines.

:::image type="content" source="../media/MKVendorInvoiceLinesDetailDualWrite.png" alt-text="Screenshot of the dual-write field map with PROJDATAAREAID and DAREAID highlighted.":::

## Create and post an intercompany vendor invoice

**USPM**, the lending legal entity, creates and posts the intercompany vendor invoice for a project from **GBPM**, the borrowing legal entity.
This **vendor invoice** represents the outsourced labor and expense that vendors perform and USPM pays.

To create an intercompany invoice, follow these steps:

1. In Microsoft Dynamics 365 Finance, go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.
1. To create a vendor invoice, on the **Action** pane, select **New**.
1. On the **Invoice header**, in the **Invoice account field**, select **Subcontractor**.
1. Select the **Invoice date**.
1. On the **Invoice line** FastTab, select **Add line** to create a **vendor invoice line**.
1. Select the **Procurement category** that you created for subcontract lines, and enter the **unit price**, **unit of measurement**, and **quantity**.
1. In the **vendor invoice lines** section, on the **Project tab**, select the Project company **GBPM** and the **project** from the **GBPM** company.
1. Select the **Project category**. It can be of type **expenses** or **hours**. If the selected **project category** is of the hour type, select the role.
1. Select **Post** to post the vendor invoice.

After you successfully post the **vendor invoice**, it becomes accessible within Microsoft Dataverse for verification and processing by the **project manager**. For more information about the process of verifying vendor invoices in Dataverse, see **[Verification of vendor invoices](VI-Verification.md)**. When you confirm an **intercompany vendor invoice** in Dataverse, this action triggers the generation of corresponding actual transactions within the Dataverse system.

| Transaction type  | Description |
| ------------- | ------------- |
| Cost  | You create this transaction for the borrowing legal entity. It doesn't synchronize with Dynamics 365 Finance for integration journal posting.  |
| Unbilled sales  | You create this transaction for the borrowing legal entity. It synchronizes with Dynamics 365 Finance for integration journal posting.  |
| Inter-organizational sales | You create this transaction for the lending legal entity. It synchronizes with Dynamics 365 Finance for integration journal posting.         |
| Resourcing unit cost | You create this transaction for the lending legal entity. It synchronizes with Dynamics 365 Finance for integration journal posting.          |

## Post the integration journal for the lending legal entity

After the project manager validates and approves the vendor invoice within Dataverse, the next step is to post **Project Integration Journals** in Dynamics 365 Finance for the lending legal entity.

To post the integration journal for the lending legal entity, follow these steps:

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Periodic** > **Project Operations on Customer Engagement** > **Import from staging** and select to run the periodic process. This periodic process fills in Project Operations Integration journal.
1. Go to **Project management and accounting** > **Journals** > **Project Operations integration journal** and review the journal lines. The system creates the journal lines for **Inter-organizational sales** and **Resourcing unit cost**.
1. On the **Action** pane, select **Post** to post the integration journal.

After you post the **Project integration journal**, the lending legal entity generates an **Intercompany customer invoice** and the borrowing legal entity performs the **vendor invoice posting**.

For more information about the process of creating intercompany customer and vendor invoices, see **[Create intercompany customer and vendor invoices](../../project-accounting/create-intercompany-customer-vendor-invoices.md)**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
