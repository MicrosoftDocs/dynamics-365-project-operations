---
title: Subcontract line resources
description: This topic explains how to specify the dedicated resources that are provided by the vendor for a specific subcontract line for time.
author: rumant
ms.date: 08/06/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Subcontract line resources

[!include [banner](../../includes/dataverse-preview.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, a vendor can specify resources that will be used to supply the resource capacity being purchased on the subcontract line for time.

## Create subcontract line resources

To create subcontract line resources, complete the following steps.

1. On the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
2. Open the subcontract line for time on which you want to specify vendor resources.
3. On the **Subcontract Line Resources** tab, in the subgrid, select **+ New Subcontract Line Resource**.
4. On the **New Subcontract Line Milestone** page, enter the required information and then select **Save and Close**.

The following table explains the fields on the subcontract line resource.

| Field |  Description |
| ----- | ------------ |
| Bookable Resource | Select a bookable resource of "Contract worker" type that you want to use as the resource on the subcontract line. If you haven't created a bookable resource for the contract worker yet, leave this field empty. A bookable resource is created when you save the record.  |
| Contact | If you have left the **Bookable Resource** field empty, you can create your subcontract line resource from an existing contact. Use the lookup to view the list of active contacts in the system. Select a contact for the vendor of this subcontract. The contact you select is validated when you save the record. If the contact you selected isn't a valid contact, your record won't save. If there is no bookable resource for the selected contact, the system creates a bookable resource for the selected contact before creating the subcontract line resource. |
| User | If you have left the **Bookable Resource** field empty, you can create a subcontract line resource by selecting an active user. Use the lookup to view the list of active users in the system. If there is no bookable resource for the selected user, the system creates a bookable resource for the selected user beforethe subcontract line resource is created. |
| Start Date | The date that the subcontract worker's assignment will start. If this resource is booked for a period that falls before this date range, a warning will occur. |
| End Date | The date that the subcontract worker's assignment is finished. If this resource is booked for a period that falls after this date range, a wanring will occur. |
| Effort | The total number of effort hours the subcontract worker will spend on this subcontract line. If this resource is booked beyond the effort they are allocated to on this subcontract, a warning will occur. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
