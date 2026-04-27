---
title: Migrate fully invoiced billing milestones at cutover
description: This article explains how to migrate fixed-priced billing milestones that have been invoiced to the customer for open project contracts before the go-live date.
author: ryansandness
ms.author: ryansandness
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Migrate fully invoiced billing milestones at cutover

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

## Scenario

Contoso is going live with Microsoft Dynamics 365 Project Operations Integrated with ERP scenarios. As part of the cutover activities, the implementation team must migrate open project contracts from the old system. Some of the project contracts include contract lines that use the fixed-price billing method and are already partially invoiced to the end customer. The implementation team must migrate these billing milestones as **Customer invoice posted**, because they must be included in the total contract value for revenue recognition purposes. However, customer balances in Accounts receivable and General ledger must not be affected.

## Solution

### Prerequisites

- Dynamics 365 Finance 10.0.24 or later must be installed.
- The environment where you complete the migration steps must be in maintenance mode. No other activities should be performed while the milestones are being migrated.
- Follow the migration steps exactly as described in this article. Use these steps only for the cutover activity. Microsoft supports no other use of this capability.

### Create a cutover version of the Project Operations integration contract line milestones dual-write map 

1. Make sure that the target mapping for the **Project Operations integration contract line milestones** entity is up to date. 

    1. In Finance, go to **Data Management** > **Data entities**, and select the **Project Operations integration contract line milestones** entity. 
    1. Select **Modify target mappings**. 
    1. On the **Map staging to target** page, select **Generate mapping**, and then confirm that you want to generate the mapping.

1. Stop and refresh the **Project Operations integration contract line milestones** (**msdyn_contractlinescheduleofvalues**) dual-write map. 

    1. Go to **Data management** > **Dual-write**, select the map, and open its details. 
    1. Select **Stop**, and wait until the system stops the map. 
    1. Select **Refresh tables**.

1. Add a mapping for the transaction status.

    1. Select **Add mapping**.
    1. On the new line, in the **Finance and operations apps** column, select the **TRANSSTATUS [TRANSSTATUS]** field.
    1. In the **Microsoft Dataverse** column, select **msdyn_invoicestatus [Invoice status]**.
    1. In the **Map type** column, select the right arrow (**>**).
    1. In the dialog box that appears, in the **Sync direction** field, select **Dataverse to Finance and Operations apps**.
    1. Select **Add transform**.
    1. In the **Transform type** field, select **ValueMap**.
    1. Select **Add value mapping**.
    1. In the left field, enter **4**. In the right field, enter **192350001**. 
    1. Select **Save**, and then close the dialog box.

1. Select **Save as** to save the version of the dual-write map. 
1. In the **Add table** pane, in the **Publisher** field, select **Default publisher**.
1. In the **Version** field, enter the version.
1. In the **Description** field, enter a note about this cutover version of the map. 
1. Select **Save**.
1. Start the map.

### Migrate invoiced milestones to the Dataverse environment

1. In the Project Operations Dataverse environment, create milestones that have an invoice status of **Ready for invoicing**. At this point, don't migrate any milestones that aren't invoiced.

    > [!NOTE]
    > Before you migrate the billing milestones, make sure that the financial dimensions related to the project contract line are set as expected. You can't edit financial dimensions after the migration is completed.

1. After you migrate all the milestones, stop the following dual-write maps:

    - Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
    - Project Operations integration actuals (msdyn\_actuals)
    - Project invoice proposal V2 (invoices)

    To stop the maps, follow these steps:

    1. In Finance, go to **Data management** \> **Dual-write**, select a map, and open its details.
    1. Select **Stop**, and wait until the system stops the map.

1. In the Project Operations Dataverse environment, create and confirm pro-forma invoices for the billing milestones. 

    1. In the site map, go to the project contracts, select the contracts, and then select **Create invoices**.
    1. After the invoices are created, open them from the **Invoices** menu in the site map, and then select **Confirm**.

    This step creates the required records in the Dataverse environment. However, it doesn't affect financials and accounts receivable, because the previously listed dual-write maps are stopped.

1. After you confirm all the pro-forma invoices, return all dual-write maps to their initial state.

    1. Update the version of the **Project Operations integration contract line milestones** (**msdyn\_contractlinescheduleofvalues**) dual-write map back to the original. 
    1. Select the dual-write map in the map list, select **Table map version**, and then select the original version of the table map.
    1. Select **Save**.
    1. Restart the following dual-write maps:

        - Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
        - Project Operations integration actuals (msdyn\_actuals)
        - Project invoice proposal V2 (invoices)

You migrated the milestones, and the system is ready for the next steps in the cutover activity.
