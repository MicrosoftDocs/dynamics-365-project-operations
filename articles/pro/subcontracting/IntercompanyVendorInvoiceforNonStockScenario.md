---
title: Intercompany vendor invoice
description: This topic outlines the functionality within Microsoft Dynamics 365 Project Operations that enables the intercompany vendor invoices for Project operations non
author: mukumarm
ms.date: 08/09/2023
ms.topic: article
ms.reviewer: johnmichalak 
ms.author: mukumarm
---

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use the functionality that's described in this article, you must enable the feature **Enable subcontract actuals processing with Project Operations for resource based scenarios** and **Enable Intercompany Vendor invoices for resource based/non-stocked scenarios.** in the **Feature management** workspace.

## Create and post intercompany vendor invoice
USPM, the lending legal entity, must create and post the intercompany vendor invoice for a project from GBPM, the borrowing legal entity. 
This vendor invoice represents the outsourced labor and expense that were performed by vendors that are paid by USPM.

1. In **Finance**, go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.
2. On the **Action Pane**, select New to create a **vendor invoice**.
3. On the **Invoice header**, in the Invoice account field, select Subcontractor.
4. Select the **invoice date**.
5. On the **Invoice line** FastTab, select **Add line** to create a **vendor invoice line**.
8. Select the **Procurement category** that was created for subcontract lines, and enter the **unit price**, **unit of measurement**, and **quantity**.
9. In the **vendor invoice lines** section, on the **Project tab**, select the Project company **GBPM** and the **project** from the **GBPM** company.
10. Select the **Project category**. It can be of type **expenses** or **hours**. If the selected **project category** is of the Hour type, select the role.
11. Select **Post** to post the vendor invoice.

When the vendor invoice is posted, it becomes available in **Dataverse** for project manager verification and processing. For verification of vendor invoices in Dataverse see **[Verification of vendor invoices](/articles/project-accounting/create-intercompany-customer-vendor-invoices.md)**.
When an intercompany vendor invoice is **confirmed** in **Dataverse**, the following **Actual transactions** are created in **Dataverse**.

| Transaction type  | Description | 
| ------------- | ------------- |
| Cost  | This transaction is created for Borrowing legal entity and does not synchronize with D365 Finance for integration journal posting.  |
| Unbilled sales  | This transaction is created for Borrowing legal entity and synchronize with D365 Finance for integration journal posting.  |
| Inter-organizational sales | This transaction is created for Lending legal entity and synchronize with D365 Finance for integration journal posting.         |
| Resourcing unit cost | This transaction is created for lending legal entity and  synchronize with D365 Finance for integration journal posting.          |

## Post the integration journal for lending legal entity
Once the vendor invoice is validated and approved by the **Project Manager** within **Dataverse**, the subsequent step involves the posting of **Project Integration Journals** in D365 Finance specifically for the lending legal entity.

1. In **D365 Finance** Go to **Project management and accounting** > **Periodic** > **Project Operations on Customer Engagement** > **Import from staging** and select to run the periodic process. This periodic process will fill in Project Operations Integration journal.
2. Go to **Project management and accounting** > **Journals** > **Project Operations integration journal** and review the journal lines. The system creates the journal lines for **Inter-organizational sales** and **Resourcing unit cost**.
3. On the **Action pane**, select **Post** to post the integration journal.

Following the completion of the **Project integration journal** posting, the subsequent action entails generating an **Intercompany customer invoice** by the **lending legal entity**, succeeded by the **vendor invoice posting** performed by the **borrowing legal entity**.
Refer **[Create intercompany customer and vendor invoices](https://learn.microsoft.com/en-us/dynamics365/project-operations/project-accounting/create-intercompany-customer-vendor-invoices)**

