---
title: Manage project price lists on project contracts
description:  This topic provides information about managing project price lists on project contracts.
author: rumant
ms.date: 03/30/2021
ms.topic: article
ms.reviewer: johnmichalak
ms.author: rumant
---

# Manage project price lists on project contracts

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project contracts in Dynamics 365 Project Operations are designed to support multiple date effective sales price lists on a contract. In Project Operations, there is a new associated entity called **Project Price Lists**. This entity has a one-to-many relationship to a project contract.

Project price lists are used to price time, material, and expense transactions on a project. When a contract has one or more project price lists, these price lists are used to price for time, material, expense estimates, and actuals on projects that are associated to the contract through the contract line.

When there are no project price lists on a project contract, you will see a warning message that there are no project price lists and your estimates, actual project work, material, and expenses logged will not be priced. There will be no price for sales values.

## Associate or unassociate a project price list on a project contract

### Create or associate a specific price list for estimating project-based work, material, and expenses

1. On the project contract, select the **Project Price Lists** tab.
2. In the subgrid, select **+ Add New Project Price List**.
3. On the **Quick Create** slider, select a price list. 

  The drop-down list shows all price lists that have the context set to **Sales**, where the currency on the price list matches the currency on the contract.
  
4. Enter a description for the project price list association, select **Save**, and then close the **Quick Create** slider.

   A project price list association is created.
   
5. Repeat steps 1-4 to associate more than one project price list to the project contract. Only create multiple project price lists if you have different date effectivity on each of the associated project price list.

> [!NOTE]
> Project Operations doesn't support overlapping the date effectivity of the project price lists. If there are multiple project prices lists for a transaction with a given date, the price on that transaction will be defaulted to zero.

### Remove a project price list association

- Select the project price list, and then select **Delete Contract Project Price List** on the subgrid. 

  The price list is removed from the project price lists on the contract. The price list itself will not be deleted. Only the association to the contract will be deleted.

## Set up automatic defaulting of project price lists on a contract

A project price list can be set up as the default project price list. This setup ensures that all contracts in your organization always start with a standard project price list for that price period.

### Set up the organizational default for project price lists

1. Go to **Settings** > **General**, and then select **Parameters**.
2. In the **Active Parameters** list page, select and double-click the record to open it. While double–clicking, make sure that you are not clicking on a field value that is hyperlink. 
3. On the **Active Parameters** page, select the **Price List** tab. A subgrid shows a list of default price lists. This is a list of standard cost and sales price lists. Having a **Sales** price list associated here for every currency that you sell in ensures that the sales price list is the default on any contract that you create for customers that transact in this currency.

### Set up a customer-specific project price list

You can also set up customer–specific project price lists when you have negotiated a master pricing agreement with your customers.

1. Go to **Sales** > **Customers**.
2. From the list of active accounts, select the customer for whom have special price list.
3. Select the customer record to open it and then select the **Project Price Lists** tab. A subgrid shows a list of project price lists specific to this customer. 
4. Create a new price list association here to have project price list specific to this customer.

## Custom pricing on a project contract

After you have organizational and customer-specific default project price lists, your project contracts will be created with these project price list associations automatically. However, project price lists on a project contract are always copied with the date and contract name appended to them. The account and project managers can then begin making edits to prices on these copies. These changed prices will be applicable to this project contract only.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
