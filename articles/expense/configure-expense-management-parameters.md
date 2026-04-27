---
title: Configure Expense management parameters
description: This article describes the parameters that control the general behavior in Expense management.
author: mukumarm
ms.author: mukumarm
ms.date: 07/21/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure Expense management parameters

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article describes the parameters the control the general behavior in Expense management.

## General

| Field                                                    | Description |
|----------------------------------------------------------|-------------|
| Standard rate of mileage                                 | Enter the reimbursement rate for mileage expenses. This rate is multiplied by the mileage that is entered for the expense to calculate the amount that is reimbursed for the travel expense. |
| Validate expense purpose                                 | Turn on this option to limit users to an existing set of values that is configured in the **Purpose of expense report** field when they create expense reports. |
| Personal expenses paid by                                | Select who is responsible for paying any credit card transaction amounts that are categorized as personal. |
| Display entire expense report on drillback               | Select this option to show all expenses for an expense report when the details of the original document are viewed for a specific voucher that was generated when the expense report was posted. |
| Preauthorization of travel is mandatory                 | Select this option to require that a travel requisition be submitted and approved before an employee can submit an expense report. |
| Allow editing of distributions before posting            | Select whether the distributions of an expense report can be edited before it's posted. |
| Evaluate expense management policies                     | Select when expenses are evaluated to determine whether an expense policy has been violated. Expenses can be evaluated for violations when the expense entry is entered and saved, or when the expense is submitted for approval. The policy rules for receipts that are required are evaluated when the expense line is saved. |
| Allow intercompany expense lines                         | Select whether expenses for other legal entities can be entered on an expense report. |
| Allow editing the exchange rate for credit card expenses | Select this option to allow the user to edit the exchange rate for imported credit card expenses. |
| Multi-level hierarchy fields to display                  | Select which approver fields are shown when the workflow assignment type is set to be a hierarchy, and the **Hierarchy** selection is set to use the approval hierarchy, expense multi-level approval. When the multi-level approval hierarchy is used for a workflow, the selected fields are shown on the expense report and can be edited. |
| Enter employee credit card number                        | Select whether a 15-character or 16-character number can be entered and saved in the **Card ID** field on the **Credit cards** page for an employee. |
| Validate travel requisition purpose                      | Turn on this option to limit users to an existing set of values that is configured in the **Purpose of expense report** field when they create travel requisitions. |
| Default document type                                   | Configure a default document type for receipts uploaded by users to ensure consistent initial categorization. By default, this field is left blank and can be set based on your organization’s needs. Once configured, the selected document type automatically applies when a user uploads a receipt. If left blank, the system refers to the default configuration set in Document Management Parameters. |

## Financial

| Field                                                                                    | Description |
|------------------------------------------------------------------------------------------|-------------|
| Ledger daily journal name                                                                | Select the name of the ledger journal that approved expense reports are posted to. |
| Enable tax recovery from expenses                                                        | Select this option to enable expense tax recovery for eligible expenses. This option can't be selected if US sales tax and use tax rules are enabled. |
| Post cash advances immediately                                                           | Select this option to post an approved cash advance when the Pay and transfer process is completed. If this option isn't selected, the Pay and transfer process generates an unposted general journal. |
| Correct accounting date during posting                                                   | Select this option to update the accounting date when expenses are posted, if the current period is on hold or closed. The accounting date is set to the next open period. |
| Allow grouping of transactions based on offset account specified in payment method       | Select this option to summarize the expense transactions for an expense report, based on the offset account that is specified in the payment method for the expenses. |
| Tax included                                                                             | Select this option to include sales tax in the expense amount by default. |
| Release encumbrances on closing travel requisitions                                      | Select this option to release encumbered funds when an approved travel requisition is closed. |
| Allow travel requisition submit on budget overrun for budget register and project budget | Select this option to allow employees to submit travel requisitions for approval, even though they exceed either the allowed budget that is set in the budget register or the allowed budget for a project. |
| Allow expense report submit on budget overrun for budget register and project budget     | Select this option to allow employees to submit expense reports for approval, even though they exceed either the allowed budget that is set in the budget register or the allowed budget for a project. |
| Allow expense report approval on budget overrun for budget register only                 | Select this option to allow approvers to approve expense reports that exceed the allowed budget that is set in the budget register. |
| Enable posting of expenses on posting date                                               | Select this option to post expenses using the posting date of the expense report. If the period is **on hold** or **closed** and **Correct accounting date during posting** is enabled, the system posts the expenses on the **first date of the next open period**. This functionality is available starting from version 1**0.0.45**.|

## Per diem

