---
title: Migrate fully invoiced billing milestones at cutover
description: This topic provides information about how to migrate open project contracts fixed priced billing milestones that have been invoiced to the customer before the go-live date.
author: sigitac
ms.date: 01/07/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Migrate fully invoiced billing milestones at cutover

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Scenario

Contoso is going live with Project Operations for resource/non-stocked scenarios. As a part of cutover activities, the implementation team must migrate open project contracts from the legacy system. Some project contracts include contract lines with the fixed-price billing method and are already partially invoiced to the end customer. The implementation team needs to migrate these billing milestones as **Customer invoice posted** because they must be included into the total contract value for revenue recognition purposes. However, customer balances in **Accounts receivable** and **General ledger** must not be impacted.

## Solution

### Prerequisites

- Dynamics 365 Finance 10.0.24 or higher must be installed.
- The environment where these steps will be completed must be in the maintenance mode. No other activities should be performed while migrating the milestones.
- The migration steps must be followed exactly as described and can be used only for the cutover activity. Using this capability in any other way isn't supported by Microsoft.

### Create a cutover version of the Project Operations integration contract line milestones dual-write map

1. Ensure that the target mapping for the Project Operations integration contract line milestones entity is up-to-date. 

   1. In Finance, go to **Data Management** > **Data entities** and select the **Project Operations integration contract line milestones** entity. 
   2. Select **Modify target mappings**. 
   3. On the **Map staging to target** page, select **Generate mapping** and then confirm.

2. Stop and refresh the Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues) dual-write map. 

   1. Go to **Data management** > **Dual-write**,  select the map and open it's details. 
   2. Select **Stop** and wait until system stops the map. 
   3. Select **Refresh tables**.

3. Add mapping for transaction status.
   1. Select **Add mapping**.
   2. In the new line, in the **Finance and Operations apps** column, select the **TRANSSTATUS [TRANSSTATUS]** field.
   3. In the **Microsoft Dataverse** column, select **msdyn\_invoicestatus [Invoice status]**.
   4. In the **Map type** column, select **>** and in the dialog box, in the **Sync direction** field, select **Dataverse to Finance and Operations apps**.
   5. Select **Add transform** and in the **Transform type** field, select **ValueMap**.
   6. Select **Add value mapping**. In the left field, enter **4** and in the right field, enter **192350001**. 
   7. Select **Save** and then close the dialog box.

4. Select **Save as** to save the dual-write map version. 
5. In the **Add table** pane, in the **Publisher** field, select **Default publisher**.
6. In the **Version** field, enter the version and in the **Description** field make a note about this Cutover version of the map. 
7. Select **Save**.
8. Start the map.

### Migrate invoiced milestones to the Dataverse environment

1. Create milestones in the Project Operations Dataverse environment with the invoice status **Ready for invoicing**. At this point, don't migrate any milestones that haven't been invoiced. Make sure that the financial dimensions related to the project contract line are set as expected before you migrate the billing milestones. Financial dimemsions can't be edited after the migration.
2. After all milestones are migrated, stop the following dual-write maps:
  1. Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
  2. Project Operations integration actuals (msdyn\_actuals)
  3. Project invoice proposal V2 (invoices)

3. To stop the maps, go to **Data management** > **Dual-write**, and select the map. 
4. Open the map details and select **Stop**. Wait until system stops the map.
5. Create and confirm proforma invoices for the billing milestones on the Project Operations Dataverse environment. You can create the invoices by navigating to the Project contracts in sitemap, multi-selecting the contracts and clicking Create invoices button. Once invoices are created, they can be opened from the Invoices menu on the site map and confirmed using Confirm button. Note that this step will create required records in the Dataverse environment but will not impact financials and accounts receivable, as dual-write maps above are stopped.
6. After all of the proforma invoices are confirmed, return all dual-write maps to their initial state.

  1. Update the Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues) dual-write map version back to the original. 
  2. Select the dual-write map in the map list, select **Table map version**, and then select the original table map version.
  3. Select **Save**.
  4. Restart the following dual-write maps:
    - Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
    - Project Operations integration actuals (msdyn\_actuals)
    - Project invoice proposal V2 (invoices)

The milestones are now migrated and the system is ready for the next steps in the cutover activity.
