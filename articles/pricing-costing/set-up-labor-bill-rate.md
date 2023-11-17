---
title: Set up labor bill rates
description: This article provides information about how to set up labor billing rates in Project Operations.
author: avisness
ms.date: 11/18/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: avisness
---

# Set up labor bill rates

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios

Each price list has a set of role prices, or labor rates, that are effective for the context and date effectivity included on the price list header. Bill rates for time in Dynamics 365 Project Operations can be set up in only one currency, which is the currency on the Price list header.

1. To set up labor bill rates for a sales price list, go to **Sales** > **Customers** > **Price Lists**, and select **New** to create a new price list. 
2. On the **Role Prices** tab, in the subgrid, select **New Role Price**. 
3. On the **Quick Create** pane, enter the role and organization unit combination for which you need to set up the bill rate.

   The following table includes the fields on the **General** tab and the **Quick Create** pane of a role price line that you need keep in mind as you create role prices on a sales price list:

    | Field | Location | Description | Downstream impact |
    | --- | --- | --- | --- |
    | Role | **General** tab and **Quick Create** pane | Select the role that you are setting the bill rate for. | Role on the incoming estimate or actual will be matched against this line to default bill rate of the role. |
    | Resourcing Company | **General** tab and **Quick Create** pane | Select the company or legal entity that the role is from. For example, a developer from Fabrikam India or a developer from Fabrikam USA. | The resourcing company on the incoming estimate or actual will be matched against this line to default the bill rate of the role. |
    | Resourcing Unit | **General** tab and **Quick Create** pane | Select the organizational unit or division of the company that the role is from. For example, a developer from the Robotics division of Fabrikam India or a developer from the Software division of Fabrikam USA. | The resourcing unit on the incoming estimate or actual will be matched against this line to default the bill rate of the role. |
    | Price | **General** tab and **Quick Create** pane | Set up the bill rate for the role resourcing company and resourcing unit combination. For example, a developer from Fabrikam India has a bill rate of 100 USD or a developer from Fabrikam USA has a bill rate of 150 USD. | This price is the default bill rate on the per unit price of the incoming estimate or actual line for Time transaction class. |
    | Currency | **General** tab and **Quick Create** pane| By default, the currency value comes from the currency on the sales price list header. On a sales price list, the currency can't be overridden. | This currency is the default currency on the per unit price of the incoming actual sales line for Time transaction class. |
    | Unit Schedule | **General** tab and **Quick Create** pane | This unit schedule defaults to Time and can't be changed on the Role price entity because it's used to express rates by units of time. | There is no downstream impact for this field. |
    | Unit | **General** tab and **Quick Create** pane | The unit value comes from the **Time Unit** field on the sales price list header. But the value can be overridden. For example, a developer from Fabrikam India has bill rate of 1000 USD per **India Day**. A developer from Fabrikam USA has a bill rate of 1500 USD per **US Day**. | When the per unit price defaults on an incoming estimate or actual line, the system uses the system of units and conversion in base units to calculate a per unit price. For example, the estimate is for 10 **India Days** worth of work for a Developer from India, and the unit India Day is defined as 10 hours. When pricing that estimate line, the application calculates the unit price on the estimate as 1000 USD/10 hours = 100 USD per hour. |

## Transfer pricing or set up bill rates for resources from other organizational units or divisions 

Project-based companies often use employees from different legal entities and different divisions within the legal entity to work on projects. Projects can be executed from a certain legal entity and division while the employees or consultants that work on the projects could come from the same legal entity and division or from a different one. The project could also be made up of a combination of people from different legal entities and divisions. In Project Operations, the legal entity that owns the delivery of the project is called the **Owning Company** and division that owns the delivery is called the **Contracting Unit**. All the other legal entities that provide resources are called **Resourcing Companies** and the divisions that provide resources are called **Resourcing Units**. Because of the differences in labor costs across various geographies and labor markets across the world, bill rates for labor are also set up differently for different geographies.

For example, a developer from the Robotics division of Fabrikam India working on US project is billed at the rate of 100 USD per hour. A developer from the Robotics division of Fabrikam US working on US Project is billed at 150 USD per hour. 

### Example: Set up a bill rate 

1. Create a sales price list called *Fabrikam US Bill Rates* and set the date effectivity.
2. In the sales price list, enter the following rate information:

    | Role | Resourcing company | Resourcing unit | Bill rate |
    | --- | --- | --- | --- |
    | Developer | Fabrikam India | Fabrikam India - Robotics | $100 |
    | Developer | Fabrikam Philippines | Fabrikam Philippines - Robotics | $90 |
    | Developer | Fabrikam US | Fabrikam US - Robotics | $150 |

3. Attach the sales price list, **Fabrikam US Bill rates** to the project price list of the project contract or to a certain account.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
