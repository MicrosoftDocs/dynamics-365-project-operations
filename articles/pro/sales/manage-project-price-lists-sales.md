---
title: Manage project price lists on project quotes 
description: This article provides information about working with project price lists on quotes.
author: rumant
ms.date: 05/24/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage project price lists on project quotes 

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

Project quotes are designed to support multiple date-effective sales price lists. With Dynamics 365 Project Operations, a new associated entity called **Project price lists** is added. This entity has a one-to-many relationship to a project quote.
Project price lists are used to price time, material, and expense transactions on a project. When a quote has one or more project price lists, these price lists are used to price time, material, expense estimates, and actuals on projects that are associated to the quote through the quote line.

A warning messages displays when there aren't any project price lists on a project quote. Because there aren't any project price lists, your estimated and actual project work and expenses can't be priced. Instead, the price for the sales value is zero (0).

## Associate or disassociate a project price list on a project quote

To create or select a specific price list for estimating project-based work and expenses, follow these steps.

1. On the quote, select the **Project Price** tab.
1. In the subgrid, select **+ Add New Project Price List**.
1. On the **Quick Create** page, select a price list. The drop-down list shows all of the price lists that have the context set to **Sales**, and the currency matches the currency on the quote.
1. Enter a description for the project price list association, and select **Save and Close**.

A project price list association is created. 

You can repeat this process as needed to associate more than one project price list to the project quote. Only create multiple project price lists if you have different effective dates on each of the associated project price lists.

> [!NOTE]
> Project Operations doesn't support overlapping date effectivity of the project price lists. If there are multiple project price lists for a transaction with a given date, the price on that transaction is defaulted to zero (0).

To remove a project price list association, select the project price list and then select **Delete Quote Project Price List**. The price list is removed from the project price lists on the quote, but the price list itself isn't deleted. Only the association to the quote is deleted.

## Set up default project price lists on a quote

Project price lists can be set up to default on a project quote. This setup ensures that all quotes in your organization always start with a standard price list for that price period.

### Set up an organizational default for the project price lists

To set up an organizational default for the project price lists, follow these steps.

1. Go to **Settings** \> **General** \> **Parameters**.
1. On the **Active Parameters** list page, locate the record, and double-click to open it. 
1. On the **Parameters** page, select the **Price List** tab. The default price list is shown. Associating a sales price list associated for every currency that you sell in ensures that this sales price list is defaulted on any quote that you create for customers that transact in the currency.

### Set up customer-specific project price lists

Customer-specific project price lists can be set up when you have negotiated a master pricing agreement with your customers.

To set up a customer-specific project price list, follow these steps.

1. In the **Sales** area, select **Customers**.
1. In the list of your active accounts, select and open the customer record that you have special price list for.
1. On the **Project Price Lists** tab, you can create a new price list association to have the project price list that is specific to this customer.

## Create custom pricing on a project quote

After you have organizational and customer-specific default project price lists, your project quotes will automatically be created with these project price list associations. However, in certain cases, you may need to create custom pricing for a specific project quote. 

To create custom pricing on a project quote, follow these steps.

1. On the **Project Quote**, on the **Project Price List** tab, verify in the subgrid that no specific price list record is selected.
1. Select **Create Custom Pricing**. 

### Managing the behavior of custom pricing on quotes

When you create custom pricing on a quote in Project Operations, the application provides options to you based on how the custom price lists are created. There are two options available. To access these options, navigate to **Settings** \> **Parameters**. On the **Parameters** page, open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **Custom pricing options**. You see two options:

#### Option 1 - Create full copy of standard price lists 
Selecting this option creates a full copy of the quote price list. The name of the quote and the date is appended and attached to this full copy of the Quote. The existing associations with the standard price lists are removed. The salesperson can then make edits to the prices on these copies. These changes are applicable to this project quote only. Of the two options, this option has a severe impact on the performance of creating custom pricing. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that you're using during quote stage for the duration of the Project. 


#### Option 2 - Create protected price overrides for price list components used on the quote or the contract
Selecting this option creates date-effective price overrides that are scoped to the quote for estimated components. In other words, the components referenced on quote line details. This option doesn't create an entire copy of the quote price list, therefore it has better performance than Option 1. Depending on the number of quote line details, it takes longer to create custom pricing, but is very quick to create custom pricing if the Quote only has a few quote line details.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
