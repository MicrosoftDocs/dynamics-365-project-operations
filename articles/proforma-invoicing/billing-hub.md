---
title: Create proforma project invoices with Billing hub
description: This article provides information about how to use Billing hub to create proforma project-based invoices.
author: suvaidya
ms.date: 02/28/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---

# Creating proforma project invoices using Billing hub

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

## Overview
The end-to-end process of invoice creation in Microsoft Dynamics 365 Project Operations involves multiple clicks and navigation between different forms and views making it cumbersome to use. 
**The Billing hub experience** aims to provide a rich, consolidated view of contracts, contract lines, related actuals, and key invoicing insights **prior to invoice creation** to help accountants and billing users create proforma invoices **quickly** and **efficiently**. By using the platform's out-of-the-box nested grid functionality, users can complete invoice creation from a single unified view and with a single click, eliminating the need to navigate between forms or views to validate data , thus leading to faster processing of invoices.

> [!Note]
> To use Billing hub, enable the feature from **Settings > Parameters > Feature control > Billing hub**.
>
> You can customize the **billing hub** forms and views once the feature becomes generally available.

## Create new invoice(s)

To use the Billing hub to create Project proforma invoices, follow these steps.

1. On the left pane, navigate to **Sales** \> **Billing Hub**.
1. The default **Billing hub** view shows the list of active Project contracts and contract lines in a nested grid.

### Update totals on contract and contract line fields

Use **Update Totals** to view latest values on amount fields in Billing hub.

To use **Update totals**, follow these steps.

1. Initially, the amount values may display as zero for the newly created project contracts. 
1. To view the updated values of available amount fields, select the project contract, and the select **Update Totals** on the form ribbon.

### Review or update the invoiceable backlog

The contract lines for each project contract provide a view of all associated actuals for time, expense, material, and fee. The Invoiceable backlog provides a comprehensive list of actuals across all transaction types. Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as ready or not ready to invoice.

To review or update the invoiceable backlog, follow these steps.

1. For a Time and material project contract line with approved time entries, for example, select the **Time** amount field. Alternatively, you can also select **Invoiceable backlog** amount field. A list of invoiceable time transactions specific to that project contract and contract line opens.
1. Select the transactions and update the Billing status by selecting **Ready to invoice** or **Not ready to invoice** from the list of options on the sub grid.
1. On the **Billing hub** form, select **Update Totals**. This updates the **Ready to be invoiced** amount.

The following information is available in the **Billing hub** view. 

### Contract fields 
| Field |Description|
| --- | --- | 
|Name | Name of the Project Contract. |
|Customer | Name of the primary customer on the contract |
|Total Amount| Amount on the contract, also referred to as **contract value**. |
|Ready to be invoiced| Total amount of transactions with **ready to invoice** billing status. |
|Available advances| Total amount of advances available for use against an invoice for the related project contract. |
|Products| Number of product based lines on the contract. |

### Contract line fields
| Field |Description |
| --- | --- | 
|Name| Name of the project contract line. |
|Project | Name of the project associated with the contract line. |
|Billing Method| Billing method on the related project contract line. |
|Milestones| All invoiceable fixed price milestones available for the selected project contract line. |
|Time| Billing backlog for all unbilled sales actuals of transaction type **time** for the selected project contract line. |
|Material| Billing backlog for all unbilled sales actuals of transaction type **material** for the selected project contract line. |
|Expense| Billing backlog for all unbilled sales actuals of transaction type **expense** for the selected project contract line. |
|Fee| Billing backlog for all unbilled sales actuals of transaction type **fee** for the selected project contract line. |
|Invoiceable backlog| Billing backlog that includes all invoiceable transactions for the project contract line. |

> [!Note]
> Billing hub best supports scenarios where only one customer is on the project contract or project contract line. In split billing scenarios, it can still be used, but you may see a **ready to invoice** amount that does not differentiate between the amount split between the different customers included on the project contract or project contract line. For more information about split billing, see [Manage multiple customers on project-based contract lines](/dynamics365/project-operations/sales/manage-multiple-customers-contract-line).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
