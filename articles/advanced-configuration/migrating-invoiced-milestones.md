---
title: Migrate fully invoiced billing milestones at cutover
description: This article explains how to migrate fixed-priced billing milestones that have been invoiced to the customer for open project contracts before the go-live date.
author: ryansandness
ms.author: ryansandness
ms.date: 05/24/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Migrate fully invoiced billing milestones at cutover

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

## Scenario

Contoso is going live with Microsoft Dynamics 365 Project Operations Integrated with ERP scenarios. As part of the cutover activities, the implementation team must migrate open project contracts from the old system. Some of the project contracts include contract lines that use the fixed-price billing method and have already been partially invoiced to the end customer. The implementation team must migrate these billing milestones as **Customer invoice posted**, because they must be included in the total contract value for revenue recognition purposes. However, customer balances in Accounts receivable and General ledger must not be affected.

## Solution

### Prerequisites

- Dynamics 365 Finance 10.0.24 or later must be installed.
- The environment where the migration steps will be completed must be in maintenance mode. No other activities should be performed while the milestones are being migrated.
- The migration steps must be followed exactly as described here and can be used only for the cutover activity. Microsoft supports no other use of this capability.

### Create a cutover version of the Project Operations integration contract line milestones dual-write map 

1. Make sure that the target mapping for the **Project Operations integration contract line milestones** entity is up to date. 

    1. In Finance, go to **Data Management** \> **Data entities**, and select the **Project Operations integration contract line milestones** entity. 
    2. Select **Modify target mappings**. 
    3. On the **Map staging to target** page, select **Generate mapping**, and then confirm that you want to generate the mapping.

2. Stop and refresh the **Project Operations integration contract line milestones** (**msdyn\_contractlinescheduleofvalues**) dual-write map. 

    1. Go to **Data management** \> **Dual-write**, select the map, and open its details. 
    2. Select **Stop**, and wait until system stops the map. 
    3. Select **Refresh tables**.

3. Add a mapping for the transaction status.

    1. Select **Add mapping**.
    2. On the new line, in the **Finance and operations apps** column, select the **TRANSSTATUS \[TRANSSTATUS\]** field.
    3. In the **Microsoft Dataverse** column, select **msdyn\_invoicestatus \[Invoice status\]**.
    4. In the **Map type** column, select the right arrow (**\>**).
    5. In the dialog box that appears, in the **Sync direction** field, select **Dataverse to Finance and Operations apps**.
    6. Select **Add transform**.
    7. In the **Transform type** field, select **ValueMap**.
    8. Select **Add value mapping**.
    9. In the left field, enter **4**. In the right field, enter **192350001**. 
    10. Select **Save**, and then close the dialog box.

4. Select **Save as** to save the version of the dual-write map. 
5. In the **Add table** pane, in the **Publisher** field, select **Default publisher**.
6. In the **Version** field, enter the version.
7. In the **Description** field, enter a note about this cutover version of the map. 
8. Select **Save**.
9. Start the map.

### Migrate invoiced milestones to the Dataverse environment

1. In the Project Operations Dataverse environment, create milestones that have an invoice status of **Ready for invoicing**. At this point, don't migrate any milestones that haven't been invoiced.

    > [!NOTE]
    > Before you migrate the billing milestones, make sure that the financial dimensions that are related to the project contract line are set as expected. Financial dimensions can't be edited after the migration is completed.

2. After all the milestones are migrated, stop the following dual-write maps:

    - Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
    - Project Operations integration actuals (msdyn\_actuals)
    - Project invoice proposal V2 (invoices)

    To stop the maps, follow these steps:

    1. In Finance, go to **Data management** \> **Dual-write**, select a map, and open its details.
    2. Select **Stop**, and wait until the system stops the map.

3. In the Project Operations Dataverse environment, create and confirm pro-forma invoices for the billing milestones. 

    1. In the site map, go to the project contracts, select the contracts, and then select **Create invoices**.
    2. After the invoices are created, open them from the **Invoices** menu in the site map, and then select **Confirm**.

    This step creates the required records in the Dataverse environment. However, it doesn't affect financials and accounts receivable, because the previously listed dual-write maps were stopped.

4. After all the pro-forma invoices are confirmed, return all dual-write maps to their initial state.

    1. Update the version of the **Project Operations integration contract line milestones** (**msdyn\_contractlinescheduleofvalues**) dual-write map back to the original. 
    2. Select the dual-write map in the map list, select **Table map version**, and then select the original version of the table map.
    3. Select **Save**.
    4. Restart the following dual-write maps:

        - Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
        - Project Operations integration actuals (msdyn\_actuals)
        - Project invoice proposal V2 (invoices)

The milestones are now migrated, and the system is ready for the next steps in the cutover activity.