| Field                                 | Description |
|---------------------------------------|-------------|
| Minimum hours for per diem            | Enter the default minimum number of hours that an employee must work in a day to be eligible to receive a per diem for travel-related expenses. This value is used as a default value only for the **Minimum hours** field for per diem rate tiers. |
| Meal percent                          | Enter the default percentage of the per diem for meals that is used on the first and last days of the travel-related expense when the **Calculate meal reduction by** field is set to either **Meal type per day** or **Number of meals per day**. The workday on the first and last days might be shorter than a standard workday. Therefore, the amount of the per diem on those days might differ from the standard amount. If the percentage is set to **0** (zero), the deductions for the first and last days will be 0.00. |
| Hotel percent                         | Enter the default percentage of the per diem for hotels that is used on the first and last days of the travel-related expense. The workday on the first and last days might be shorter than a standard workday. Therefore, the amount of the per diem on those days might differ from the standard amount. If the percentage is set to **0** (zero), the deductions for the first and last days will be 0.00. |
| Other percent                         | Enter the default percentage of the per diem for miscellaneous expenses that is used on the first and last days of the travel-related expense. The workday on the first and last days might be shorter than a standard workday. Therefore, the amount of the per diem on those days might differ from the standard amount. If the percentage is set to **0** (zero), the deductions for the first and last days will be 0.00. |
| Reduction in percentage for breakfast | Enter the amount that the per diem is reduced by for breakfast. For example, if an employee receives a complimentary breakfast, you might want to reduce the amount of the per diem by 10 percent. |
| Reduction in percentage for lunch     | Enter the amount that the per diem is reduced by for lunch. For example, if an employee receives a complimentary lunch, you might want to reduce the amount of the per diem by 15 percent. |
| Reduction in percentage for dinner    | Enter the amount that the per diem is reduced by for dinner. For example, if an employee receives a complimentary dinner, you might want to reduce the amount of the per diem by 25 percent. |
| Calculate meal reduction by           | Specify how the system should calculate the per diem meal reduction, by selecting whether the reduction is based on the meal type per trip or per day, or whether it's based on the number of meals that is allowed per day. |
| Per diem rounding                     | Select the type of rounding that is used for per diem expenses. If you select normal rounding, any per diem expense that has an amount of 0.50 is rounded up to 1.00, and any per diem expense that has an amount that is less than 0.50 is rounded down to 0.00. |
| Base per diem calculation on          | Select whether a per diem amount is based on a calendar day or a 24-hour period. |
| Allow user to edit transaction date          | Select this option to modify the transaction date for a per diem expense. The exchange rate on the expense line is updated automatically based on the new transaction date selected. This functionality is available starting from version **10.0.0.45**. |

## Fax cover pages

| Field                          | Description |
|--------------------------------|-------------|
| Instructions                   | Enter the instructions that employees must follow when they create a cover page for a fax that is used to send receipts that are related to an expense report. To enter language-specific text that is shown, based on the user language, select **Translations**. |
| User ID (Bar code information) | Select this option to store an employee's unique identifier in the bar code that is used on the cover page of the fax. |
| Bar code                       | Select the bar code that is used on the cover page of the fax. Bar codes 39 and 128 are supported in Expense management. |

## Number sequence

Starting with version **10.0.45**, the **Enable number sequence configuration in the Expense parameters form** feature was introduced. The Number sequence feature enables the configuration of unique identifiers for various Expense Management documents, such as cash advance requests, vouchers, invoices, and expense reports. This enhancement allows you to view and manage number sequences directly within the **Expense Management parameters** to help streamline the setup process.

**Expense management** > **Setup** > **Expense management parameters** > **Number sequence**

### Shared number sequence

There are certain number sequences, such as the **Expense transaction number** and **Itemization group**, that are **shared** across all legal entities. To support this, the **Shared number sequence** tab was introduced in the **Expense Management parameters** form, allowing users to view and configure these shared number sequences directly within the interface.

**Expense management** > **Setup** > **Expense management parameters** > **Shared number sequence**

> [!NOTE]
> This feature doesn't affect the use of number sequences; it simply enables the display of number sequences specific to expense management within the expense management parameters.

## Anti-corruption

| Field                                 | Description |
|---------------------------------------|-------------|
| Display anti-corruption attestation   | Select this option to show the anti-corruption text when an expense report is created. Specific expense categories can then be enabled that will require that the anti-corruption attestation be selected on the expense report. For example, a gift category that is related to a government official expense might require that the employee confirm that the expense meets company policy that is related to government officials. |
| Anti-corruption message for submitter | Enter the text that should be shown to an employee who is creating an expense report. To enter language-specific text that is shown, based on the user language, select **Translations**. |
| Anti-corruption message for approver  | Enter the text that should be shown to the approver when an expense report is created. To enter language-specific text that is shown, based on the user language, select **Translations**. |

## Expense mobile

| Field                                 | Description |
|---------------------------------------|-------------|
|Enable project validations | This field determines which projects are displayed in the project selection field by applying **project-related validations**, such as **project-category and resource-project**. When **enabled**, the system displays up to **10,000 active projects** based on these validations during expense creation. When **disabled**, there isn't a limit on the number of projects displayed, but validations are applied when the expense line is saved. This field setting is valid only for expense mobile application.|

[!INCLUDE[footer-include](../includes/footer-banner.md)]
