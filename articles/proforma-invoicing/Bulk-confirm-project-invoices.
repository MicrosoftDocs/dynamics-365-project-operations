---
title: Bulk confirm proforma project-based invoices
description: This article provides information about bulk confirming proforma project-based invoices. 
author: suvaidya
ms.date: 01/20/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Bulk confirm a proforma project-based invoice

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

**Bulk confirm Proforma Project invoices**

With this feature, users will be able to multi-select project invoices and use the confirm action on the ribbon to confirm all the selected invoices. 
To use this feature, admins must enable it under Parameters--> Organization unit-->Feature control -->Enable bulk confirm. 

On "Confirm", all selected invoices that meet the invoice validation criteria, will be scheduled by a batch job to be processed asynchronously. 
Users can track the progress on an invoice using the **Bulk confirmation status" field which reflects the current state of each invoice being processed. 
The values for this field include-  blank (default), scheduled, processing, complete and failed. 

Note: The "Project invoice status" reflects the state of each invoice confirmed individually.  The "Bulk confirmation status" reflects the state of each invoice when confirmed in bulk.
If the invoice has been scheduled using bulk confirmation, the "Project invoice status" field will be "Draft" , and the "Bulk confirmation status" will reflect the processing stage of the invoice.
If the invoice was bulk confirmed, then both the **project invoice status** and the "Bulk confirmation status" will be "confirmed" . 

## Error Handling
Users can confirm upto 250 invoices at a single point in time. 
On Bulk confirmation, invalid invoices, invoices with a bulk confirmation status of "processing"  or "complete" will be skipped from further processing. 
Failed invoices can be tracked using the bulk confirmation status "failed" . Users can navigate to the details tab--> timeline to view the failure details on each invoice.
