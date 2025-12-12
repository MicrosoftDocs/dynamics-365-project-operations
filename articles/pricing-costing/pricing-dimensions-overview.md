--- 
title: Pricing dimensions overview
description: This article provides information about the pricing dimensions in Dynamics 365 Project Operations.
author: abriccetti
ms.author: abriccetti 
ms.date: 01/09/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

--- 

# Pricing dimensions overview

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The dimensions that are used in human resources to set up pricing and costs fall into two categories:

- People
- Planned work

Because of this, there are two types of pricing dimension values available:

- **Option sets**: Dimensions that are fixed enumerations for a set of values.
- **Entity-based values**: Dimensions that can be a varied set of values.

## Pricing dimensions

Dynamics 365 Project Operations ships with a default set of pricing dimensions. You can view these pricing dimensions by going to **Project Operations** > **Parameters**. In the parameter record, on the **Amount-based pricing dimensions** tab, verify that the role, **msdyn_resourcecategory** and resourcing organizational unit, **msdyn_organizationalunit** have the fields **Applicable to sales** and **Applicable to cost** set to **Yes**. 
With these fields enabled, you can set up the price and cost for each role and organizational unit combination.

![Screenshot of Project Service parameters with “Applicable to Sales” highlighted.](media/PS-OOB-parameters.png)

If you need to price or cost for your resources using additional attributes, you can create customized fields, entities, and dimensions. For more information, see the following articles. 
  
  > [!NOTE]
  > The procedures must be completed in the order they are listed.

1. [Create a solution for custom pricing dimensions](../sales/create-solution-custompd.md)
2. [Create custom fields and entities](create-custom-fields-entities-pricing-dimensions.md)
3. [Add custom fields to price setup and transactional entities](add-custom-fields-price-setup-transactional-entities.md)
4. [Set up custom fields as pricing dimensions](set-up-custom-fields-pricing-dimensions.md)
5. [Update plug-in attributes to include new pricing dimensions](update-plugin-attributes-pd.md)


## Pricing human resource time
How an organization prices human resource time is often an important strategic consideration that directly affects the organization's profitability. Work with the finance teams and practice heads when your organization is ready to identify how it wants to set up bill and cost rates for human resource time.

Other considerations for pricing include whether to re-use fields or entities that are not currently pricing dimensions but apply as a pricing dimension for your organization. Fields like **Transaction Category** (**msdyn_transactioncategory**) and **Bookable Resource** (**bookableresource**) are examples of candidate dimensions. 

Consider whether your pricing dimension should be a table or an option set. If you foresee changes to the values of a dimension which will exceed 10 or 12 and you need additional attributes on these values, you could create an entity rather than an option set. Maintaining an option set, such as adding or removing values, requires an admin or developer whereas adding new rows to a table can be done by most users.

The following example shows bill rates that are set up based on the role and the resourcing org unit to which the resource belongs. Cost rates are typically based on the salary band of the employee and the org unit that they belong to. In this example, the bill rate and cost rate tables will look like the following.

**Sample bill rates**

| Role        | Org Unit    |Unit      |Price      |Currency  |
| ------------|-------------|----------|----------:|----------|
| Developer   | Contoso US  |Hour | 200|USD     |
| Developer   | Contoso India |Hour|   112|USD     |


**Sample cost rates**

| Salary Band     | Org Unit    |Unit      |Price      |Currency  |
| ----------------|-------------|----------|----------:|----------|
| My company_Band1 | Contoso US  |Hour | 145|USD     |
| My company_Band2 | Contoso India |Hour|   67|USD     |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
