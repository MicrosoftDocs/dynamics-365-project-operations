---
title: Currency mismatch error when creating project, contract, quote or bookable resource
author: sigitac
ms.date: 12/08/2021
ms.topic: article
ms.prod:
ms.reviewer: kfend 
ms.author: sigitac
---

# Currency mismatch error when creating project, contract, quote or bookable resource

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

## Symptoms
System displays a business process error when saving project, contract, quote or bookable resource record: "Owning company currency does not match the contracting unit currency. Pick different owning company or contracting unit to continue".


## Resolution

Verify the currencies:
- Verify the currency of the Contracting unit set for this record. You can see the currency by opening Organizational Unit record from the Settings and verifying Currency field value set in the General tab.
- Verify the currency of the Owning company. You can see the currency by opening Related > Ledgers in the Company record. Double click on the Ledger record associated with this company and verify the Accounting currency field set in the General tab.

If the currency set in the Contracting unit and the currency set in the Ledger record, do not match, adjust the configuration or pick different values when saving the record. System requires these records to match due to ensure correct intercompany invoicing flows. You can read more about the intercompany configurations in [Create intercompany transactions](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-accounting/create-intercompany-transactions) article.

If the Company record has no associated Ledger record, this indicates missing configuration when setting up the environment. Configuration has to be corrected by system administrator.
System administrator must navigate to Dual-write configurations, stop Ledgers dual-write map and restart it with Initial sync of this map and it's prerequisites. More details are available in the [Project Operations Dual-Write map versions](https://docs.microsoft.com/en-us/dynamics365/project-operations/environment/resource-dual-write-maps) article.
