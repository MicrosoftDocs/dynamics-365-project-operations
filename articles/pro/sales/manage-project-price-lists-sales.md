---
title: Manage project price lists on project quotes 
description: This article provides information about working with project price lists on quotes.
author: rumant
ms.date: 05/24/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage project price lists on project quotes 

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Core, Project Operations Integrated with ERP_

Project quotes are designed to support multiple date-effective sales price lists. In Microsoft Dynamics 365 Project Operations, a new associated entity named **Project price lists** is added. This entity has a one-to-many relationship with a project quote.

Project price lists are used to price time, material, and expense transactions on a project. When a quote has one or more project price lists, these price lists are used to price time, material, expense estimates, and actuals on projects that are associated to the quote through the quote line.

A warning message appears if there aren't any project price lists on a project quote. Because there aren't any project price lists, your estimated and actual project work and expenses can't be priced. Instead, the price for the sales value is 0 (zero).

## Associate or disassociate a project price list on a project quote

To create or select a specific price list for estimating project-based work and expenses, follow these steps.

1. On the quote, select the **Project Price** tab.
1. In the subgrid, select **Add New Project Price List**.
1. On the **Quick Create** page, select a price list. The drop-down list shows all the price lists where the context is set to **Sales** and the currency matches the currency on the quote.
1. Enter a description for the project price list association, and then select **Save and Close**.

A project price list association is created. 

You can repeat this process as needed to associate more than one project price list with the project quote. Create multiple project price lists only if you have a different effective date on each associated project price list.

> [!NOTE]
> Project Operations doesn't support overlapping date effectivity of project price lists. If there are multiple project price lists for a transaction that has a given date, the price on that transaction is set to 0 (zero) by default.

To remove a project price list association, select the project price list, and then select **Delete Quote Project Price List**. The price list is removed from the project price lists on the quote, but the price list itself isn't deleted. Only the association with the quote is deleted.

## Set up default project price lists on a quote

Project price lists can be set up to default on a project quote. This setup ensures that all quotes in your organization always start with a standard price list for that price period.

### Set up an organizational default for the project price lists

To set up an organizational default for the project price lists, follow these steps.

1. Go to **Settings** \> **General** \> **Parameters**.
1. On the **Active Parameters** list page, find the record, and double-tap (or double-click) it to open it. 
1. On the **Parameters** page, select the **Price List** tab. The default price list is shown. By associating a sales price list with every currency that you sell in, you ensure that this sales price list is used by default on any quote that you create for customers that transact in the currency.

### Set up customer-specific project price lists

Customer-specific project price lists can be set up when you've negotiated a master pricing agreement with your customers.

To set up a customer-specific project price list, follow these steps.

1. In the **Sales** area, select **Customers**.
1. In the list of your active accounts, select and open the customer record that you have a special price list for.
1. On the **Project Price Lists** tab, you can create a new price list association to have a project price list that is specific to the selected customer.

## Create custom pricing on a project quote

After you have organizational and customer-specific default project price lists, your project quotes will automatically be created with these project price list associations. However, in certain cases, you may need to create custom pricing for a specific project quote. 

To create custom pricing on a project quote, follow these steps.

1. On the project quote, on the **Project Price List** tab, in the subgrid, verify that no specific price list record is selected.
1. Select **Create Custom Pricing**. 

### Managing the behavior of custom pricing on quotes

When you create custom pricing on a quote in Project Operations, the application provides options that let you specify how custom price lists are created. Two options are available. To access them, go to **Settings** \> **Parameters**, and open the **Parameters** record. Then, in the **Price List Defaulting Behavior** section, for the **Custom pricing options** setting, select one of the following options.

#### Option 1: Create full copy of standard price lists

Select this option to create a full copy of the quote price list. The name of the quote and the date are appended and attached to this full copy of the quote. The existing associations with the standard price lists are removed. The salesperson can then make edits to the prices on the copy. These changes apply only to this project quote. Of the two options, this option has more impact on the performance of custom pricing creation. It also causes data explosion of price list records. Therefore, use this option only when you must protect the entire price list (or price lists) that you use during the quote stage for the duration of the project. 

#### Option 2: Create protected price overrides for price list components used on the quote or the contract

Select this option to create date-effective price overrides that are scoped to the quote for estimated components (in other words, the components that are referenced in quote line details). Because this option doesn't create a full copy of the quote price list, it has better performance than option 1. Depending on the number of quote line details, custom pricing takes longer to create. If the quote has only a few quote line details, custom pricing creation is very quick.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
