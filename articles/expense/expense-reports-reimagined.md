---
title: Expense reports reimagined
description: This article explains the redesigned and reimagined experience for expense report entry.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense reports reimagined

[!INCLUDE[banner](../includes/banner.md)]

Expense report entry was redesigned to simplify the process and reduce the time needed to complete a report. Here are the major components of the new expense experience:

- A new expense management workspace that lets you access your delegate's expenses.
- A new receipt matching experience to better show header-level receipts and simplify the process of attaching receipts to expense lines.
- A new read-only grid that lets you view many more expense lines and other columns of data. You can now see all itemized and split lines, together with their parent expenses.
- A simplified pane for editing expenses.
- Redesigned error, warning, and policy messages to provide the correct context and understanding of the issue and how to resolve it. We removed several of the messages that appeared before users could complete their tasks and address the issues.
- A new page to specify required fields, optional fields, and the fields that shouldn't be included. This page helps to reduce the number of fields that must be set.
- A new look and feel for expense reports, so that the reports no longer seem as though they were designed for accounting personas.

To turn on the new experience, use the **Feature management** workspace to turn on the **Expense reports reimagined** and **Expense reports reimagined enhancements** features. When you turn on these features, the following actions occur:

- The existing expense workspace is replaced with the new workspace.
- A new menu item for expense field visibility is added.
- No existing menu items for expense reports (the existing page) or expense report fields are removed.

> [!VIDEO ad14b5ae-36c0-4cef-bfcd-776261f8cb29]

## Features available when enabling the Expense reports reimagined feature

| Feature | Description |
|---|----|
| Expense field visibility | A new setup page lets you specify which fields should be disabled for an organization. You can also specify which fields should be required, and which fields are recommended. |
| Required fields | New simple configuration lets you make some required fields without using the policy framework. |
| Optional fields | A second page for optional fields is added. In this way, employees won't feel as if they must set the fields, but the fields are still easily accessible. |
| Add unattached receipts | The ability to add unattached receipts to expense report is more visible from the workspace and on the expense report. |
| Improved messaging | Better visibility into expense lines that have warnings or errors. |
| Reduction in messages in the message bar| The number of Infolog messages was decreased, and an effort was made to prevent duplicate messages from appearing in many cases. |
| Grouped together common actions | The interface was cleaned up with the addition of a new actions button for most of the common line-level actions and the addition of an ellipsis button (...) for header and other less frequent actions. |
| New workspace to increase visibility | A new workspace unifies features and links that let users move to different areas. |
| Add existing expenses and receipts during expense creation | When you create expense reports, you can add all expenses, or select unattached expenses. Unattached expenses are expenses that were imported from the corporate credit card feed or expenses that were manually created by the user but not attached to an expense report.|
| Exchange rate calculator | An exchange rate calculator is added that lets you calculate the exchange rate for out-of-pocket multicurrency transactions. |
| Save and add new expense lines | **Save** and **New** buttons are available when new expenses are entered, to help you quickly enter expense lines. |
| Better visibility into split and itemized lines | Itemized and split lines are added directly to the list of expenses to increase visibility and help you easily determine whether there are any errors. |
| View subcategory details in itemized lines | Itemized lines of a parent expense show the subcategory labels on the expense report. The itemization lets you  review the granular details at a glance.|
|Itemize recurring expenses quickly | The reimagined expense workspace provides the ability to itemize recurring expenses quickly by adding the subcategory, start date, and quantity. The quantity refers to the number of times the charge is repeated across a continuous period. |
| Show receipts during itemization | Receipts can be shown during itemization. |
| Cash advance selection | Select one or more cash advances for fulfilling a single expense transaction. |
| Cash advance balance | Review the cash advance balance in real time when you create an expense entry against approved and paid cash advances. |

## New features available when enabling the 'Expense reports reimagined enhancements' feature

| Feature | Description |
|---|----|
| Workflow history | View the workflow history for an expense report. |
| Line-level workflows | Submit and recall line-level workflows. |
| Map expenses to a travel requisition | Map an expense to an approved travel requisition. |
| Quick matching of receipts to expenses | Match a receipt to multiple expenses at once. |
| Interim and final approvers | Configure interim and final approvers for expense reports. |
| Merge with a draft expense | If an expense is a duplicate of another draft expense, you can select the concerned expenses and merge them into a single expense. |
| Reconcile against submitted expenses | Match unattached expenses to expenses that have already been submitted. |
| Attestation of anti-corruption messages | Attest to the anti-corruption message configured for a particular expense category. |

To enable the **Per Diem** capability within Expense reports reimagined, enable the **Per-diem for expense report re-imagined interface** feature in **Feature management**.

Expense reports reimagined is currently focused on expense entry scenarios. Any expense report review or approval scenario will continue to use the existing expense entry page.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
