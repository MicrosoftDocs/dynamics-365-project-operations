---
title: Set up labor bill rates Core deployment
description: This article provides information about setting up labor billing rates in Project Operations Core.
author: abriccetti
ms.date: 01/09/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Set up labor bill rates Core deployment

[!INCLUDE[banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Project Operations Core_

Each price list has a set of role prices or labor rates that are effective for the context and date effectivity that are included on the price list header. Bill rates for time in Microsoft Dynamics 365 Project Operations can be set up in only one currency, which is the currency on the price list header.

To set up labor bill rates for a sales price list, follow these steps:

1. Create a price list based on the price list header. 
2. On the **Role Prices** tab, in the subgrid, select **+ New Role Price**. 
3. In the **Quick Create** pane, enter the role and organization unit combination for which you need to set up the bill rate.

The following table shows the fields that appear on the **General** tab and in the **Quick Create** pane for a role price line. Keep these fields in mind as you create role prices on a sales price list.

| Field | Location | Description | Downstream impact |
| --- | --- | --- | --- |
| Role | **General** tab and **Quick Create** pane | Select the role that you're setting the bill rate for. | The role on the incoming estimate or actual is matched against this line to enter the default bill rate of the role. |
| Resourcing Unit | **General** tab and **Quick Create** pane | Select the organizational unit or division of the company that the role is from. Examples include a developer from the Robotics division of Fabrikam India and a developer from the Software division of Fabrikam USA. | The resourcing unit on the incoming estimate or actual is matched against this line to enter the default bill rate of the role. |
| Price Calculation | **General** tab and **Quick Create** pane | Possible values of the **Pricing calculation** or **Pricing method** field are **Price per unit**, **At transaction cost**, and **Markup over transaction cost**. | During price setup, selection of the ***Price per unit** value locks the **Percent** field on the category price line. Selection of **At transaction cost** locks the **Price** and **Percent** fields on the sales price list. Selection of **Markup over transaction cost** locks the **Price** field on the sales price list. On an incoming actual line for an expense, the **At transaction cost** or **Markup over transaction cost** pricing calculation causes the corresponding unbilled sales line to be assigned a price that either equals the price on the cost actual or is calculated as a markup over the cost price. |
| Price | **General** tab and **Quick Create** pane | Set up the bill rate for the role resourcing company and resourcing unit combination. For example, a developer from Fabrikam India has a bill rate of 100 USD or a developer from Fabrikam USA has a bill rate of 150 USD. | This price is the default bill rate on the per unit price of the incoming estimate or actual line for Time transaction class. |
| Percent | **General** tab and **Quick Create** pane | Set up the percentage over cost for the combination of a transaction category and a unit. For example, the role sales rate should be marked up 10 percent over the cost rate. | This percentage over cost is applicable on a sales price list only when the **Markup over transaction cost** pricing method is selected. |
| Currency | **General** tab and **Quick Create** pane| By default, the currency value comes from the currency on the sales price list header. On a sales price list, the currency can't be overridden. | This currency is the default currency on the per unit price of the incoming actual sales line for Time transaction class. |
| Unit Schedule | **General** tab and **Quick Create** pane | By default, this unit schedule is set to **Time** and can't be changed on the Role price entity because it's used to express rates by units of time. | This field has no downstream impact. |
| Unit | **General** tab and **Quick Create** pane | The unit value comes from the **Time Unit** field on the sales price list header. However, the value can be overridden. For example, a developer from Fabrikam India has bill rate of 1,000 USD per India Day. A developer from Fabrikam USA has a bill rate of 1,500 USD per US Day. | When the default per-unit price is entered on an incoming estimate or actual line, the system uses the system of units and conversion in base units to calculate a per-unit price. For example, the estimate is for 10 India Days' worth of work for a developer from India, and the **India Day** unit is defined as 10 hours. When you price that estimate line, the application calculates the unit price on the estimate as 1,000 USD &divide; 10 hours = 100 USD per hour. |

## Pricing methods for labor roles (Preview)

When you set up role prices that are relevant in the context of sales pricing, three pricing methods are supported:

- **Price per unit** – (Default) The sales price of the role is set to the amount that's specified in the **Currency amount** field.
- **At transaction cost** – The sales price of the role is set to the transaction cost of the role.
- **Markup over transaction cost %** – The sales price of the role is calculated as a markup or markdown percentage, based on the transaction cost of the specified role.

## Enable cost plus pricing (Preview)

To use all pricing methods and enable cost plus pricing, follow these steps:

1. Go to **Settings** \> **Parameters**.
2. Open the **Parameters** record.
3. On the Action Pane, on the **Feature control** tab, select **Enable Cost plus pricing**.
4. In the confirmation dialog box, select **OK**.
5. Refresh your browser. This feature is now activated and removed from the selection on the **Feature control** tab.

> [!NOTE]
> After the cost plus pricing feature is enabled, it can't be disabled.

## Price per unit

When the **Price per unit** pricing method is selected on a role price line that's linked to a sales price list, the default price is entered for the combination of a role and a resource unit for an actual. This pricing method is carried through to project estimate lines, quote line details, and contract line details for expenses.

## At transaction cost

When the **At transaction cost** pricing method is selected on the role price line that's linked to a sales price list, the default price is entered for the combination of a role and a resourcing unit for an actual. The unit price is set on the unbilled sales actual from the unit price on the cost actual for the specified role.

> [!NOTE]
> Price defaulting for labor, based on cost is valid on project estimates and actuals. It is not effective for quote lines or contract line details.

## Markup over transaction cost

When the **Markup over transaction cost** pricing method is selected on the role price line that's linked to a sales price list, the default price is entered for the combination of a role and a resourcing unit for an expense actual. This unit price is set on the unbilled sales actual to a calculated value from the unit price on the cost actual for that expense after the defined markup percentage is applied.

A negative percentage is used to apply a markdown of the transaction cost.

> [!NOTE]
> Price defaulting for labor, based on cost is valid on project estimates and actuals. It is not effective for quote lines or contract line details.

## Transfer pricing or set up bill rates for resources from other organizational units or divisions 

Project-based companies often use employees from different divisions of a company to work on projects. Projects can be executed from one division while the employees or consultants come from the same division or a different division. The project can also be made up of a combination of people from different divisions. In Project Operations, the company that owns the delivery of the project is called the **Contracting unit**. All the other divisions that provide resources are called **Resourcing units**. With the differences in labor costs across geographies and labor markets around the world, bill rates for labor are also set up differently for different geographies.

For example, a developer from the Fabrikam India working on a US project is billed at the rate of 100 USD per hour. A developer from the Fabrikam US working on a US project is billed at 150 USD per hour.

### Example: Set up a bill rate

To set up a bill rate, follow these steps:

1. Create a sales price list called *Fabrikam US Bill Rates*, and set the date effectivity.
2. In the sales price list, enter the following rate information:

    | Role | Organizational unit | Bill rate |
    | --- | --- | --- |
    | Developer | Fabrikam India | $100 |
    | Developer | Fabrikam Philippines | $90 |
    | Developer | Fabrikam US | $150 |

3. Attach the sales price list, **Fabrikam US Bill Rates** to the project price list of the project contract or to a certain account.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
