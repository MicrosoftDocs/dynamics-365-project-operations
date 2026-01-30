---
title: Project operations dual-write integration errors and mitigation
description: This article describes dual-write errors that you might encounter during transaction execution together with strategies for mitigating them.
author: mukumarm
ms.date: 04/02/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Project operations dual-write integration errors and mitigation

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP._

This article describes dual-write errors that you might encounter during transaction execution together with strategies for mitigating them.

## Expense reports

When a user tries to post expense reports in Microsoft Dynamics 365 Finance, dual-write generates the following error and prevents the expense reports from being posted.

(To post expense reports, go to **Expense management** \> **Process expense reports** \> **Post**.)

| Dual-write error | Reason | Mitigation |
|------------------|--------|------------|
| Unable to write data to entity msdyn\_expenses. Writes to ProjExpenseExportEntity failed with the error message Request failed with the status code BadRequest and CDS error code : 0x80040265 response message: Could not resolve project task for export expense. The specified task activity number doesn't uniquely identify the task of the project in the system. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). Activity ID for troubleshooting \{47076787-D238-4689-9C7E-A463E708851A\}. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). | Dual-write triggers this error if the user selects the parent task ID during expense creation. | The user must recall the workflow and select the correct activity ID. |

## Vendor invoice

When a user tries to post vendor invoices in Dynamics 365 Finance, dual-write generates the following errors and prevents the vendor invoices from being posted.

(To post vendor invoices, go to **Accounts payables** \> **Invoices** \> **Pending vendor invoice**.)

| Dual-write error | Reason | Mitigation |
|------------------|--------|------------|
| **Posting** - Unable to write data to entity msdyn\_projectvendorinvoicelines. Unable to lookup uoms with values \{TST\}. Writes to msdyn_projectvendorinvoicelines failed with an error message. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). | Dual-write triggers this error if the unit of measurement (UOM) doesn't exist in Dataverse. | Initiate the **UOM** dual-write job with the initial synchronization. |
| **Posting** - Unable to write data to entity msdyn\_projectvendorinvoicelines.Writes to ProjVendInvoiceLineExportEntity failed with the error message Request failed with status code BadRequest and CDS error code : 0x80040265 response message: Product id is mandatory. Select a product from the catalog. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). Activity ID for troubleshooting \{A3191FDD-43DB-0004-7169-1F232164DA01\}. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). | Dual-write triggers this error if the product that's used on the vendor invoice line doesn't exist in Dataverse. | Initiate the **Products** dual-write job with initial synchronization from Finance to Dataverse. |
| **Posting** - Unable to write data to entity msdyn\_projectvendorinvoicelines. Writes to ProjVendInvoiceLineExportEntity failed with the error message Request failed with status code BadRequest and CDS error code : 0x80040265 response message: The Transaction Category linked to this vendor invoice line is invalid. Please select an Active, Expense Transaction Category. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). Activity ID for troubleshooting \{A3191FDD-43DB-0000-5E4F-1D232164DA01\}. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). | Dual-write triggers this error if the project category that's used on the vendor invoice line doesn't exist in Dataverse. | Transaction categories should be created in Dataverse and synced with Finance. |
| **Posting** - Unable to write data to entity msdyn\_projectvendorinvoices. Unable to lookup accounts with values \{USPM-000022,edbebb23-fe15-4af3-b839-199c7603f322\}. Writes to msdyn\_projectvendorinvoices failed with an error message. For more information on troubleshooting, see [Troubleshoot live synchronization issues](https://go.microsoft.com/fwlink/?linkid=2244045). | Dual-write triggers this error if the vendor or supplier that's used on the vendor invoice line doesn't exist in Dataverse. | Verify that the vendor exists in Dataverse. Initiate the **Vendors** dual-write job with initial synchronization from Finance to Dataverse. |

## Timesheet confirmation

When a user tries to confirm timesheets in Dataverse, dual-write generates the following error and prevents the timesheets from being confirmed.

(To confirm timesheets, go to **Approve Time Entry** \> **Create Journal Line Entry** \> **Auto Create Actuals**.)

| Dual-write error | Reason | Mitigation |
|------------------|--------|------------|
| Write failed for entity Project Operations integration actuals with unknown exception - Line property Not available doesn't exist. \nvalidateWrite failed on data source 'ProjCDSActualsImport (ProjCDSActualsImport)'. Please rectify your data and try again. If issue persists after multiple retries, please contact your system administrator. | Dual-write triggers this error if a line property doesn't exist in Finance. | Configure the line properties in Finance.|

[!INCLUDE[footer-include](../includes/footer-banner.md)]
