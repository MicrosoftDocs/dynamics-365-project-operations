---
title: Manage project invoice proposals
description: This article provides details about processing customer-facing invoices with Project Operations for resource/ non-stocked based scenarios.
author: sigitac
ms.date: 04/12/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Manage project invoice proposals

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project invoice proposals can be processed by your billing department when the following two conditions are met:

  - The Project manager confirms the proforma invoice in Microsoft Dataverse.
  - All time and material unbilled sales transactions that are included in the proforma invoice are posted using the Dynamics 365 **Project Operations Integration** journal.

Use the following steps to complete a project invoice proposal in Dynamics 365 Finance.

1. Review billing information for time and material transactions and post the **Project Operations Integration** journal.
2. Review billing information for fixed price billing milestones.
3. Review and format a project invoice proposal.
4. Post and print project invoices.

## Manage billing information in the Project Operations Integration journal

Project actuals created in Dataverse are reviewed and posted in Finance by the Project accountant. For more information about working with the Integration journal, see [Integration journal in Project Operations](../project-accounting/project-operations-integration-journal.md).

Cost actuals and unbilled sales actuals are added to the Integration journal as separate lines:

  - The unit cost price and cost amount on the Cost actual default from the project actual cost transaction in Dataverse.
  - The unit sales price and sales amount on the Unbilled sales transaction defaults from the project actual unbilled sales transaction in Dataverse.

### Billing sales tax

Sales tax calculation for billing is determined by the **Billing sales tax group** and **Billing item sales tax group** field combination on an unbilled sales record on the **Project Operations Integration** journal line. The system defaults these field values based on settings on the **Financials** tab on the **Project management and accounting parameters** page.

- **Sales tax group method** determines the billing sales tax group defaulting logic:
  
  - **Project**: Will always default the billing sales tax group from the project. You can review or change the default billing sales tax group on a project by selecting **Show default accounting** on the **All Projects** page.
  - **Project contract**: Will always default the billing sales tax group from the project contract. You can review or change the default sales tax group on a project contract by selecting **Show default accounting** on the **Project contracts** page.
  - **Customer**: Will always default the billing sales tax group from the customer.
  - **Search**: Will search across all the above entities and select the first value available. Search starts with the **Project** entity, then the **Project contract** entity, and finally the **Customer** entity.

- **Item sales tax group method** determines the billing item sales tax group defaulting logic:
  
  - For time, expense, and fee transaction types, the billing item sales tax group will always default from the **Project category** entity.
  - For material transaction types, the billing item sales tax group defaults based on the **Item sales tax group method** setting in **Project management and accounting parameters**. The item number defaults the item sales tax group from the **Released product** entity. The category defaults the item sales tax group from the **Project category** entity.

### Financial dimensions

The financial dimensions for unbilled sales records in the **Project Operations Integration** journal default from the **Project** entity. Financial dimensions can be reviewed and adjusted by selecting **Distribute Amounts**. If you need to change the financial dimensions of the unbilled sales record after the Integration journal is posted but before the Proforma invoice is confirmed, go to **All Projects** > **Manage** > **Posted transactions**, select the transaction, and then select **Process** > **Adjust accounting**.

### Exchange rates

Unbilled transaction currency in Dataverse is used as transaction currency in Finance and converted to company's accounting currency using exchange rates defined in Finance.


## Manage the financial attributes of billing milestones 

