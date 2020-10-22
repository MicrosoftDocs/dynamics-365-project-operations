---
title: Override project sales price lists
description: 
author: rumant
manager: Annbe
ms.date: 10/22/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Override project sales price lists

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

# Overrides to Project sales price lists in Project Operations.

## Customer-specific project price lists

Customer – specific price agreements can be setup us project price lists on an Account record in Project Operations.

For setting up customer – specific project price lists, navigate to the Account record in Sales area from the Left navigation of Project Operations.

1. Open the Accounts list page.
2. Double -click a customer record from this page to open the Account details page
3. On the Account details page, access the tab called Project Price lists.
4. A sub-grid that shows all the project price lists for this account is shown. On this sub-grid, click + New Project Price List.
5. On the new Project price list page, select a price list from the dropdown. Only price lists that have the context set to &quot;sales&quot; and whose currency matches with the currency of the Account are shown in this dropdown.
6. Give this association a name and Save the association.
7. A customer-specific project price list is created and this will be used for defaulting as Project Prices on any Project Quotes or Project Contracts created for this Customer where the created date of the Quote or Project Contract falls within the date effectivity of the price list.

## Custom pricing on Project Quotes

On Project Quotes in project Operations, you can have a project pricing that starts off with a default standard price list that is defaulted from the Customer or from Project Parameters.

But in cases where you need some custom pricing for project related work for a particular Quote, you can achieve this in Project Operations from the Project Price lists associated entity.

In order setup Quote-specific project pricing:

1. Navigate to the specific Project Quote page and open the tab for Project Price Lists on the Quote page.
2. A sub-grid that shows all the project price lists for this Quote is shown. Making to no select any rows in the sub grid, click on the action to &quot;Create custom pricing&quot; from the Sub-grid actions.
3. All project price lists attached to the Quote are copied to new price lists and the name of these new price lists is changed to reflect the name of Quote with a date-time stamp for the creation of these price lists.
4. You can now open each of those price lists and make updates to Labor (role price) and Expense (category price) prices and these prices will only be applicable to this Project Quote and not to all Quotes in the system.

## Price lists on Project Contract

On Project Contracts in project Operations, project pricing is always defaulted as a custom price list with the name of contract and its created date time stamp appended to the name of the price list. This is true whether the Project Contract was created when the Quote was won or if the Project Contract was created from scratch. You can also, if required, and based on the requirement, remove this association to the custom price list and instead associate a standard price list to the project contract.

Please be aware that when you have associated a standard price list to the Project price lists on Quote or Project Contract, any changes to make to the prices in the price list will impact all Quotes and Contracts that use this price list.
