---
# required metadata

title: Deactivate Price Lists 
description: This topic provides information about how to deactivate or remove unsused or old price lists from Project Operations.
author: rumant
manager: AnnBe
ms.date: 03/14/2021
ms.topic: article
ms.prod: 
ms.service: project-operations
#

# optional metadata

# ms.search.form: 
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Professional Service industries
ms.author: rumant
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Deactivate Price Lists 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

When you need to remove old or unused Price Lists from Project Operations, follow the steps below:
1. **Remove or delete the price list from the following places:**

      a. Price Lists tab on Project parameters 

      b. Price Lists grid on Organizational Unit

      c. Project Price Lists grid on Account 

      d. Project Price Lists grid on all active Project Quotes in the system

      e. Project Price Lists grid on all active PRoject Contracts in the system
  
      To remove a Price List from any of these places, you will need to navigate to the subgrid mentioned above, select the Price List that you wish to remove from the subgrid and click on **Delete** from the Sub-grid menu. 
      This will ensure that Project Operations pricing will not retrieve this Price List in any Search for pricing or costing 
 
 2. **Deactivate or delete this Price List from the Active Price Lists**
 
     For deactivating or deleting a Price List from the Active Price Lists, select **Sales** area in the Project Operations Left Navigation menu. Then in **Customers** section of the Sales area, select the Navigation item **Price Lists**. This will show you a list of all active price lists in the system.
 
     From here, select the Price List that you wish to delete and click on the **Delete** button from the ribbon. If this Price List was already referenced on any transactions in the past, you will not be able to delete the Price List. In that case, you can choose to deactivate it so it does not appear in any views. To deactivate it, select Price List and click on **Deactivate** from the page ribbon.  

>[!NOTE]
> You will need to perform both of the steps mentioned above for Project Operations to not use a Price List. Only performing the Step 2 of directly deleting or deactivating the Price List from the Active Price Lists view will not be sufficient. You must also delete the association of this Price List from all the places mentioned in Step1. 
 
 
