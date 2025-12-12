---
title: Use general journals for advanced accounting
description: Learn more about using general journals and record various financial transactions directly into the general ledger.
author: ryansandness
ms.author: ryansandness
ms.date: 12/11/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Use general journals for advanced accounting

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

General journals are the all-purpose accounting feature in Microsoft Dynamics 365 Finance. This document allows recording of various financial transactions directly into the general ledger (GL). Common uses include daily accounting entries, adjustments, and integrations from external systems.

## 10.0.46 Feature Enhancements

This feature is now generally available (GA) starting with the 10.0.46 release. Enhancements in the GA include:

- Increased journal line limit increased to 200 lines from 50 lines. Journals larger than 200 lines will error on posting that "A maximum of 200 project-based lines are supported" and ask the user to reduce the number of lines.
- Introduced asynchronous processing in transferring the journals to Dataverse.
  - There is a new process automation named **Project Operations create and confirm Dataverse journals** that is configured with a 5 minute interval to transfer the journal lines to Dataverse, and to send the confirmation in Dataverse when the journal is transferred and ready to confirm.
- The Project Operations Integration workspace is used for tracking any transient communication errors with Dataverse after the first attempt to confirm in Dataverse fails. A new tab for General journal Dataverse sync has been added.
  - After five attempts, any further retries require manual intervention from the user to click **Sync** to resume retrying the sync and confirmation.
- The Dataverse journal will be read-only to users during processing and prevent users from changing or confirming the integrated journal.

## 10.0.45 Preview

In the 10.0.45 release, a new preview feature is available that enables the ability to create general journals against a project originating in Dataverse. This feature is enabled from the **Feature management** workspace and is named **Enable general journal entries for modern projects**. This feature lets you specify the ledger offset account on the journal. Manual control of the offset enables you to have complete control of the accounting behind the expense. In addition, the journal framework provides many advanced capabilities such as workflow and approvals.

## Entering transactions

When you enter journals, a user typically enters a single line transaction with the Project on the left side for the account type, and the Ledger on the right side as the offset account type. Entering the project details before the offset creates a new expense against the project. Reversing the order creates a credit for the project.

An alternate way of entering journals is to create a project line with the debit but no offset, and create a second line for the same voucher with a ledger credit.

When project is specified for the journal, a new **Project** tab becomes available.

An amount can be entered into the debit or credit column to determine the cost price for the journal. A **Description** is optional and flows through to Dataverse onto the customer invoice. Currency for cost can be modified from the defaulted company currency. Once the account, offset, and price are entered, you can select the **Project** tab to complete the remaining required details.

On the **Project** tab, the fields to consider when creating an entry include:

- **Contract line ID** maps to the Dataverse contract line that allows expense entries or was selected based on task-based billing for the activity number. If the combination of project, category, and task aren't valid for any contract line, the "**There's no contract that exists for this project**" message displays.
- **Activity number** maps to task name for project tasks and is optional.
- **Category** determines which posting account to use for the expense, and defaults the line property value. The category defaults based on the Project management and accounting parameter for the expense category within project category defaults.
- **Quantity** can be defined.
- **Cost price** defaults to what you entered on the general tab earlier.
- **Sales price** always defaults to zero. You always need to define a sales price if necessary.
- **Sales currency** is locked to the contract currency.

General journals aren't aware of Dataverse pricing. The journals allow manual entry of costs and sales. You may see the warning "**Sales price not specified for time and material projects.**"

When the transaction posts, cost commits immediately to general ledger and the project subledger. This process doesn't use the expense integration account and instead, unlike expense reports, posts immediately. A connection is made to Dataverse using the **IOrganization** service, and creates a journal header and journal lines for each cost and sales amount in general journal. 

For example, there might be one project expense journal line for 100 cost and 200 sales. This single journal line with cost and sales ends up in Dataverse as two journal lines, with one line being 100 cost and one line being 200 sales. For time and material contract lines, a corresponding cost and sales line is always created even when sales price is zero. For time and material contract lines or projects without contracts, only a cost line is created. The journal is automatically posted in Dataverse.

The general journal has a journal batch number to uniquely identify it. For example, USPM-000095. This same voucher number carries through to the Dataverse journal header **Description**.

Actuals are created in Dataverse, but only unbilled sales lines are generated in the integration journal. Cost lines were already posted in Finance and were synced to Dataverse, but they don't come back through the integration journal. Once the import from staging completes, the sales line is imported and posted to complete the transaction in Finance.

## OneVoucher transactions for allocations

An alternate method to entering journals is possible by enabling [One voucher](/dynamics365/finance/general-ledger/one-voucher). These transactions can have negative impacts on reporting and should be thoroughly tested before enabling. These types of transactions allow for allocations or apportionment. For example, Contoso might want to purchase a piece of equipment for use for their organization. They have an expense for the equipment but want to charge back 10% of it to each of 10 individual projects. Entering transactions in this way with several lines with different projects allows for a single voucher entry to be posted against multiple projects at the same time.

## Limitations

- Using a cost currency that's different from the project currency requires the UR60 release of Project Operations. Without this update installed, the currency may be posted differently in the Dataverse journal from what was posted in the PMA journal.
- Journals are limited to 200 project-related lines in the client. Previously this limitation was at 50 lines as of 10.0.45. We still generally recommend using smaller journals to post if possible for optimal performance of synchronization and availibility in Dataverse, like during period end close.
- Contract lines with multiple customers aren't considered. These sales lines might not generate unbilled sales correctly without the contract customer defined on the Dataverse journal line.
- Both modern projects and Project Management and Accounting (PMA) projects can't be used in the same journal when customers have previous projects and are [transitioning to using the modern architecture.](../prod-pma/move-to-modern-architecture.md)
- If posting multiple journals concurrently, we recommend to avoid using the same projects in multiple journals when possible and limit journal size to avoid table locking on Dataverse entities where the same project updates cause agreggate totals to be updated and cause locks. The retry logic will eventually handle this scenario, but can introduce delay in confirming the journal and generating Dataverse actuals.
- The process automation lags slighly in knowing if the journal has been confirmed in Dataverse or not. Check for a confirmed journal or the existinence of the actuals from the journal in Dataverse to know if the transaction has been fully synced or not. The integration tracking in Dynamics 365 Finance only checks for updates on posted status at the start of every process automation recurrence.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
