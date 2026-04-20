---
title: Manage project price lists on project contracts
description:  This article provides information about managing project price lists on project contracts.
author: abriccetti
ms.author: abriccetti
ms.date: 02/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage project price lists on project contracts

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Project contracts in Microsoft Dynamics 365 Project Operations support multiple date-effective sales price lists on a contract. In Project Operations, a new associated entity named **Project Price Lists** has a one-to-many relationship with a project contract.

Use project price lists to price time, material, and expense transactions on a project. When a contract has one or more project price lists, use these price lists to price time, material, and expense estimates and actuals on projects that the contract line associates to the contract.

If a project contract doesn't have any project price lists, a warning message appears. The message informs you that there are no project price lists, and that your estimates and actual project work, material, and expenses that you log aren't priced. There's no price for sales values.

## Associate or disassociate a project price list on a project contract

### Create or associate a specific price list for estimating project-based work, material, and expenses

1. On the project contract, select the **Project Price Lists** tab.
1. In the subgrid, select **+ Add New Project Price List**.
1. On the **Quick Create** slider, select a price list. 

    The drop-down list shows all price lists that have the context set to **Sales**, where the currency on the price list matches the currency on the contract.

1. Enter a description for the project price list association, select **Save**, and then close the **Quick Create** slider.

    A project price list association is created.

1. Repeat steps 1-4 to associate more than one project price list to the project contract. Only create multiple project price lists if you have different date effectivity on each of the associated project price list.

> [!NOTE]
> Project Operations doesn't support overlapping date effectivity of project price lists. If there are multiple project price lists for a transaction that has a given date, the price on that transaction is set to 0 (zero) by default.

### Remove a project price list association

- Select the project price list, and then select **Delete Contract Project Price List** on the subgrid. 

    The price list is removed from the project price lists on the contract. The price list itself isn't deleted. Only the association to the contract is deleted.

## Set up automatic defaulting of project price lists on a contract

You can set up a project price list as the default project price list. This setup ensures that all contracts in your organization always start with a standard project price list for that price period.

### Set up an organizational default for the project price lists

To set up an organizational default for the project price lists, follow these steps:

1. Go to **Settings** \> **General** \> **Parameters**.
1. On the **Active Parameters** list page, find the record, and double-tap (or double-click) it to open it. While you double-tap (or double-click), make sure that you don't select a field value that is a hyperlink.
1. On the **Parameters** page, select the **Price List** tab. The default price list is shown. This list is a list of standard cost and sales price lists. By associating a sales price list with every currency that you sell in, you ensure that the sales price list is used by default on any contract that you create for customers that transact in this currency.

### Set up a customer-specific project price list

Set up customer-specific project price lists when you negotiate a master pricing agreement with your customers.

To set up a customer-specific project price list, follow these steps:

1. In the **Sales** area, select **Customers**.
1. In the list of your active accounts, select and open the customer record that you have a special price list for.
1. On the **Project Price Lists** tab, create a new price list association to have a project price list that's specific to the selected customer.

## Manage the default behavior for price lists during contract creation

When you create a project contract in Project Operations, the application provides options that let you specify how project price lists are associated with the project contract. Two options are available. To access these options, go to **Settings** \> **Parameters**, and open the **Parameters** record. Then, in the **Price List Defaulting Behavior** section, for the **During Contract creation** setting, select one of the following options.

#### Option 1: Associate existing applicable standard price lists to project contracts

Select this option to attach the standard price lists from **Parameters** or from **Customer** on the project contract. Of the two options, this option has the best performance for project contract creation, because only one new record is created from a pricing standpoint. However, if you select this option when a standard price list is used, you expose the contract to any price changes that are made in this price list. Therefore, the prices that you use might deviate from the prices that are used during execution of the project if you update prices in the price list at any time during execution of the project. 

#### Option 2: Associate copies of applicable standard price lists to the project contract

Select this option to create a full copy of the standard price list from **Parameters** or from **Customer**. The name of the contract and the date are appended and attached to this full copy for the project contract. Of the two options, this option has more impact on the time that is required to create the project contract. This option also causes data explosion of price list records. Therefore, use this option only when you must protect the entire price list (or price lists) during the project. 

## Create custom pricing on a project contract

1. On the project contract, on the **Project Price List** tab, in the subgrid, verify that no specific price list record is selected.
1. Select **Create Custom Pricing**. 

### Managing the behavior of custom pricing on project contracts

When you create custom pricing on a quote in Project Operations, the application provides options that let you specify how to create custom price lists. Two options are available. To access these options, go to **Settings** \> **Parameters**, and open the **Parameters** record. Then, in the **Price List Defaulting Behavior** section, for the **Custom pricing options** setting, select one of the following options.

#### Option 1: Create full copy of standard price lists 

Select this option to create a full copy of the contract price list. The name of the contract and the date are appended and attached to this full copy for the project contract. The existing associations with the standard price lists are removed. The salesperson can then make edits to the prices on the copy. These changed prices apply only to this project contract. Of the two options, this option has more impact on the performance of custom pricing creation. It also causes data explosion of price list records. Therefore, use this option only when you must protect the entire price list (or price lists) that you use during the execution stage during the project.

#### Option 2: Create protected price overrides for price list components used on the quote or the contract

Select this option to create date-effective price overrides that are scoped to the project contract for estimated components (in other words, the components that are referenced in contract line details). Because this option doesn't create a full copy of the contract price list, it has better performance than option 1. Depending on the number of contract line details, custom pricing takes longer to create. If the project contract has only a few contract line details, custom pricing creation is quick.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
