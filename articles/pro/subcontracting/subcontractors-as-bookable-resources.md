---
title: Set up subcontractors as bookable resources
description: Learn how to configure subcontractors as bookable resources in Dynamics 365. Follow these steps to ensure accurate vendor and worker type associations.
author: rumant
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: rumant
---

# Set up subcontractors as bookable resources

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Follow these steps to set up subcontractors as bookable resources in Microsoft Dynamics 365 Project Operations.

1. Go to **Project** > **Resources**, and select **New**.
1. On the **New Bookable Resource** page, in the **Resource Type** field, select one of the following options:

    - **User** – Select this resource type if the subcontractor must access Project Operations to enter time or expenses. If you select **User**, the subcontractor needs a valid license to access the system.
    - **Contact** or **Account** – Select one of these resource types if the subcontractor doesn't require access to Project Operations, but must be available for task assignments or bookings on projects. Neither of these resource types provides access to the system. Select **Account** to represent the company of the vendor as a bookable resource. Select **Contact** to represent the individual employees of the vendor.

1. Depending on the resource type that you select, select the corresponding user, account, or contact record.
1. In the **Type of Worker** field, select the "Contract worker" to set up the subcontractor as a bookable resource.

    > [!NOTE]
    > If you leave the **Type of Worker** field blank, the bookable resource is considered as an employee.

1. If you select **Contract Worker** as the type of worker, select the vendor that the resource works for.
1. Select the time zone of the resource, and then select **Save**. To assign a work hour template to the bookable resource, you can select **Set calendar** on the **Bookable Resource** list page.

To associate a subcontract line, a bookable resource must meet these conditions:

- The bookable resource must be a contract worker.
- A bookable resource of the **Contact** resource type must be associated with the vendor account as a contact. A bookable resource of the **User** resource type doesn't need to be associated with the vendor account as a contact.
- The value of the **Vendor** field for the bookable resource must match the value of the **Vendor** field for the subcontract.

## Update the type of worker and vendor mapping for bookable resources

The **Type of worker** field for a bookable resource determines whether the bookable resource is a contract worker or an employee. The **Vendor** field defines the vendor account that the bookable resource is associated with. By associating a bookable resource with a vendor as a contact, you indicate that the contact is an employee of the vendor company.

If you change the **Type of Worker** and **Vendor** fields for a bookable resource, the changes affect any future validations on new records that the bookable resource creates, such as time entries. However, the changes don't invalidate existing records.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