Project contract lines using the fixed price billing method are invoiced through [Fixed price milestones](../sales/invoice-schedules-contract-line.md#create-a-fixed-price-invoice-schedule-for-a-contract-line). The Project accountant can review billing milestones in Finance by going to **Project management and accounting** > **All projects** > **Manage** > **On-account transactions**.

### Billing sales tax

The **Sales tax group** and **Item sales tax group**  values default from the settings when a new billing milestone is created in Dataverse. The system defaults the values to these fields based on settings on the **Financial** tab on the **Project management and accounting parameters** page.

- **Sales tax group method** determines the defaulting logic of the **Billing sales tax group**:

    - **Project** will always default the billing sales tax group from the project. You can review or change the default sales tax group on a project by selecting **Show default accounting** on the **All Projects** page.
    - **Project contract** will always default the billing sales tax group from the project contract. You can review or change default sales tax group on a project contract by selecting **Show default accounting** on the **Project contracts** page.
    - **Customer** will always default to the billing sales tax group from the customer.
    - **Search** will search across all the entities in this list and select the first value available. Search starts with the **Project** entity, then the **Project contract** entity, and then the **Customer** entity.

- **Fixed price milestone item sales tax group** is used as the default value in the **Item sales tax group** field for the billing milestone. The accountant can review and modify this value on the **On-account transactions** page. The system uses the value from the on-account transaction when creating a project invoice proposal line.
 

### Financial dimensions

Default financial dimensions for the fixed price billing milestone are set on Project contract lines. Go to **Project contracts** > **Show default accounting** and on the **Contract lines** tab, select **price contract line**, then set the financial dimension values that you want to use as the default.

The Project accountant can edit the sales tax and financial dimensions information on invoice milestones up until the Project invoice proposal is created.


## Create project invoice proposals

Project invoice proposals can be reviewed in the **Project management and accounting** module by going to **Project invoices** > **Project invoice proposals**.

The Project invoice proposal header is created in Finance when the Proforma invoice is confirmed in Dataverse. For easier reconciliation, the system sets the Project invoice proposal number in Finance to the same number as the Proforma invoice ID in Dataverse. Because Proforma invoices are not necessarily confirmed in the same order they are created, the Project invoice proposal number sequence in Finance must allow for changes to lower and higher numbers. Configure number sequences using the following steps:

1. In Finance, go to **Organization Administration** > **Number sequences** > **Number sequences**.
2. In the **Area** filter, select **Projects**.
3. In the **Reference** filter, select **Invoice proposal**.
4. Use the **Company** field to filter each legal entity with Project Operations Dataverse integration enabled.
5. Open **Number Sequence details** and on the **General** tab set:

    - **Allow user changes: To a lower number** = **Yes**
    - **Allow user changes: To a higher number** = **Yes**

Project invoice proposal lines are added by the system using the periodic process **Import from staging table** (**Project management and accounting** > **Periodic** > **Project Operations integration** > **Import from staging table**). This process can be run manually or by using a periodic schedule. The system won't add lines to the invoice proposal document until all the lines are ready to be invoiced. Time and material transactions are ready to be invoiced only when they are posted using the **Project Operations Integration** journal.

## Format and print invoice proposals

The Project accountant can customize a project invoice printout by using the **Format invoice proposal** page and print management capabilities.

### Format invoice proposals

The **Format invoice proposals** page allows custom grouping transactions to display in the customer project invoice.

1. On the **Project invoice proposal** page, select **Print** > **Format invoice proposal**.
2. Select **New** to create a new grouping for the Project invoice printout.
3. In the **Detail/Summary** field, select options for this grouping:

    - Select **Detail** to print the transaction details of the customer invoice.
    - Select **Summary** to print the transaction summary of the customer invoice.

> [!NOTE]
> The selection in the **Detail/Summary** field on the **Format invoice proposal** page overrides the option selected in the **Invoice format** field on the **Invoice proposals** page to print a detailed invoice or a summarized invoice.

- Select the transaction lines to include in this section on the **Available transactions** tab and select **Include transactions** to move them to the **Selected transactions** tab.
- Select **Move up** and **Move down** to change the order of the sections.
- Select **Print preview** to preview formatted invoice.

### Print management

Print management uses different report files to print, specify destinations, and customize footer text for the invoice. Print management can be set up at the module level, however these settings can be overridden for a specific customer, contract, or invoice proposal. To access this function on the **Project invoice proposal** page, select **Print** > **Print management**.

Print management setup is displayed as a tree view, where each node level displays the available documents to adjust. You can assign custom printouts at the module, customer, contract, or invoice proposal document level. To modify the original document printout, expand the desired node and select **Original item**. In the **Report format** field, select the report format to be used for printing. You can use custom report formats by using [Business Document Management framework](/dynamics365/fin-ops-core/dev-itpro/analytics/er-business-document-management).

## Post invoice proposals

After the invoice has been reviewed and edited, and the invoice proposal lines are satisfactory, check the invoice totals and sales tax. In the **Details** group, select **Totals** and then select **Post** to post the invoice.

To view the invoice before posting, clear the **Posting** check box. **Pro forma** will be printed on the invoice to signify it is a sample invoice. To print the invoice, select the **Print invoice** check box.

In addition to the **Invoice proposal** page, invoice proposals can also be posted by running the periodic job, **Post invoice proposals**. To find this job, go to **Project management and accounting** > **Periodic** > **Project invoices** > **Post invoice proposals**.

This page shows all the invoice proposals that are ready for posting. You can schedule posting invoice proposals by selecting **Batch**. Set the **Batch processing parameter** to **Yes** and set the recurrence of batch processing by selecting **Recurrence**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
