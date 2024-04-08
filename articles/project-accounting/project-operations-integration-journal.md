---
title: Integration journal in Project Operations
description: This article provides information about working with the Integration journal in Project Operations.
author: sigitac
ms.date: 04/2/2024
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Integration journal in Project Operations

_**Applies To:** Project Operations for resource/non-stocked based scenarios._

Time, expense, fee, and material entries create **Actual** transactions, which represent the operational view of work completed against a project. Dynamics 365 Project Operations provides accountants with a tool to review transactions and adjust the accounting attributes as needed. After the review and adjustments are complete, the transactions are posted to the Project subledger and General ledger. An accountant can perform these activities using the **Project Operations Integration** journal (**Dynamics 365 Finance** > **Project management and accounting** > **Journals** > **Project Operations Integration** journal.

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
  - The **Date** field represents the date of the transaction. The **Accounting date** field represents the date that the transaction is recorded to the ledger. If the accounting date is in a [closed financial period](/dynamics365/finance/general-ledger/close-general-ledger-at-period-end), and the parameter **Automatically set accounting date to open ledger period** is set on the **Financial** tab of the **Project management and accounting parameters** page, the system adjusts the accounting date of the transaction to the first date in next open ledger period.
  - The **Voucher** field shows the voucher number for every actual transaction. The voucher number sequence is defined on the **Number sequences** tab, on the **Project management and accounting parameters** page. Each line is assigned a new number. After the voucher is posted, you can view how cost and unbilled sales transaction are related by selecting **Related vouchers** on the **Voucher transaction** page.
  - The **Category** field represents a project transaction and defaults based on the transaction category for the related project actual.
    - If **Transaction category** is set in the Project actual and a related **Project category** exists in a given legal entity, the category defaults to this project category.
    - If **Transaction category** isn't set in the Project actual, the system uses the value in the **Project category defaults** field on the **Project Operations on Dynamics 365 Customer Engagement** tab on the **Project management and accounting parameters** page.
  - The **Resource** field represents the project resource related to this transaction. The resource is used as a reference in Project invoice proposals to customers.
  - The **Exchange rate** field defaults from **Currency exchange rate** set in Dynamics 365 Finance. If the exchange rate setup is missing, the **Import from staging** periodic process won't add the record to a journal, and an error message is added to the job execution log.
  - The **Line property** field represents the billing type in Project actuals. Line property and billing type mapping are defined on the **Project Operations on Dynamics 365 Customer Engagement** tab on the **Project management and accounting parameters** page.

Only the following accounting attributes can be updated in the Project Operations integration journal lines:

- **Billing sales tax group** and **Billing item sales tax group**
- **Financial dimensions** (using the **Distribute amounts** action)

Integration journal lines can be deleted. However, any unposted lines will be inserted into the journal again after you rerun the **Import from staging** periodic process.

### Post the Project Operations integration journal

When you post the Integration journal, a project subledger and general ledger transactions are created. These are used in downstream customer invoicing, revenue recognition, and financial reporting.

The selected Project Operations integration journal can be posted by using **Post** on the Project Operations integration journal page. All journals can be automatically posted by running a process at **Periodics** > **Project Operations integration** > **Post Project Operations integration journal**.

Posting can be performed interactively or in a batch. All journals that have more than 100 lines will automatically be posted in a batch. For better performance when journals that have many lines are posted in a batch, enable the **Post Project Operations integration journal using multiple batch tasks** feature in the **Feature management** workspace. 
#### Transfer all lines that have posting errors to a new journal

> [!NOTE]
> To use this capability, enable the **Transfer all lines with posting errors to a new Project Operations integration journal** feature in the **Feature management** workspace.

This feature helps improve the experience with the Project Operations integration journal. When it's enabled, dual-write timing issues and setup issues no longer prevent valid journals from being posted. During posting to the Project Operations integration journal, the system validates every line in the journal. It posts all lines that have no errors and creates a new journal for all lines that have posting errors.

To review the journals that have posting error lines, go to **Project management and accounting** \> **Journals** \> **Project Operations integration journal**, and filter the list of journals by using the **Original journal** field. The following illustration shows an example where the journals on the **Project Operations integration journal** page have been filtered in this way.

![Original journal shown on the Project Operations integration journal page.](./media/transferLines-originalJournal.png)

If a periodic batch job is configured to post the integration journal, posting is reattempted, and the journals are posted if the timing issue has been fixed. Any remaining journals should be manually investigated by reviewing the logs and taking any required action.

#### Working with integration journal lines with warnings and errors

If there are configuration issues or other problems that are found during posting, the system logs a warning or error to describe the issue and leaves the transaction in the integration journal to be posted later.

The **Enable integration journal processing improvements** feature is available in 10.0.37, and is recommended for all customers. This feature prevents a race condition error and prevents the system from trying to continually post integration journals that fail until the configuration issue is resolved.

With this feature enabled, new statuses are visible within the integration journal line to control posting. This feature also optimizes posting to ensure work can be split up into multiple threads. This feature depends on the **Transfer all lines with posting errors to a new journal** feature, and we recommend the **Post Project Operations Integration journal using multiple batch tasks** feature to be enabled. 

This feature introduces an enhanced process where posting transactions is attempted and any lines without errors post successfully. If any errors are encountered, that subset of transactions are moved to a new integration journal with the header and lines with status of **error**. The transactions with the error won't attempt to post again until the underlying issue is fixed, the header is updated, and line is set back to draft status. Common examples of underlying issues could be a closed financial period or an incorrect financial dimension not valid for the account structure. Once the underlying issue is fixed, the user can mark it as ready to process again using the **Update to draft** button on the integration journal line or in the integration journal header. 

| Line Status | Description | Error can be resolved by end user |
|--- | --- | ---|
| Draft | The line is in draft status as it existed prior to the new integration journal processing improvement feature being enabled. The line can be posted. | |
| Error | One or more integration journal lines have an error and the header can't be posted. | **Reset to draft** can be performed. |
| Processing | The line is in the processing status and moves to posted status soon. If a line is listed in processing status for a long time, it's likely that an error has occurred and a user can manually reset the line to draft status. | **Reset to draft** can be performed. | 
| Posted | The line has been successfully posted and no further action is required.| |
| Unrecoverable | The line has an error that can't be posted by the system. A support ticket may be necessary in this case. This error should only occur for transactions that existed prior to the feature being enabled. | |
| Invalid actuals | The line has an error that can't be posted due to missing **Actuals** within Dataverse. A support ticket may be necessary in this case.| 

|Header Status | Description | Error can be resolved by end user|
|--- | --- | ---|
|Draft | The header is in draft status as it hasn't been posted yet.| |
| Processing | The header is in the processing status and moves to posted status soon. | **Reset to draft** can be performed. |
| Posted | The header has been successfully posted and no further action is required. | |
| Error | One or more integration journal lines have an error and the header can't be posted. A user can manually reset the header to draft status to try posting again. | **Reset to draft** can be performed. |

##### Transactions in processing state

It's possible that integration journal lines can be left in processing state for an extended period of time and need to be reset. If transactions are listed as pending status and 24 hours have passed or an administrator has verified there are no running interactive or batch posting processes for the integration journal, the status likely wasn't updated correctly. Users can manually reset the status back to draft by clicking **Update to draft** in the integration journal line. 

##### Further improvements have been made in this area in the 10.0.38 release. Improvements include:

- Other functionality is available to multiselect rows when working with integration headers.
- More flexibility in controlling posting with a new optional parameter to **Limit the integration journal lines per header**. With the parameter disabled, a default of 200 lines is used. The parameter can be increased or decreased as needed. Decreasing the parameter reduces the time taken to post the journal.
- The **Add filters to the Project Integration journal posting batch job** feature adds default filters to allow users to specify a period start date, a journal number, or an original journal number in the batch job filter. These filters are useful when you have transactions that require some setup or configuration changes before they can be posted and you can avoid trying to post until the issue is resolved.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
