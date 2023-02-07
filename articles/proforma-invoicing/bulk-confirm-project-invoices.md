---
title: Bulk-confirm proforma project-based invoices
description: This article provides information about bulk confirmation of proforma project-based invoices.
author: suvaidya
ms.date: 01/20/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Bulk-confirm proforma project-based invoices

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

This feature lets users select multiple project invoices and then use the **Confirm** button on the toolbar to confirm all of them at the same time. To use this feature, enable it at **Parameters \> Organization unit \> Feature control \> Enable bulk confirm**. 

After you select **Confirm**, all selected invoices that meet the invoice validation criteria are scheduled by a batch job for asynchronous processing.

The **Project invoice status** field reflects the current status of each invoice that's confirmed individually. The **Bulk confirmation status** field reflects the status of each invoice that's confirmed in bulk. This field has one of the following values: blank, **Scheduled**, **Processing**, **Complete**, or **Failed**. A blank status indicates that no bulk confirmation action was performed on the invoice.

When an invoice is scheduled by using bulk confirmation, the **Project invoice status** value will be **Draft**, and the **Bulk confirmation status** value will reflect the processing stage of the invoice. After the invoice is confirmed, the **Project invoice status** value will be **Confirmed**, and the **Bulk confirmation status** value will be **Complete**.

> [!NOTE]
> Users can bulk-confirm up to 250 invoices at a time.
>
> Failed invoices can be tracked by using the **Failed** bulk confirmation status. Users can go to the timeline on the **Details** tab to view the failure details for each invoice.
