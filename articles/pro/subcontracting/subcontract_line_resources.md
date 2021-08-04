---
title: Subcontract line resources
description: This topic provides information that will help you specify dedicated resources that will be provided by the vendor for a specific subcontract line for time.
author: rumant
ms.date: 08/02/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract line resources

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Project Operations, **a subcontract line for time** allows a vendor to specify resources that will be used to supply the resource capacity being purchased on the line.

## Creating subcontract line resources

To create a subcontract line resources, complete the following steps.

1. Open the subcontract line for time on which you want to specify vendor resources.
2. On the  **Subcontract line resources**  tab, on the sub grid, select  **+ New Subcontract line resource**.
3. On the New Subcontract line milestone page, enter the required information and click Save and close.

The following table explains the fields on the Subcontract line resources and their downstream impact.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Resource | Quick create and Subcontract line resource details page | A look up of all the Active Bookable Resources that are contract workers. If you have not created a Bookable resource for the subcontract worker yet, you can leave this field empty, and the system will create a bookable resource on save of this record. | |
| Contact | Quick create and Subcontract line resource details page | If you have left the Bookable resource field empty, you can create your subcontract line resource from one of the contacts in your system. This field lookup will show a list of active contacts in the system. Make sure to pick a contact for the vendor of this subcontract. This will be validated on save and the save will fail if the contact chose is not a valid contact of the vendor on the subcontract | If there is no Bookable resource for the selected contact, the system will create a Bookable resource for the selected contact before creating the subcontract line resource |
| User | Quick create and Subcontract line resource details page | If you have left the Bookable resource field empty, you can also create your subcontract line resource from one of the active users in your system. This field lookup will show a list of active users in the system. | If there is no Bookable resource for the selected user, the system will create a Bookable resource for the selected user before creating the subcontract line resource |
| Start Date | Quick create and Subcontract line resource details page | Date when the subcontract worker will be starting their assignment | This will be used to show warnings when this resource is being booked for a period that falls before this date range* |
| End Date | Quick create and Subcontract line resource details page | Date when the subcontract worker will be ending their assignment | This will be used to show warnings when this resource is being booked for a period that falls before this date range* |
| Effort | Quick create and Subcontract line resource details page | Total number of effort hours the subcontract worker will be spending on this subcontract line | This will be used to show warnings when this resource is being booked beyond the capacity they are allocated to on this subcontract* |

*See Subcontracting in Project Operations - Early Access Scope

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
