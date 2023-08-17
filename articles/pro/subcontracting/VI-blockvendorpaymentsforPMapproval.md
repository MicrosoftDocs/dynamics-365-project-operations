---
title: Vendor invoicing - Block vendor payments until approved by Project manager
description: This topic outlines the functionality within Microsoft Dynamics 365 Project Operations that enables the blocking of vendor payments for vendor invoices until approved by the Project Manager in Dataverse.
author: mukumarm
ms.date: 06/07/2023
ms.topic: article
ms.reviewer: johnmichalak 
ms.author: mukumarm
---

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use the functionality that's described in this article, you must enable the feature **Enable Hold Vendor Payment for vendor invoices till PM confirms the invoice for resource based/non-stocked scenarios.** in the D365 Finance Feature management workspace.

## Minimum version required
The following versions are required to use this feature for **Microsoft Dynamics 365 Project Operations non-stocked/resource-based scenarios**

**Project Operations Dataverse** version 4.41.0.45 or later, **D365 Finance environment** version 10.0.36 or later

## Run dual-write maps for vendor invoice header
Make sure that the mapping for **Project Operations integration project vendor invoice export entity V2** and **msdyn_projectvendorinvoices** uses version 1.0.0.0 or later.

## Set up Subcontract vendor invoice verification and block vendor payments parameters 

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
2. Go to **Financial tab**.
3. If vendor invoice verification is required in Dataverse by the Project Manager, the field **Set Manual verification" must be set to Yes.** This action will activate the **Block vendor payments till PM confirmation** field.
4. Set **Block vendor payments till PM confirmation** to **Yes**, if the vendor payment needs to be blocked till PM approves the vendor invoice in Dataverse. This field is activated only only if **Manual verification by PM is required** is set to **Yes**.

## Create and post subcontract vendor invoices
When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in Dynamics 365 Finance.

1. In **Finance**, go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.
2. On the **Action Pane**, select New to create a **vendor invoice**.
3. On the **Invoice header**, in the Invoice account field, select Subcontractor.
4. Select the **invoice date**.
5. On the Header tab, Validate the **Manual verification by PM is required** and **Block vendor payments till PM confirmation** are defaulted from the **Project management and accounting parameters** form. However, it can be changed at vendor invoice level.
6. Set the field **Manual verification by PM is required** and **Block vendor payments till PM confirmation** to **yes**.
7. On the **Invoice line** FastTab, select **Add line** to create a **vendor invoice line**.
8. Select the **Procurement category** that was created for subcontract lines, and enter the **unit price**, **unit of measurement**, and **quantity**.
9. In the **vendor invoice lines** section, on the **Project tab**, select the project that the subcontractor shares the subcontract invoice against.
10. Select the **Project category**. It can be of any type (Item, Expense, Materials, or Hours). If the selected **project category** is of the Hour type, select the role.
11. Select **Post** to post the vendor invoice.

When the vendor invoice is posted, it becomes available in Dataverse for project manager verification and processing. For verification of vendor invoices in Dataverse see **Confirm project vendor invoices**.

## Enable vendor invoice for payment
When the Project manager confirms the vendor invoice in **Dataverse**, Vendor invoice will be approved for **vendor payment**. In certain scenarios if the vendor payment is required even before the PM approval in **Dataverse** then vendor invoice can be approved manually for payments.
1. Go to **Accounts payable** > **Vendors** > **All vendors**.
2. Select the vendor from the list.
3. On the **Action pane**, select **Transactions**.
4. Select the **Vendor transaction** for vendor invoice.
5. Go to **General** tab and set **Approved** field to **Yes**.
