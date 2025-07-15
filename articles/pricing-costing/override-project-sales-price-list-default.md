---
title: Override project sales price lists
description: This article provides information about creating custom sales price lists. 
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Override project sales price lists

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

## Customer-specific project price lists

Customer-specific price agreements can be set up as project price lists on an account record in Dynamics 365 Project Operations.

To set up a customer-specific project price list, in the **Sales** area, navigate to the account record.

1. Open the **Accounts** list page.
2. Locate and double-click a customer record to open the **Account** details page.
3. On the **Project Price lists** tab, select **+ New Project Price List**.
4. On the **New Project Price List** page, select a price list from the drop-down. Only price lists that have the context set to **Sales** and whose currency matches the account currency are included.
5. Name the association, and then select **Save**. A customer-specific project price list is created. This price list will be used to default project prices on project quotes or contracts created for this customer where the created date of the quote or project contract falls within the date effectivity of the price list.

## Custom pricing on project quotes

On project quotes, you can have project pricing that starts with a default standard price list that defaults from the customer or from the project parameters.

When you need custom pricing for project-related work on a particular quote, you can get that from the project price lists associated entity.

Complete the following steps to set up quote-specific project pricing.

1. Open the project quote and select the **Project Price Lists** tab.
2. In the subgrid, select **Create custom pricing**.

All the project price lists that are attached to the quote are copied to new price lists. The names of the new price lists reflect the name of quote with a date-time stamp for when these price lists were created.

You can use each of those price lists and make updates to labor (role price) and expense (category price) prices. These prices will only be applicable to this project quote.

## Price lists on a project contract

On a project contract, project pricing always defaults as a custom price list with the name of contract and the created date time stamp appended to the name. This is true whether the contract was created when the quote was won or if the contract was created from scratch. If needed, you can remove this association to the custom price list and associate a standard price list to the project contract instead.

When you associate a standard price list to the project price lists on quote or contract, any changes made to the prices in the price list will impact all quotes and contracts that use the price list.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
