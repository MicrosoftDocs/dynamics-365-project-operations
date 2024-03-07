---
title: Integration journal in Project Operations
description: This article provides information about working with the Integration journal in Project Operations.
author: sigitac
ms.date: 09/22/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Integration journal in Project Operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Time, expense, fee, and material entries create **Actual** transactions which represent the operational view of work completed against a project. Dynamics 365 Project Operations provides accountants with a tool to review transactions and adjust the accounting attributes as needed. After the review and adjustments are complete, the transactions are posted to the Project subledger and General ledger. An accountant can perform these activities using the **Project Operations Integration** journal (**Dynamics 365 Finance** > **Project management and accounting** > **Journals** > **Project Operations Integration** journal.

![Integration journal flow.](./media/IntegrationJournal.png)

### Create records in the Project Operations Integration journal

Records in the Project Operations Integration journal are created using periodic process, **Import from staging table**. You can run this process by going to **Dynamics 365 Finance** > **Project management and accounting** > **Periodic** > **Project Operations Integration** > **Import from staging table**. You can run the process interactively or configure the process to run in the background as needed.

When the periodic process runs, any actuals that aren't yet added to the Project Operations Integration journal are found. A journal line for each actual transaction is created.
The system groups journal lines into separate journals based on the value selected in the **Period unit on Project Operations Integration journal** field (**Finance** > **Project management and accounting** > **Setup** > **Project management and accounting parameters**, **Project Operations on Dynamics 365 Customer Engagement** tab). Possible values for this field include:

  - **Days**: Actuals are grouped by transaction date. A separate journal is created for each day.
  - **Months**: Actuals are grouped by calendar month. A separate journal is created for each month.
  - **Years**: Actuals are grouped by calendar year. A separate journal is created for each year.
  - **All**: All actual transactions are included in the same integration journal. If the journal isn't available when the periodic process runs, for example if the journal is in the process of posting transactions, a new journal is created.

Journal lines are created based on project actuals. The following list includes some of the more notable default and transformation rules:

  - Each project actual transaction has a line in the Project Operations Integration journal. Cost and unbilled sales transactions for time and material billing type are shown on separate lines.
  - The **Date** field represents the date of the transaction. The **Accounting date** field represents the date that the transaction is recorded to the ledger. If the accounting date is in a [closed financial period](/dynamics365/finance/general-ledger/close-general-ledger-at-period-end), and the parameter **Automatically set accounting date to open ledger period** is set on the **Financial** tab of the **Project management and accounting parameters** page, the system will adjust the accounting date of the transaction to the first date in next open ledger period.
  - The **Voucher** field shows the voucher number for every actual transaction. The voucher number sequence is defined on the **Number sequences** tab, on the **Project management and accounting parameters** page. Each line is assigned a new number. After the voucher is posted, you can view how cost and unbilled sales transaction are related by selecting **Related vouchers** on the **Voucher transaction** page.
  - The **Category** field represents a project transaction and defaults based on the transaction category for the related project actual.
    - If **Transaction category** is set in the Project actual and a related **Project category** exists in a given legal entity, the category defaults to this project category.
    - If **Transaction category** isn't set in the Project actual, the system uses the value in the **Project category defaults** field on the **Project Operations on Dynamics 365 Customer Engagement** tab on the **Project management and accounting parameters** page.
  - The **Resource** field represents the project resource related to this transaction. The resource is used as a reference in Project invoice proposals to customers.
  - The **Exchange rate** field defaults from **Currency exchange rate** set in Dynamics 365 Finance. If the exchange rate setup is missing, the **Import from staging** periodic process won't add the record to a journal and an error message will be added to the job execution log.
  - The **Line property** field represents the billing type in Project actuals. Line property and billing type mapping are defined on the **Project Operations on Dynamics 365 Customer Engagement** tab on the **Project management and accounting parameters** page.

Only the following accounting attributes can be updated in the Project Operations integration journal lines:

- **Billing sales tax group** and **Billing item sales tax group**
- **Financial dimensions** (using the **Distribute amounts** action)

Integration journal lines can be deleted. However, any unposted lines will be inserted into the journal again after you rerun the **Import from staging** periodic process.

### Post the Project Operations integration journal

When you post the Integration journal, a project subledger and general ledger transactions are created. These are used in downstream customer invoicing, revenue recognition, and financial reporting.

The selected Project Operations integration journal can be posted by using **Post** on the Project Operations integration journal page. All journals can be automatically posted by running a process at **Periodics** > **Project Operations integration** > **Post Project Operations integration journal**.

Posting can be performed interactively or in a batch. Note that all journals that have more than 100 lines will automatically be posted in a batch. For better performance when journals that have many lines are posted in a batch, enable the **Post Project Operations integration journal using multiple batch tasks** feature in the **Feature management** workspace. 

#### Transfer all lines that have posting errors to a new journal

> [!NOTE]
> To use this capability, enable the **Transfer all lines with posting errors to a new Project Operations integration journal** feature in the **Feature management** workspace.

This feature helps improve the experience with the Project Operations integration journal. When it's enabled, dual-write timing issues and setup issues no longer prevent valid journals from being posted. During posting to the Project Operations integration journal, the system validates every line in the journal. It posts all lines that have no errors and creates a new journal for all lines that have posting errors.

To review the journals that have posting error lines, go to **Project management and accounting** \> **Journals** \> **Project Operations integration journal**, and filter the list of journals by using the **Original journal** field. The following illustration shows an example where the journals on the **Project Operations integration journal** page have been filtered in this way.

![Original journal shown on the Project Operations integration journal page.](./media/transferLines-originalJournal.png)

If a periodic batch job is configured to post the integration journal, posting will be reattempted, and the journals will be posted if the timing issue has been fixed. Any remaining journals should be manually investigated by reviewing the logs and taking any required action.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
