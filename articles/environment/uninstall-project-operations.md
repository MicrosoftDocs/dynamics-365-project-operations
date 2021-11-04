---
title: Uninstall Dynamics 365 Project Operations 
description: This topic provides information about how to uninstall Dynamics 365 Project Operations.
author: stsporen
ms.date: 11/04/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Uninstall Dynamics 365 Project Operations 

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

To uninstall Dynmaics 365 Project operations, you must be assigned the role of Administrator.

1. Go to **Settings** > **Solutions**.

    ![Settings page.](./media/uninstall-proj-ops-solutions.png)
  
2. Remove the solutions in the exact order they are listed in the following table. 

  | Solution   name                                    | Note                                                                                         |
|----------------------------------------------------|----------------------------------------------------------------------------------------------|
| msdyn_ProjectServiceUpgrade_managed.cab            | If not found, skip this   solution.                                                          |
| ProjectOperations_Anchor                           | If not found, skip this   solution.                                                          |
| Dynamics365ProjectOperationsDualWriteEntityMaps    | If not found, skip this   solution.                                                          |
| Dynamics365ProjectOperationsDualWrite              | If not found, skip this   solution.                                                          |
| ProjectService                                     | No additional notes.                                                                         |
| ProjectServiceCore_Patch                           | No additional notes.                                                                         |
| ProjectServiceCore                                 | No additional notes.                                                                         |
| ProjectServiceDeprecatedComponents                 | If not found, skip this   solution.                                                          |
| FieldServiceCommon                                 | Required for dual-write with   Dynamics 365 Finance or Dynamics 365 Supply Chain Management. |
| msdyn_AssetCommon                                  | Required for dual-write with   Dynamics 365 Finance or Dynamics 365 Supply Chain Management. |
| msdyn_TESA_Anchor                                  | Required for Dynamics 365 Field   Service.                                                   |
| msdyn_TESA_Patch                                   | Required for Dynamics 365 Field   Service.                                                   |
| msdyn_TESA                                         | Required for Dynamics 365 Field   Service.                                                   |
| ResourceSchedulingControls                         | Required for Dynamics 365 Field   Service.                                                   |
| MicrosoftDynamicsScheduling3_CumulativePatch       | Required for Dynamics 365 Field   Service.                                                   |
| MicrosoftDynamicsScheduling_Patch_xx               | Required for Dynamics 365 Field   Service.                                                   |
| MicrosoftDynamicsScheduling                        | Required for Dynamics 365 Field   Service.                                                   |
| Dynamics365FinanceAndOperationsAnchor              | If not found, skip this   solution.                                                          |
| Dynamics365Notes                                   | If not found, skip this   solution.                                                          |
| Dynamics365FinanceAndOperationsDualWriteEntityMaps | If not found, skip this   solution.                                                          |
| DualWriteCore                                      | If not found, skip this   solution.                                                          |
| Dynamics365AssetManagementApp                      | If not found, skip this   solution.                                                          |
| Dynamics365AssetManagement                         | If not found, skip this   solution.                                                          |
| Dynamics365SupplyChainExtended                     | If not found, skip this   solution.                                                          |
| Dynamics365FinanceExtended                         | If not found, skip this   solution.                                                          |
| HCMCommon                                          | If not found, skip this   solution.                                                          |
| Dynamics365FinanceAndOperationsCommon              | If not found, skip this   solution.                                                          |
| Party                                              | If not found, skip this   solution.                                                          |
| Dynamics365Company                                 | If not found, skip this   solution.                                                          |
| CurrencyExchangeRates                              | If not found, skip this   solution.                                                          |
| AssetCommon                                        | If not found, skip this   solution.                                    
