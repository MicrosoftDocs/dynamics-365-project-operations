---
title: Adding new invoice line details to a draft invoice
description: This article provides information about how to add new invoice line details to an existing proforma project-based invoice in draft status.
author: suvaidya
ms.date: 02/10/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Add new invoice line details to a draft invoice

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

The ability to create transactions for time, expense, and material usage directly on a draft invoice streamlines the process of invoicing to help ensure timely and accurate billing. This enhances operational efficiency and accelerates cash flow, providing significant financial and administrative benefits to project-oriented companies.

> [!NOTE]
>The capability to add new Invoice line details to an invoice is already available on lite deployment of Project Operations. This enhancement extends this capability to integrated deployments as well. 

## How to manually add new invoice line details to a draft proforma invoice
1. Select the +New Button to create an invoice line detail with transaction class of type time, expense, material or fee.
2. Doing so will open the invoice line detail form with the ability to edit price, quantity, billing type, external description and description. 
3. Update the invoice line detail with the details and save.

## Impact of manually added invoice line details on actuals 

For each invoice line detail added for project(s) mapping to a Time and material contract line. 
Billing action - Invoice confirmation, Invoice Revision,  Deletion of Invoice line detail.
The following table lists the actuals that are created when a corrective invoice is confirmed.

<table border="0" cellspacing="0" cellpadding="0">
    <tbody>
        <tr>
            <td width="216" valign="top">
                <p>
                    <strong>Scenario</strong>
                </p>
            </td>
            <td width="808" valign="top">
                <p>
                    <strong>Actuals created on confirmation</strong>
                </p>
            </td>
        </tr>
        <tr>
            <td width="216" rowspan="2" valign="top">
                <p>
                    Invoicing the full credit of a previously invoiced time
                    transaction.
                </p>
            </td>
            <td width="408" valign="top">
                <p>
                    A billed sales reversal for the hours and amount on the
                    original invoice line detail for time.
                </p>
            </td>
        </tr>
        <tr>
            <td width="408" valign="top">
                <p>
                    A new unbilled sales actual for the hours and amount on the
                    original invoice line detail for time.
                </p>
            </td>
        </tr>



### Enabling the feature on integrated deployments
The feature can be enabled in Parameters-- settings-- feature control.  Once enabled the feature cannot be disabled.
