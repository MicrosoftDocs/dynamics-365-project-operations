---
title: Configure project categories
description: This article provides information about setting up project categories.
author: ryansandness
ms.author: ryansandness
ms.date: 09/13/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure project categories

_**Applies To:** Project Operations Integrated with ERP_

Project Operations offers robust capabilities for categorizing revenue and expenses on projects. Categories provide the ability to report on and analyze project transactions, and drive posting to the general ledger.

The following diagram illustrates the correlation between transaction categories, shared categories, and project categories.

Transaction categories are the basic grouping for project transactions. That grouping has a set of shared categories that can be shared across applications and modules. Project categories are the most granular level of categories. Project categories are specific to legal entity, module, and application.

![Correlation between transaction categories, shared categories, and project categories.](media/project-categories.png)

## Transaction categories

Transaction categories represent the basic grouping for project transactions and aren't company or transaction type-specific. For example, Contoso Robotics uses Design, Travel, Installation, and Service Transaction categories to group Project transactions.

Transaction categories are defined within Dataverse.
1. Go to **Settings** \> **Transaction Categories** to open the form. 
2. Create a new transaction category either by selecting **New** or by selecting **Import from Excel**.

In the finance and operations architecture, the **Transaction categories** form provides a list of the transaction categories defined in Dataverse, and the enumeration mapping to each of the shared categories. The transaction category from Dataverse is assigned a unique identifier similar to TCN-0000001000-D3B43. Then five transaction categories are created to allow for setup for each shared category type. For example, using a category named Training, the mapping to the enumeration values for setup is:

| Shared category        | Name | Type |
|------------------------|------|------|
| TCN-0000001000-D3B43-1 | Training | Hour |
| TCN-0000001000-D3B43-2 | Training | Fee |
| TCN-0000001000-D3B43-3 | Training | Item |
| TCN-0000001000-D3B43-4 | Training | Expense |
| TCN-0000001000-D3B43-5 | Training | On-account |

Within Dataverse, users generally work with the name of the category. Within the finance and operations architecture, use of the category often requires a combination of shared category ID and type.

A user in Dataverse may enter a sales journal of type of expense against the Training category. In the finance and operations architecture, the user would set a default category for expense transactions to use by setting the default to TCN-0000001000-D3B43-Expense.


## Shared categories

Microsoft Dynamics 365 uses the Shared categories concept to categorize expenses in different applications, such as Microsoft Dynamics 365 Finance, Microsoft Dynamics 365 Supply Chain, and Project Operations. For each transaction category that's created, Project Operations automatically creates these five related Shared categories: Hours, Expense, Fees, Item, and On-account. You can review and adjust the shared categories by going to **Project management and accounting** \> **Setup** \> **Categories** \> **Shared Categories**.

### New functionality to allow categories on on-account type transactions

With the 10.0.41 release, there's a new feature that lets you create a shared category for on-account type transactions. Within **Feature management**, the **Enable project categories for on-account transactions** feature is now available. New functionality enabled by this feature includes:

- New transaction categories created in Dataverse now have a fifth shared category available to be configured.
- **Project management and accounting parameters** has a new default setting to default the category for on-account transactions. This default applies to both retainers and milestone transactions.
- The **Category groups** form now allows you to configure groups of type on-account. 
- The **Project categories** form now allows you to configure a category of type on-account.
- Category is added as an optional field. Existing on-account transactions continue to work without a category configured. New on-account transactions work with or without a category defined. Posting continues to be based on the setup of **Ledger posting setup** for the **Invoiced revenue - on-account** posting type.
- The **Ledger posting setup** form was enhanced to allow for configuration of a specific main account for a specific category relation. This enhancement allows users to set up a different revenue account for different categories.
- The **On-account** form allows for editing of the category, and the **Project invoice proposal** form prior to posting.
- 
## Project categories

Project categories represent most granular level of category configuration and must be configured separately, and for each company, by a Project accountant.

1. Go to **Project Management and Accounting** \> **Setup** \> **Categories** \> **Project categories**.
2. Select **New**.
3. Select the **Category ID** of the Shared category you created in the previous section. Project Operations allows using only those shared categories that are associated with transaction categories.
4. Select a category group.
 


## Category groups

Category groups are used to share properties, primarily posting profiles, between related Project categories. There must be at least one category group for each transaction type and each project category is assigned a group.

The posting specifications in Project Operations are defined using the project cost and revenue profile rules, project categories, and category groups. You can set up category groups by going to **Project management and accounting** \> **Setup** \> **Categories** \> **Category groups**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
