---
title: Deactivate price lists 
description: This article explains how to deactivate or remove unused or old price lists.
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Professional Service industries
ms.search.validFrom: 2020-10-01
---

# Deactivate price lists 

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

To remove old or unused price lists from Dynamics 365 Project Operations, there are two steps you must complete. 

1. Remove or delete the price list from specific pages.
2. Deactivate or delete the price list from the Active price lists on the **Price Lists** page.

>[!IMPORTANT]
> You must complete both steps to fully remove a price list. Only performing step 2, which is to directly delete or deactivate the price list from the Active Price Lists view, is not sufficient. You must also delete the association of this price list from all the places mentioned in step 1.

## Delete the price list from specific pages
1. To delete a price list from Project Operations, go to the following pages:  

      - **Project parameters** page > **Price Lists** tab
      - **Organizational Unit** page > **Price Lists** grid
      - **Account** page > **Project Price Lists** grid
      - **Project Quotes** page > **Project Price Lists** grid: **Project Price Lists** applies to all active project quotes.
      - **Project Contracts** page > **Project Price Lists** grid: **Project Price Lists** applies to all active project contracts.

 2. For each page, you need to select the price list that you want to delete, and then select **Delete**. 
 
## Delete or deactivate the price list from the Price Lists page
 
1. To delete a price list from the active price lists, go to **Sales** > **Customers** > **Price Lists**. 
2. Select the price list that you want to delete and then select **Delete**. If the price list is referenced on any existing transactions, you can't delete it. If this price list is referenced on any existing transactions, you can deactivate the price list so that it doesn't appear in any views. 
3. To deactivate the price list, select the price list again, and then select **Deactivate**.   
