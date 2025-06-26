---
title: Set up labor cost rates - Core deployment
description: This article provides information about how to set up the cost rates for labor in Project Operations.
author: abriccetti
ms.author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up labor cost rates - Core deployment

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Core deployment - deal to proforma invoicing_

Each price list has a set of labor rates (role prices) that align with the content and date effectivity of the price list.

1. Create a price list and on the **Role Price** tab, in the subgrid, select **New Role**.
2. On the **Quick Create** page, select the role and organization unit.
3. Enter any other required field information.

The following table includes some of the fields that are important when creating labor rates on a cost price list.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Role | **General** tab and **Quick Create** pages | Select the role that the cost rate applies to. | The role on the incoming estimate or actual matches against this line to default the cost of the role. |
| Resourcing Unit | **General** tab and **Quick Create** pages | Select the organizational unit or division of the company from where this role is used. For example, a developer from the Robotics division of Fabrikam India or a developer from the Software division of Fabrikam USA. | The resourcing unit on the incoming estimate or actual matches against this line to default the cost of the role. |
| Price | **General** tab and **Quick Create** pages | Set up the cost rate for the role, resourcing company, and resourcing unit combination. For example, a developer from Fabrikam India costs 1000 INR or a developer from Fabrikam USA costs 150 USD. | The price is the cost rate that defaults on the per unit cost of the incoming estimate or actual line for **Time** transaction class. |
| Currency | **General** tab and **Quick Create** pages | By default, the currency value comes from the currency on the header of the cost price list but can be overridden. For example, a developer from Fabrikam India costs 1000 INR. A developer from Fabrikam USA costs 150 USD. | This currency defaults on the per unit cost of the incoming actual cost line for the **Time** transaction class. On a project estimate, the currency value is converted to the project currency and shown on the Time-phased view of the estimate. |
| Unit Schedule | **General** tab and **Quick Create** pages | The unit schedule defaults to Time and can't be changed on the Role price entity because it's used express rates by units of time. | There's no downstream impact. |
| Unit | **General** tab and **Quick Create** pages | By default, the value comes from the **Time Unit** field on the header of the cost price list. The value can be overridden. For example, a developer from Fabrikam India costs 1000 INR per **India Day**. A developer from Fabrikam USA costs 150 USD per **US Day**. | The system uses the system of units and conversion in base units to compute a per unit cost to calculate the default price per unit on an incoming estimate or actual line. For example, an estimate is for 10 **India Days** worth of work for a developer from India, and the unit, **India Day** is defined as 10 hours. When costing that estimate line, the application calculates the unit cost on the estimate as: 1000 INR/ 10 hours = 100 INR per hour, which is converted into USD and shown as the unit cost on the **Project Estimates** page. |

## Transfer pricing and costs for resources outside of your division or legal entity

In project-based companies, it's common to use employees from different legal entities or divisions on projects. A project can be executed by one legal entity, but the employees or consultants that work on the project could come from the same legal entity or from a different one, or there may be a combination of both. In Dynamics 365 Project Operations, the legal entity that owns the delivery of the project is the **Owning Company** and the division that owns the delivery is the **Contracting Unit**. Other legal entities that provide resources are the **Resourcing companies** and divisions that provide resources are the **Resourcing Units**. In most countries/regions, companies are required to ensure that the resourcing legal entity or division, charge the owning company and the contracting unit for the use of resources.

For example, the Fabrikam corporation must ensure that Fabrikam India-Robotics has a negotiated a cost rate card with Fabrikam US-Robotics or Fabrikam UK-Robotics.

A developer from Fabrikam India-Robotic charges $100 when lent to Fabrikam US-Robotics and $150 when lent to Fabrikam U-Robotics.

### Set up costs for outside resources

1. Create a cost price list called, *Fabrikam US-Robotics cost rates* and set a date effective range.
2. In the cost price list, set up rates using information from the following table. 

| Role | Resourcing Company | Resourcing Unit | Cost rate |
| --- | --- | --- | --- |
| Developer | Fabrikam India | Fabrikam India-Robotics | $100 |
| Developer | Fabrikam Philippines | Fabrikam Philippines-Robotics | $90 |
| Developer | Fabrikam US | Fabrikam US-Robotics | $150 |

3. Attach this cost price list to the Fabrikam US-Robotics organization unit.

### Set up transfer pricing for a resource in the appropriate currency 

In Project Operations, resource pricing can be set up in any currency. The currency defaults to what is on the price list header, but can be changed.

Using the example for transfer price setup, the information could be changed to:

Fabrikam corporation must ensure that Fabrikam India-Robotics has a negotiated a cost rate with Fabrikam US-Robotics or Fabrikam UK-Robotics.

A developer from Fabrikam India-Robotics costs 5000 INR when lent to Fabrikam US-Robotics and 5500 INR when lent to Fabrikam UK-Robotics.

In the cost price list for Fabrikam US-Robotics, cost rates can be expressed as:

| Role | Resourcing Company | Cost |
| --- | --- | --- |
| Developer | Fabrikam India | 5000 INR |
| Developer | Fabrikam US | 115 USD |

In the cost price list for Fabrikam UK-Robotics, cost rates can be expressed below:

| Role | Resourcing company | Cost |
| --- | --- | --- |
| Developer | Fabrikam India | 5500 INR |
| Developer | Fabrikam UK | 115 GBP |

The cost price list can provide labor rates in multiple currencies. When you generate a cost estimate on the project, Project Operations converts these cost rates into the project currency and display it to the user. When a time entry is approved and a cost actual is created, the cost actual is priced in the currency of that matching role price line on the cost price list. Cost actuals for time on a single project can be recorded in multiple currencies. However, when rolling up or summarizing the actual labor costs at the project level, Project Operations converts all labor cost amounts into the project currency that the user can view.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
