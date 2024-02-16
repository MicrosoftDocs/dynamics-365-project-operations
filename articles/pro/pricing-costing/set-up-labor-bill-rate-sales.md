---
title: Set up labor bill rates Lite deployment (preview)
description: This article provides information about setting up labor billing rates in Project Operations Lite deployment (preview).
author: avisness
ms.date: 02/16/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: avisness
---

# Set up labor bill rates Lite deployment (preview)

[!INCLUDE[banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

_**Applies To:** Lite deployment - deal to proforma invoicing_

Each price list has a set of role prices or labor rates that are effective for the context and date effectivity included on the price list header. Bill rates for time in Dynamics 365 Project Operations can be set up in only one currency, which is the currency on the Price list header.

To set up labor bill rates for a sales price list, follow these steps.

1. Create a price list based on the price list header. 
2. On the **Role Prices** tab, in the subgrid, select **+ New Role Price**. 
3. On the **Quick Create** pane, enter the role and organization unit combination for which you need to set up the bill rate.

The following table includes the fields on the **General** tab and the **Quick Create** pane of a role price line. Keep these in mind as you create role prices on a sales price list:

  | Field | Location | Description | Downstream impact |
  | --- | --- | --- | --- |
  | Role | **General** tab and **Quick Create** pane | Select the role that you're setting the bill rate for. | Role on the incoming estimate or actual is matched against this line to default bill rate of the role. |
  | Resourcing Unit | **General** tab and **Quick Create** pane | Select the organizational unit or division of the company that the role is from. For example, a developer from the Robotics division of Fabrikam India or a developer from the Software division of Fabrikam USA. | The resourcing unit on the incoming estimate or actual is matched against this line to default the bill rate of the role. |
  | Price Calculation | **General** tab and **Quick Create** pane | Possible values of the **Pricing calculation** or **Pricing method** field are, **Price per unit**, **At transaction cost**, and **Markup over transaction cost**. | During price setup, selecting ***Price per unit** locks the **Percent** field on the category price line. If **At transaction cost** is selected, the **Price** and **Percent** fields are locked on the sales price list. Selecting **Markup over transaction cost** locks the **Price** field on the sales price list. On an incoming actual line for expense, the **At transaction cost** or **Markup over transaction cost** pricing calculation results in the corresponding unbilled sales line being assigned a price that is equal to the price on the cost actual or calculated as a markup over the cost price. |
  | Price | **General** tab and **Quick Create** pane | Set up the bill rate for the role resourcing company and resourcing unit combination. For example, a developer from Fabrikam India has a bill rate of 100 USD or a developer from Fabrikam USA has a bill rate of 150 USD. | This price is the default bill rate on the per unit price of the incoming estimate or actual line for Time transaction class. |
  | Percent | **General** tab and **Quick Create** pane | Set up percent over cost for the transaction category and unit combination. For example, the role sales rate should be marked up 10 percent over cost rate. | This percent over cost is only applicable on a sales price list when the pricing method selected is Markup over transaction cost. |
  | Currency | **General** tab and **Quick Create** pane| By default, the currency value comes from the currency on the sales price list header. On a sales price list, the currency can't be overridden. | This currency is the default currency on the per unit price of the incoming actual sales line for Time transaction class. |
  | Unit Schedule | **General** tab and **Quick Create** pane | This unit schedule defaults to Time and can't be changed on the Role price entity because it's used to express rates by units of time. | There isn't a downstream impact for this field. |
  | Unit | **General** tab and **Quick Create** pane | The unit value comes from the **Time Unit** field on the sales price list header. But the value can be overridden. For example, a developer from Fabrikam India has bill rate of 1,000 USD per **India Day**. A developer from Fabrikam USA has a bill rate of 1,500 USD per **US Day**. | When the per unit price defaults on an incoming estimate or actual line, the system uses the system of units and conversion in base units to calculate a per unit price. For example, the estimate is for 10 **India Days** worth of work for a Developer from India, and the unit India Day is defined as 10 hours. When you price that estimate line, the application calculates the unit price on the estimate as 1,000 USD/10 hours = 100 USD per hour. |


## Pricing methods for labor (roles) 

When you set up role prices relevant in the context of sales pricing, there are three pricing methods supported:
 - **Price per unit** (default) - The sales price of the role is set to the amount specified in the Currency amount field.
 - **At transaction cost** - The sales price of the role is set to the transaction cost of the role. 
 - **Markup over transaction cost %** - The sales price of the role is calculated as a markup or markdown percentage based on the transaction cost of the specified role. 

## Enable Cost plus pricing

To utilize all pricing methods and enable **Cost plus pricing**, follow these steps.

1. Go to **Settings** > **Parameters**.
2. Open the **Parameters** record.
3. On the **Action** pane, **Feature control** tab, select **Enable Cost plus pricing**.
4. In the confirmation dialog box, select **OK**.
5. Refresh your browser. This feature is now activated and removed from the selection in the **Feature control** tab. 

> [!Note]
> Once the Cost plus pricing feature is enabled, it can't be disabled.


## Price per unit

When this pricing method is selected on a role price line that is linked to a sales price list, the price defaults for the role and resource unit combination for an actual. This pricing method carries through to project estimate lines, quote line detail, and contract line detail for expenses. 

## At transaction cost

When this pricing method is selected on the role price line linked to a sales price list, the price defaults for the role and resourcing unit combination for an actual. The unit price is set on the unbilled sales actual from the unit price on the cost actual for that specified role. 

> [!Note]
> Price defaulting based on cost is valid on actuals only, and isn't effective on project estimates, quote line, or contract line details. 

## Markup over transaction cost

When this pricing method is selected on the role price line that is linked to a sales price list, the price defaults for the role and resourcing unit combination for an expense actual. This unit price is set on the unbilled sales actual to a calculated value from the unit price on the cost actual for that expense after the defined markup percent is applied. 

A negative percentage is used to apply a markdown of the transaction cost. 

> [!Note]
> Price defaulting based on cost is valid on actuals only, and isn't effective on project estimates, quote lines, or contract line details. 

## Transfer pricing or set up bill rates for resources from other organizational units or divisions 

Project-based companies to use employees from different divisions of the company to work on projects. Projects can be executed from one division while the employees or consultants come from the same a different division of the company. The project could also be made up of a combination of people from different divisions. In Project Operations, the company that owns the delivery of the project is called the **Contracting Unit**. All the other divisions that provide resources are called the **Resourcing Units**. Because of the differences in labor costs across various geographies and labor markets across the world, bill rates for labor are also set up differently for different geographies.

For example, a developer from Fabrikam India working on a US project is billed at the rate of 100 USD per hour. A developer from Fabrikam US working on US Project is billed at 150 USD per hour.

### Example: Set up a bill rate

To set up a bill rate, follow these steps.

1. Create a sales price list called *Fabrikam US Bill Rates*, and set the date effectivity.
2. In the sales price list, enter the following rate information:

    | Role | Organizational unit | Bill rate |
    | --- | --- | --- |
    | Developer | Fabrikam India | $100 |
    | Developer | Fabrikam Philippines | $90 |
    | Developer | Fabrikam US | $150 |

3. Attach the sales price list, **Fabrikam US Bill Rates** to the project price list of the project contract or to a certain account.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
