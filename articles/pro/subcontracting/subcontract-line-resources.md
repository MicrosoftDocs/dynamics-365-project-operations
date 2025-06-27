---
title: Subcontract line resources
description: This article explains how to specify the dedicated resources that are provided by the vendor for a specific subcontract line for time.
author: rumant
ms.date: 12/15/2023
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract line resources

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

In Dynamics 365 Project Operations, a vendor can specify resources that will be used to supply the resource capacity being purchased on the subcontract line for time.

## Create subcontract line resources

To create subcontract line resources, complete the following steps.

1. On the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
2. Open the subcontract line for time on which you want to specify vendor resources.
3. On the **Subcontract Line Resources** tab, in the subgrid, select **+ New Subcontract Line Resource**.
4. On the **New Subcontract Line Resource** page, enter the required information and then select **Save and Close**.

The following table explains the fields on the subcontract line resource.

| Field | Description | Functional impact |
| ----- | ----------- | ----------------- |
| Bookable Resource | Select a bookable resource of **Contract worker** type that you want to use as the resource on the subcontract line.| If you haven't created a bookable resource for the contract worker, leave this field empty. A bookable resource will be created when you save the record.  |
| Contact | You can create your subcontract line resource from an existing contact. Use the lookup to view the list of active contacts in the system. Select a contact for the vendor of this subcontract. If the contact you selected is not a valid contact for the vendor on the subcontract, the subcontract line resource record won't be saved.| If there is no bookable resource for the selected contact, the system creates a bookable resource for the selected contact before creating the subcontract line resource. |
| User | You can create a subcontract line resource by selecting an active user. Use the lookup to view the list of active users in the system.| If there is no bookable resource for the selected user, the system creates a bookable resource for the selected user before the subcontract line resource is created. |
| Start Date | The date that the subcontract worker's assignment will start.| If this resource is booked for a period that falls before this date range, a warning will occur. |
| End Date | The date that the subcontract worker's assignment is finished.| If this resource is booked for a period that falls after this date range, a warning will occur. |
| Effort | The total number of effort hours the contracted worker will spend on this subcontract line.| If this resource is booked beyond the effort that is allocated on this subcontract, a warning will occur. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
