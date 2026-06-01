---
title: Subcontract line resources
description: Learn how to assign vendor resources to subcontract lines in Dynamics 365 Project Operations. Follow our guide to ensure accurate resource tracking.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Subcontract line resources

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

In Dynamics 365 Project Operations, a vendor can specify resources that supply the resource capacity they're purchasing on the subcontract line for time.

## Create subcontract line resources

To create subcontract line resources, complete the following steps.

1. On the navigation pane, select **Subcontracts** and open the subcontract you want to work with.
1. Open the subcontract line for time on which you want to specify vendor resources.
1. On the **Subcontract Line Resources** tab, in the subgrid, select **+ New Subcontract Line Resource**.
1. On the **New Subcontract Line Resource** page, enter the required information and then select **Save and Close**.

The following table explains the fields on the subcontract line resource.

| Field | Description | Functional impact |
| ----- | ----------- | ----------------- |
| Bookable Resource | Select a bookable resource of **Contract worker** type that you want to use as the resource on the subcontract line.| If you don't create a bookable resource for the contract worker, leave this field empty. The system creates a bookable resource when you save the record.  |
| Contact | Create your subcontract line resource from an existing contact. Use the lookup to view the list of active contacts in the system. Select a contact for the vendor of this subcontract. If the contact you selected isn't a valid contact for the vendor on the subcontract, the system doesn't save the subcontract line resource.| If there's no bookable resource for the selected contact, the system creates a bookable resource for the selected contact before creating the subcontract line resource. |
| User | Create a subcontract line resource by selecting an active user. Use the lookup to view the list of active users in the system.| If there's no bookable resource for the selected user, the system creates a bookable resource for the selected user before the subcontract line resource is created. |
| Start Date | The date that the subcontract worker's assignment starts.| If you book this resource for a period that falls before this date range, a warning occurs. |
| End Date | The date that the subcontract worker's assignment finishes.| If you book this resource for a period that falls after this date range, a warning occurs. |
| Effort | The total number of effort hours the contracted worker spends on this subcontract line.| If you book this resource beyond the effort that you allocated on this subcontract, a warning occurs. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
