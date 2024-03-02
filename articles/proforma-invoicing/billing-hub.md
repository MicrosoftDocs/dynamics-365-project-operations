---
title: Billing hub for generating proforma invoices
description: This article provides information about billing hub for the creation of proforma project-based invoices.
author: suvaidya
ms.date: 02/28/2024
ms.topic: article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: suvaidya
---
# Proforma Invoicing Reimagined
_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

The end to end process of invoice creation in Project Operations involves multiple clicks and navigation between different forms and views. 
The Billing hub experience aims to provide a rich consolidated view of contracts, contract lines, related actuals and key invoicing insights **prior to invoice creation** thereby helping accountants and billing users to create proforma invoices quickly and efficiently. By leveraging the platform's out of box nested grid functionality, the experience enables users to complete invoice creation from a single unified view, eliminating the need to navigate between forms or views to help validate all information in a single click leading to faster invoice processing.

> [!Note]
> To use Billing hub, enable the feature from **Settings > Parameters > Feature control > Billing hub**.


## Using the Billing Hub to create Project proforma invoices
1. Navigate to **Sales** area --> **Billing Hub** on the left pane.
2. The default **Billing hub** view shows the list of active Project contracts and contract lines in a nested grid.

### Update Totals 
Use **Update Totals** to view latest values on amount fields in Billing Hub
1. Initially , amount values may display as "0" for newly created project contracts. 
2. Select the project contract and click on **Update Totals** on the form ribbon to view the updated values of available amount fields.

### Review or update the invoiceable backlog
The contract lines for each project contract provide a view of all associated actuals for time, expense, material and fee.  The Invoiceable backlog provides a comprehensive list of actuals across all transaction types.  Use the hyperlinks to drill down into each category of invoiceable transactions and mark them as ready or not ready to invoice.
1.  For Example, for a Time and material project contract line with approved time entries, click on the **Time** amount field. Alternatively, you can also select **Invoiceable backlog** amount field.
2.  This opens up the list of invoiceable time transactions specific to that project contract and contract line.
3.  Select the transactions and update the Billing status by selecting **Ready to invoice** or **Not ready to invoice** from the list of options on the sub grid.
5.  On the **Billing hub** form, select **Update Totals**. This should update the **Ready to be invoiced** amount.


The following information is available in the **Billing hub** view 

### Contract fields 
| Field |Description|
| --- | --- | 
|Name | Name of the Project Contract |
|Customer | Name of the contract customer|
|Total Amount| Amount on the contract , also referred to as **contract value** |
|Ready to be invoiced| Total amount of transactions with **ready to invoice** billing status|
|Available advances| Total amount of advances available for use against an invoice for the related project contract|
|Products| Number of product based lines on the contract |

### Contract line fields
| Field |Description |
| --- | --- | 
|Name| Name of the project contract line|
|Project | Name of the project associated with the contract line |
|Billing Method| Billing method on the related project contract line |
|Milestones| All invoiceable fixed price milestones available for the selected project contract line |
|Time| Billing backlog for all unbilled sales actuals of transaction type **time** for the selected project contract line |
|Material| Billing backlog for all unbilled sales actuals of transaction type **material** for the selected project contract line |
|Expense| Billing backlog for all unbilled sales actuals of transaction type **expense** for the selected project contract line |
|Fee| Billing backlog for all unbilled sales actuals of transaction type **fee** for the selected project contract line|
|Invoiceable backlog| Billing backlog that includes all invocieable transactions for the project contract line|

> [!Note]
> Billing hub best supports scenarios where only one customer is on the project contract or project contract line. In split billing scenarios, it can still be used, but users may see a **ready to invoice** amount that does not differentiate between the amount split between the different customers included on the project contract or project contract line. To learn more about split billing , refer https://learn.microsoft.com/en-us/dynamics365/project-operations/sales/manage-multiple-customers-contract-line 
