---
title: Set up subcontractors as bookable resources
description: This topic covers the creation and maintenance of subcontractor resources from users and contacts in the system so they can be associated with Subcontracts in Project Operations.
author: rumant
ms.date: 07/28/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Set up subcontractors as bookable resources

_**Applies To:** Lite deployment - deal to proforma invoicing_


Complete the following steps to set up subcontractors as bookable resources in Dynamics 365 Project Operations.

1. Go to **Project** > **Resources** and select **New**.
2. On the **New Bookable Resource** page, in the **Resource Type** field, select one of the following options:

    - **User**: Select this resource type if the subcontractor will need to access Project Operations to enter time or exenses. If you select this option, the subcontractor will need a valid license to access the system. 
    - **Contact** or **Account**: Select one of these options if the subcontractor doesn't need access to Project Operations, but must be available for task assignments or bookings on projects.
    
    > [!NOTE]
    >  There is no difference between the resource types **Contact** and **Account** in that bookable resources with this resource type can't access the system. However, select **Account** to represent the company of the vendor as a bookable resource. Select **Contact** to represent the individual employees of the vendor.

3. Depending on the resource type you selected, you will be prompted to select the corresponding user, contact, or account record.
4. In the **Type of Worker** field, select the contract worker to set up the subcontractor as a bookable resource.

> [!NOTE]
> If you leave the **Type of Worker** field blank, the system to view the bookable resource as an employee.

5. If you select **Contract Worker**, select the vendor that the resource works for. 
6. Select the time zone of the resource, and then select **Save**. You can also assign a work hour template to this bookable resource by selecting **Set calendar** on the **Bookable Resource** list page.


To associate a bookable resource to a subcontract line, the bookable resource must be:

  - A contract worker
  - If the bookable resource type is **Contact**, they must be associated to the vendor account as a contact. If the bookable resource type is **User**, they don't have to be associated to the vendor account as a contact.
  - The value in the **Vendor** field for the bookable resource must match the value in the **Vendor** field for the subcontract.

## Update the type of worker and vendor mapping for bookable resources

The **Type of Worker** and **Vendor** fields for a bookable resource determine if the bookable resource is a contract worker or an employee and the vendor account that they are associated to. Associating a bookable resource as a contact for a vendor indicates that the contact is an employee of the vendor company. If the **Type of Worker** and **Vendor** fields on a bookable resource are changed, the changes impact any future validations on new records such as time entries, which are created by the bookable resource. Any updates to these fields don't invalidate existing records.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
