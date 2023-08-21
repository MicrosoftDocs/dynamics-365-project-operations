---
title: Block vendor payments until approved by Project manager
description: This article delves into the features present in Microsoft Dynamics 365 Project Operations that facilitate the withholding of vendor payments for vendor invoices until they receive approval from the Project Manager within Dataverse. Situations arise where Project Manager authorization is necessary prior to initiating vendor payment. During these instances, accounts payable clerks document the invoice and  await the Project Manager's approval before proceeding with payment processing.
author: mukumarm
ms.date: 08/17/2023
ms.topic: article
ms.reviewer: johnmichalak 
ms.author: mukumarm
---

# Block vendor payments until approved by Project manager

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To use the functionality that's described in this article, you must enable the feature **Enable Hold Vendor Payment for vendor invoices till PM confirms the invoice for resource based/non-stocked scenarios.** in the Dynamics 365 Finance Feature management workspace.

## Minimum version required

To use this feature for **Microsoft Dynamics 365 Project Operations non-stocked/resource-based scenarios**, the following versions are required:

* **Project Operations Dataverse** version 4.76.0.0 or later.
* **Dynamics 365 Finance** version 10.0.36 or later.

## Run dual-write maps for vendor invoice header

Make sure that the mapping for **Project Operations integration project vendor invoice export entity V2** and **msdyn_projectvendorinvoices** uses version 1.0.0.0 or later.

The following screenshost shows the **Dual write entity map** used for **vendor invoice**. 

![A screenshot of the Dual write maps](../media/BlockvendorPaymentDualWrite.png)

The following screenshot shows the **Dual write** field mapping used for **vendor invoice**.

![A screenshot of the Dual write field mapping](../media/VendorInvoiceDualwritefieldmapping.jpg)

## Set up Subcontract vendor invoice verification and block vendor payments parameters 

1. In Dynamics 365 Finance, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**.
1. Select the **Financial** tab.
1. If vendor invoice verification is required in Dataverse by the Project manager, the **Set Manual verification** field must be set to **Yes**. This action activates the **Block vendor payments till PM confirmation** field.
1. If the vendor payment needs to be blocked untill the Program manager approves the vendor invoice in Dataverse, set **Block vendor payments till PM confirmation** to **Yes**. This field is activated only if **Manual verification by PM is required** is set to **Yes**.

## Create and post subcontract vendor invoices

When an Accounts payable clerk receives an invoice from the subcontractor, a new invoice is created in Dynamics 365 Finance.

1. In **Finance**, go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.
1. On the **Action Pane**, select **New** to create a vendor invoice.
1. On the **Invoice header**, in the **Invoice account** field, select **Subcontractor**.
1. Select the **invoice date**.
1. On the **Header** tab, validate that **Manual verification by PM is required** and **Block vendor payments till PM confirmation** are defaulted from the **Project management and accounting parameters** form. However, it can be changed at vendor invoice level.
1. Set the **Manual verification by PM is required** and **Block vendor payments till PM confirmation** fields to **Yes**.
1. On the **Invoice line** fast tab, select **Add line** to create a **vendor invoice line**.
1. Select the **Procurement category** that was created for the subcontract lines, and enter the **unit price**, **unit of measurement**, and **quantity**.
1. In the **Vendor invoice lines** section, on the **Project** tab, select the project that the subcontractor shares the subcontract invoice against.
1. Select the **Project category**. It can be of any type (Item, Expense, Materials, or Hours). If the selected **project category** is of the **Hour** type, select the role.
1. Select **Post** to post the vendor invoice.

When the vendor invoice is posted, it becomes available in Dataverse for Project manager verification and processing. For verification of vendor invoices in Dataverse, see [Confirm project vendor invoices](confirm-a-project-vendor-invoice.md).

## Enable vendor invoice for payment

When the Project manager confirms the vendor invoice in **Dataverse**, the vendor invoice is approved for **vendor payment**. In certain scenarios if the vendor payment is required even before the Program manager's approval in **Dataverse** then vendor invoice can be approved manually for payment.

1. Go to **Accounts payable** > **Vendors** > **All vendors**.
1. Select the vendor from the list.
1. On the **Action pane**, select **Transactions**.
1. Select the **Vendor transaction** for the vendor invoice.
1. Go to the **General** tab and set the **Approved** field to **Yes**.
