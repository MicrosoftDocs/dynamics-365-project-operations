---
title: Manage project price lists on project quotes 
description: This article provides information about working with project price lists on quotes.
author: rumant
ms.date: 03/30/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage project price lists on project quotes 

_**Applies To:** Lite deployment - deal to proforma invoicing, Project Operations for resource/non-stocked based scenarios_

Project quotes are designed to support multiple date effective sales price lists. With Dynamics 365 Project Operations, a new associated entity called **Project price lists** is added. This entity has a 1-to-many relationship to a project quote.

Project price lists are used to price time, material, and expense transactions on a project. When a quote has one or more project price lists, these price lists are used to price time, material, expense estimates, and actuals on projects that are associated to the quote through the quote line.

When there are no project price lists on a project quote, you will receive a warning message. The message states that because there are no project price lists, your estimated and actual project work and expenses will not be priced. Instead, they will have zero (0) price for sales values.

## Associate or disassociate a project price list on a project quote

To create or select a specific price list for estimating project-based work and expenses, complete the following steps.

1. On the quote, select the **Project Price** tab and in the subgrid, select **+ Add New Project Price List**.
2. On the Quick Create page, select a price list. The drop-down list shows all price lists that have the context set to **Sales** and the currency matches the currency on the quote.
4. Enter a description for the project price list association and select **Save and Close**.

A project price list association is created.

You can repeat this process if you need to associate more than one project price list to the project quote. Only create multiple project price lists if you have different effective dates on each of the associated project price lists.

> [!NOTE]
> Project Operations does't support overlapping date effectivity of the project price lists. If there are multiple project prices lists for a transaction with given date, the price on that transaction will be defaulted to zero (0).
To remove a project price list association, select the project price list and then select **Delete Quote Project Price List**. The price list is removed from the project price lists of the quote, but the price list itself is not deleted. Only the association to the quote is deleted.

## Set up default project price lists on a quote

Project price lists can be set up to default on a project quote. This setup ensures that all quotes in your organization always start with a standard price list for that price period.

### Set up organizational default for project price lists

1. Go to **Settings** > **General** > **Parameters**.
2. On the **Active Parameters** list page, locate the record and double-click to open it. 
3. On the **Parameters** page, select the **Price List** tab. You can see the list of default price lists is shown. This is a list standard cost and sales price lists. Having a sales price list associated here for every currency that you sell in, will ensure that this sales price list is defaulted on any quote that you create for customers that transact in this currency.

### Set up customer-specific project price lists

Customer-specific project price lists can also be set up when you have negotiated a master pricing agreement with your customers.

To set up a customer-specific project price list, complete the following steps.

1. In the **Sales** area, select **Customers**.
2. In the list of your active accounts, select and open the customer record that you have special price list for.
3. On the **Project Price Lists** tab, you can create a new price list association to have the project price list that is specific to this customer.

## Create custom pricing on a project quote

After you have organizational and customer-specific default project price lists, your project quotes will automatically be created with these project price list associations. However, in certain cases, you may need to create custom pricing for a specific project quote. 

1. On the **Project Quote**, on the **Project Price List** tab, verify in the subgrid that no specific price list record is selected.
2. Select **Create Custom Pricing**. 

### Managing the behavior of custom pricing on quotes

When creating custom pricing on a quote in Project Operations, the application provides options to you on how custom price lists are created. There are 3 options available. To access these options navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **Custom pricing options**. You will see 2 options:

Option 1 - **Create full copy of standard price lists**: 
Selecting this option will create a full copy of the quote price list with the name of the quote and date appended and attach this full copy to the Quote. The existing associations to standard price lists will be removed.  The salesperson can then begin making edits to prices on these copies. These changed prices will be applicable to this project quote only. Of the 2 options, this option will have a severe impact on the performance of creating custom pricing. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that you are using during quote stage for the duration of the Project. 


Option 2 - **Create protected price overrides for price list components used on the quote or the contract**:
Selecting this option will create date effective price overrides scoped to the quote for estimated components i.e. components referenced on quote line details. This option will not create an entire copy of the quote price list and therefore will give much better performance than selecting Option 1 above. Dependning on the number of quote line details, this could take longer to create custom pricing or be very quick to create custom pricing if the Quote had only a few Quote line details.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
