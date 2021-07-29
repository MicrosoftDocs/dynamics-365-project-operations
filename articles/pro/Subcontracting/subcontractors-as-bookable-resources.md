---
title: Set up subcontractors as Bookable Resources
description: This topic covers the creation and maintenance of subcontractor resources from users and contacts in the system so they can be associated with Subcontracts in Project Operations.
author: rumant
ms.date: 07/28/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: rumant
---

# Set up subcontractors as Bookable Resources

_**Applies To:** Lite deployment - deal to proforma invoicing_


The following steps will help you setup subcontractors as Bookable Resources:

1. Navigate to the Bookable Resources list page using Project-\&gt;Resources on Left Navigation
2. The list of Bookable Resources opens. Click &#39;New&#39; from the ribbon.
3. On the New Bookable Resource form, select &quot;Resource Type&quot;. There are many choices in the dropdown list. For setting up subcontractors as bookable resources, the only relevant choices are &#39;User&#39;, &#39;Contact&#39; or &#39;Account&#39;. Depending on the level of access your subcontractors need, you should pick the appropriate choice of Resource Type.
  1. If Subcontractors need to access the Project Operations system to log time or expenses or other information, then pick &#39;User&#39;. This also means that they will need a valid license to access the system.
  2. If Subcontractors do not need to access the Project Operations system but they need to available for task assignments and bookings on projects, then use Resource Type values of &#39;Contact&#39; or &#39;Account&#39; when setting them up.
  3. There is no difference between the choices of &#39;Contact&#39; and &#39;Account&#39; for Resource Type in that bookable resources with this resource type will not be able to access the system. Use Account resource type when you need to represent the company of the vendor as a Bookable resource instead of individual employees of the vendor.
4. Depending on the Resource Type field choice, you will be prompted to select the corresponding user, contact, or account record.
5. In the &quot;Type of Worker&quot; field, make sure to pick the choice of &#39;Contract Worker&#39; when setting up a Subcontractor as a Bookable Resource.

_Note: Blank value for Type of Worker field will lead the system to treat the Bookable resource as an &#39;Employee&#39;_

1. Selecting &#39;Contract Worker&#39; will prompt for selecting a vendor that this resource works for. Vendor field does not appear for when Type of Worker is &#39;Employee&#39;. Select a vendor from the list of vendors shown in dropdown.
2. Select time zone of the resource and save the bookable resource. You can also assign a work hour template for this bookable resource using the &#39;Set calendar&#39; action from the Bookable Resource list page.

Note: To associate a Bookable resource to a Subcontract line, the Bookable resource must be:

- A Contract Worker
- If the Bookable Resource is Contact type, then they must be associated to the Vendor Account as a contact. If the Bookable Resource is User type, then they DO NOT have to be associated to the Vendor Account as a contact
- Vendor field on the Bookable Resource must match the vendor field on Subcontract.

## Updating Type of Worker and Vendor mapping for Bookable Resources

Type of Worker and Vendor fields on a Bookable Resources determine if the Bookable resource is a Contract Worker or an Employee and the Vendor account that they are associated to. Associating a Bookable resource as a contact for a Vendor indicates that the contact is an employee of the vendor company. If the Type of Worker and Vendor fields on a Bookable Resource are changed, then the changes impact any future validations on new records such as time entries etc. created by this Bookable resource. However, updates to these fields will not render any of the already created records invalid.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
