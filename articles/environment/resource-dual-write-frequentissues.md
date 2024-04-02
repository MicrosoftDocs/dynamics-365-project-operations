---
title: Project operations dual write errors and mitigation
description: This article offers insights into dual-write errors encountered during transaction execution, along with strategies for mitigating them. 
author: mukumarm
ms.date: 04/02/2021
ms.topic: how-to
ms.custom: 
  - bap-template
ms.prod:
ms.reviewer: johnmichalak
ms.author: mukumarm
---
# Project operations dual write integration errors and mitigation

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

This article offers insights into dual-write errors encountered during transaction execution, along with strategies for mitigating them.

# Expense reports
When attempting to post expense reports in Dynamics 365 Finance, Dual write generates the following error and prevents the posting of the expense report.

**Expense management** > **Process expense reports** > **Post**

| Dual write error | Reason | Mitigation |
| ------------- | ------------- |  ------------- |
| Unable to write data to entity msdyn_expenses.Writes to ProjExpenseExportEntity failed with error message Request failed with status code BadRequest and CDS error code : 0x80040265 response message: Could not resolve project task for export expense. The specified task activity number doesn't uniquely identify task of the project in the system..For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045. Activity ID for troubleshooting {47076787-D238-4689-9C7E-A463E708851A}For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045..  | Dual write triggers this error when the user selects the parent task ID during expense creation. | User needs to recall the workflow and select the correct activity id.

# Vendor invoice
When attempting to post vendor invoices in Dynamics 365 Finance, Dual write generates the following error and prevents the posting of the vendor invoices.

**Accounts payables** > **Invoices** > **Pending vendor invoice**

| Dual write error | Reason | Mitigation |
| ------------- | ------------- |  ------------- |
| Posting - Unable to write data to entity msdyn_projectvendorinvoicelines.Unable to lookup uoms with values {TST}.Writes to msdyn_projectvendorinvoicelines failed with error message For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045. | Dual write triggers this error when the unit of measurement (UOM) does not exists in Dataverse. |  Initiate the **UOM** Dual write job with initial sync|
| Posting - Unable to write data to entity msdyn_projectvendorinvoicelines.Writes to ProjVendInvoiceLineExportEntity failed with error message Request failed with status code BadRequest and CDS error code : 0x80040265 response message: Product id is mandatory. Select a product from the catalog..For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045. Activity ID for troubleshooting {A3191FDD-43DB-0004-7169-1F232164DA01}For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045.. | Dual write triggers this error when the Product used in the vendor invoice line does not exists in Dataverse. |  Initiate the Products dual write job with initial sync from Dynamics 365 Finance to Dataverse|
| Posting - Unable to write data to entity msdyn_projectvendorinvoicelines.Writes to ProjVendInvoiceLineExportEntity failed with error message Request failed with status code BadRequest and CDS error code : 0x80040265 response message: The Transaction Category linked to this vendor invoice line is invalid. Please select an Active, Expense Transaction Category..For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045. Activity ID for troubleshooting {A3191FDD-43DB-0000-5E4F-1D232164DA01}For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045.. | Dual write triggers this error when the Project cateogory used in the vendor invoice line does not exists in Dataverse. |  Transaction categories should be created in Dataverse and Synchronized with Dynamics 365 Finance  |
|Posting - Unable to write data to entity msdyn_projectvendorinvoices.Unable to lookup accounts with values {USPM-000022,edbebb23-fe15-4af3-b839-199c7603f322}.Writes to msdyn_projectvendorinvoices failed with error message For information on troubleshooting see https://go.microsoft.com/fwlink/?linkid=2244045.. | Dual write triggers this error when the vendor or supplier used in the vendor invoice line does not exists in Dataverse. |  Verify that the vendor should exists in Dataverse. Initiate the Vendors dual write job with initial sync from Dynamics 365 Finance to Dataverse |

# Timesheet confirmation
When attempting to confirm the timesheets in Dataverse , Dual write generates the following error and prevents the timesheet confirmation.

**Approve Time Entry** > **Create Journal Line Entry** > **Auto Create Actuals**

| Dual write error | Reason | Mitigation |
| ------------- | ------------- |  ------------- |
|  {"Write failed for entity Project Operations integration actuals with unknown exception - Line property Not available does not exist.\nvalidateWrite failed on data source 'ProjCDSActualsImport (ProjCDSActualsImport)'"}
 Please rectify your data and try again. If issue persists after multiple retries, please contact your system administrator.| Dual write triggers the error when line property does not exists in D365 Finance |  Configure the line properties in D365 Finance.|

