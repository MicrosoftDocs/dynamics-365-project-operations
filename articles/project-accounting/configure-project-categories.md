---
title: Configure project categories
description: This article provides information about setting up project categories.
author: ryansandness
ms.author: ryansandness
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure project categories

_**Applies To:** Project Operations Integrated with ERP_

Project Operations provides robust capabilities for categorizing revenue and expenses on projects. By using categories, you can report on and analyze project transactions, and drive posting to the general ledger.

The following diagram shows the correlation between transaction categories, shared categories, and project categories.

Transaction categories are the basic grouping for project transactions. That grouping has a set of shared categories that you can share across applications and modules. Project categories are the most granular level of categories. Project categories are specific to legal entity, module, and application.

:::image type="content" source="media/project-categories.png" alt-text="Screenshot of correlation between transaction categories, shared categories, and project categories.":::

## Transaction categories

Transaction categories represent the basic grouping for project transactions. They're not company or transaction type-specific. For example, Contoso Robotics uses Design, Travel, Installation, and Service transaction categories to group project transactions.

Define transaction categories within Dataverse.
1. Go to **Settings** \> **Transaction Categories** to open the form. 
1. Create a new transaction category either by selecting **New** or by selecting **Import from Excel**.

In the finance and operations architecture, the **Transaction categories** form provides a list of the transaction categories defined in Dataverse, and the enumeration mapping to each of the shared categories. The transaction category from Dataverse is assigned a unique identifier similar to TCN-0000001000-D3B43. Then five transaction categories are created to allow for setup for each shared category type. For example, using a category named Training, the mapping to the enumeration values for setup is:

| Shared category        | Name | Type |
|------------------------|------|------|
| TCN-0000001000-D3B43-1 | Training | Hour |
| TCN-0000001000-D3B43-2 | Training | Fee |
| TCN-0000001000-D3B43-3 | Training | Item |
| TCN-0000001000-D3B43-4 | Training | Expense |
| TCN-0000001000-D3B43-5 | Training | On-account |

Within Dataverse, users generally work with the name of the category. Within the finance and operations architecture, use of the category often requires a combination of shared category ID and type.

A user in Dataverse can enter a sales journal of type of expense against the Training category. In the finance and operations architecture, the user sets a default category for expense transactions to use by setting the default to TCN-0000001000-D3B43-Expense.


## Shared categories

Microsoft Dynamics 365 uses the shared categories concept to categorize expenses in different applications, such as Microsoft Dynamics 365 Finance, Microsoft Dynamics 365 Supply Chain, and Project Operations. For each transaction category that you create, Project Operations automatically creates these five related shared categories: Hours, Expense, Fees, Item, and On-account. You can review and adjust the shared categories by going to **Project management and accounting** \> **Setup** \> **Categories** \> **Shared Categories**.

### New functionality to allow categories on on-account type transactions

In the 10.0.41 release, a new feature lets you create a shared category for on-account type transactions. Within **Feature management**, the **Enable project categories for on-account transactions** feature is now available. New functionality enabled by this feature includes:

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
1. Select **New**.
1. Select the **Category ID** of the Shared category you created in the previous section. Project Operations allows using only those shared categories that are associated with transaction categories.
1. Select a category group.
 


## Category groups

Use category groups to share properties, primarily posting profiles, between related Project categories. Each transaction type requires at least one category group, and you assign each project category to a group.

Project Operations defines the posting specifications by using the project cost and revenue profile rules, project categories, and category groups. Set up category groups by going to **Project management and accounting** \> **Setup** \> **Categories** \> **Category groups**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
