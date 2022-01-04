---
title: Migrate fully invoiced billing milestones at cutover
description: This topic provides step by step tutorial of migrating open project contracts fixed priced billing milestones, that have been invoiced to the customer before the go-live date.
author: sigitac
ms.date: 01/04/2022
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Migrate fully invoiced billing milestones at cutover

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Scenario

Contoso is going live with Project Operations for resource/ non-stocked scenarios. As a part of cutover activities, implementation team must migrate open project contracts from the legacy system. Some project contracts include contract lines with the fixed price billing method and are already partially invoiced to the end customer(s). Implementation team needs to migrate such billing milestones as &quot;Customer invoice posted&quot; as they must be included into the total contract value for revenue recognition purposes, but customer balances in Accounts receivable and General Ledger must not be impacted.

## Solution

### Prerequisites

- Dynamics 365 Finance and Operations environment must be version 10.0.24 or higher.
- Environment where activity below is performed must be in the maintenance mode. No other users/ activity must be performed while migrating the milestones.
- Migration steps must be followed exactly as described and can be used only for the cutover activity. Using this capability in any other way is not supported by Microsoft.

### Create a cutover version of Project Operations integration contract line milestones dual-write map

1. Ensure Project Operations integration contract line milestones entity has up to date target mapping. In Finance and Operations environment navigate to Data Management \&gt; Data entities and select Project Operations integration contract line milestones entity. Click button Modify target mappings. In the Map staging to target form click Generate mapping and confirm the dialog.
2. Stop and refresh Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues) dual-write map. Navigate to Data management \&gt; Dual-write, select the map and open it&#39;s details. Click the Stop button and wait until system stops the map. Then click Refresh tables button.
3. Add mapping for transaction status:
  1. Click Add mapping button.
  2. In the new line select TRANSSTATUS [TRANSSTATUS] field in the Finance and Operations apps column.
  3. Select msdyn\_invoicestatus [Invoice status] on the Microsoft Dataverse column.
  4. Click on the Map type column and select Sync direction Dataverse to Finance and Operations apps, Transform type ValueMap and set value 4 on the left field (Finance and Operations apps) and 192350001 on the right field (Dataverse). Save and close the transform dialog.
4. Save dual-write map version using Save as button. Select Default publisher, Version and in the description note this is Cutover version of the map. Start the map.

### Migrate invoiced milestones to the Dataverse environment

1. Create milestones in the Project Operations Dataverse environment with the Invoice status &quot;Ready for invoicing&quot;. Do not migrate any un-invoiced milestones at this step. Make sure Project contract line related financial dimensions are set as expected before migrating the billing milestones, as it won&#39;t be possible to edit them after the migration.
2. Once all milestones are migrated, stop the following dual-write maps:
  1. Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
  2. Project Operations integration actuals (msdyn\_actuals)
  3. Project invoice proposal V2 (invoices)

To stop the map, navigate to Data management \&gt; Dual-write, select the map and open it&#39;s details. Click the Stop button and wait until system stops the map.

1. Create and confirm proforma invoices for the billing milestones on the Project Operations Dataverse environment. You can create the invoices by navigating to the Project contracts in sitemap, multi-selecting the contracts and clicking Create invoices button. Once invoices are created, they can be opened from the Invoices menu on the site map and confirmed using Confirm button. Note that this step will create required records in the Dataverse environment but will not impact financials and accounts receivable, as dual-write maps above are stopped.

1. Once all proforma invoices are confirmed, return all dual-write maps to their initial state:

  1. Update Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues) dual-write map version back to original. Select the dual-write map in the map list, click Table map version button, select original table map version and Save.
  2. Restart all the following dual-write maps:
    1. Project Operations integration contract line milestones (msdyn\_contractlinescheduleofvalues)
    2. Project Operations integration actuals (msdyn\_actuals)
    3. Project invoice proposal V2 (invoices)

Now, the milestones are migrated and system is ready for the next steps in the cutover activity.
