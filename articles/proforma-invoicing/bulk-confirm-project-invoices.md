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

On **confirm**, all selected invoices that meet the invoice validation criteria, are scheduled by a batch job to be processed asynchronously. The **Bulk confirmation status** field which reflects the current state of each invoice being processed, allows users to track the confirmation status of an invoice.
The values for this field include-  blank , scheduled, processing, complete and failed. 

The **Project invoice status** reflects the state of each invoice confirmed individually.  The **Bulk confirmation status** reflects the state of each invoice when confirmed in bulk.

When an invoice is scheduled using bulk confirmation, the **Project invoice status** will be **draft** , and the **Bulk confirmation status** will reflect the processing stage of the invoice.  Once the invoice is confirmed, the **Project invoice status** will be "confirmed" and the **Bulk confirmation status** will be **complete**. 

[Note:]
Users can bulk-confirm upto **250** invoices at a single point in time. 
Failed invoices can be tracked using the bulk confirmation status **failed**. Users can navigate to the timeline under details tab to view the failure details on each invoice.
