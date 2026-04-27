---
title: Bulk-confirm proforma project invoices
description: This article provides information about bulk confirmation of proforma project-based invoices.
author: suvaidya
ms.date: 09/24/2025
ms.topic: concept-article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Bulk-confirm proforma project invoices

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

After you select **Confirm**, all selected invoices that meet the invoice validation criteria are scheduled by a batch job for asynchronous processing.

The **Project invoice status** field reflects the current status of each invoice that's confirmed individually. The **Bulk confirmation status** field reflects the status of each invoice that's confirmed in bulk. This field has one of the following values: blank, **Scheduled**, **Processing**, **Complete**, or **Failed**. A blank status indicates that no bulk confirmation action was performed on the invoice.

When an invoice is scheduled by using bulk confirmation, the **Project invoice status** value will be **Draft**, and the **Bulk confirmation status** value will reflect the processing stage of the invoice. After the invoice is confirmed, the **Project invoice status** value will be **Confirmed**, and the **Bulk confirmation status** value will be **Complete**.

> [!NOTE]
> Users can bulk-confirm up to 250 invoices at a time and configure [notifications upon completion of invoice confirmation](../proforma-invoicing/long-running-jobs.md)
>
> Failed invoices can be tracked by using the **Failed** bulk confirmation status. Users can go to the timeline on the **Details** tab to view the failure details for each invoice.
