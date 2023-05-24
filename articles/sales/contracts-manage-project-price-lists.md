---
title: Manage project price lists on project contracts
description:  This article provides information about managing project price lists on project contracts.
author: rumant
ms.date: 05/24/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage project price lists on project contracts

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project contracts in Dynamics 365 Project Operations are designed to support multiple date-effective sales price lists on a contract. In Project Operations, there is a new associated entity called **Project Price Lists**. This entity has a one-to-many relationship to a project contract.

Project price lists are used to price time, material, and expense transactions on a project. When a contract has one or more project price lists, these price lists are used to price for time, material, expense estimates, and actuals on projects that are associated to the contract through the contract line.

When there are no project price lists on a project contract, you will see a warning message that there are no project price lists and your estimates, actual project work, material, and expenses logged will not be priced. There will be no price for sales values.

## Associate or disassociate a project price list on a project contract

### Create or associate a specific price list for estimating project-based work, material, and expenses

1. On the project contract, select the **Project Price Lists** tab.
2. In the subgrid, select **+ Add New Project Price List**.
3. On the **Quick Create** slider, select a price list. 

  The drop-down list shows all price lists that have the context set to **Sales**, where the currency on the price list matches the currency on the contract.
  
4. Enter a description for the project price list association, select **Save**, and then close the **Quick Create** slider.

   A project price list association is created.
   
5. Repeat steps 1-4 to associate more than one project price list to the project contract. Only create multiple project price lists if you have different date effectivity on each of the associated project price list.

> [!NOTE]
> Project Operations doesn't support overlapping the date effectivity of the project price lists. If there are multiple project prices lists for a transaction with a given date, the price on that transaction is defaulted to zero (0).

### Remove a project price list association

- Select the project price list, and then select **Delete Contract Project Price List** on the subgrid. 

  The price list is removed from the project price lists on the contract. The price list itself will not be deleted. Only the association to the contract will be deleted.

## Set up automatic defaulting of project price lists on a contract

A project price list can be set up as the default project price list. This setup ensures that all contracts in your organization always start with a standard project price list for that price period.

### Set up an organizational default for the project price lists

To set up an organizational default for the project price lists, follow these steps.

1. Go to **Settings** \> **General** \> **Parameters**.
1. On the **Active Parameters** list page, locate the record, and double-click to open it. While double–clicking, make sure that you are not clicking on a field value that is a hyperlink. 
1. On the **Parameters** page, select the **Price List** tab. The default price list is shown. This is a list of standard cost and sales price lists. Having a **Sales** price list associated here for every currency that you sell in ensures that the sales price list is the default on any contract that you create for customers that transact in this currency.

### Set up a customer-specific project price list

Customer-specific project price lists can be set up when you have negotiated a master pricing agreement with your customers.

To set up a customer-specific project price list, follow these steps.

1. In the **Sales** area, select **Customers**.
1. In the list of your active accounts, select and open the customer record that you have special price list for.
1. On the **Project Price Lists** tab, you can create a new price list association to have the project price list that is specific to this customer.

## Managing how price lists defaulted during Contract creation

When creating a Project Contract in Project Operations, the application provides options to you on how Project Price Lists are associated to Project Contract. There are two options available. To access these options navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **During Contract creation**. You will see two options:

#### Option 1 - Associate existing applicable standard price lists to project contracts

Selecting this option attaches the standard price list(s) from **Parameters** or from **Customer** on the Project contract. Of the two options, this option has the best performance for project contract creation because there's only one new record that's created from a pricing standpoint. However, selecting this option when a standard price list is used exposes the contract to any price changes that are made in this price list. So the prices used may deviate from the prices used during execution of the project if prices in the price list are updated at any time during the execution of the project. 

#### Option 2 - Associate copies of applicable standard price lists to the project contract*

Selecting this option creates a full copy of the standard price list from **Parameters** or from **Customer**. The name of the contract and date are appended, and attached to this full copy to the Project contract. Of the two options, this option has a severe impact on the time it take to create the Project Contract. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) for the full duration of the project. 

## Create custom pricing on a project contract

After you have organizational and customer-specific default project price lists, your project contracts are automatically created with these project price list associations. However, in certain cases, you may need to create custom pricing for a specific project contract. 

1. On the **Project Contract**, on the **Project Price List** tab, verify in the subgrid that no specific price list record is selected.
2. Select **Create Custom Pricing**. 

### Managing the behavior of custom pricing on project contracts

When creating custom pricing on a quote in Project Operations, the application provides options to you on how custom price lists are created. There are two options available. To access these options navigate to **Settings** \> **Parameters**. On the **Parameters** page, Open the **Parameters** record. On the section **Price List Defaulting Behavior**, use the setting **Custom pricing options**. You see two options:

Option 1 - **Create full copy of standard price lists**: 
Selecting this option creates a full copy of the contract price list. The name of the contract and the date is appended and attach ed to this full copy to the Project Contract. The existing associations with standard price lists is removed. The salesperson can then make edits to prices on these copies. These changed prices are applicable to this project contract only. Of the two options, this option has a severe impact on the performance of creating custom pricing. This option also creates data explosion of price list records. Use this option only when you need to protect the entire price list(s) that you are using during execution stage for the duration of the Project. 

Option 2 - **Create protected price overrides for price list components used on the quote or the contract**:
Selecting this option creates date-effective price overrides that are scoped to the Project Contract for estimated components. In other words, the components referenced on Contract line details. This option doesn't create an entire copy of the Contract price list, therefore it has better performance than Option 1. Depending on the number of contract line details, it takes longer to create custom pricing, but is very quick to create custom pricing if the Project Contract only has a few Contract line details.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
