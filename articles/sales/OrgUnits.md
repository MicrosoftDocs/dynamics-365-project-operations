---
title: Organizational units
description: This article describes the concept of organizational units, and explains how to create and maintain organizational units in Microsoft Dynamics 365 Project Operations.
author: suvaidya
ms.author: suvaidya
ms.date: 06/10/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Organizational units overview

In Microsoft Dynamics 365 Project Operations, an *organizational unit* is a distinct group or division in a professional services company that employs billable resources that have cost rates.

For professional services companies that employ technical resources in different practice areas or business lines, the cost to fill a role might vary, depending on the practice area or business line where the role is filled. In this scenario, the concept of organizational units helps by providing a way to group a set of billable roles in a division of a company that has a distinct cost structure for those roles.

## The concept of organizational units in Project Operations

In Project Operations, an organizational unit has a specific currency and specific cost price lists.

The currency of an organizational unit is the primary currency that is used to track costs.

One or more cost price lists can be attached to each organizational unit. Project Operations puts the following limitations on the price lists that can be attached to an organizational unit:

- The price lists must be in the currency of the organizational unit.
- The price lists must be cost price lists.

In addition, the Resource entity includes an attribute for the organizational unit. Each resource can be assigned to one organizational unit.

### Roles of organizational units

The organizational unit plays two roles in Project Operations:

- **Contracting unit** – The organizational unit that represents the company group or division that is primarily responsible for winning the sale and managing the delivery of work and services to the customer. The contracting unit is identified by the **Contracting Unit** field in the header section of the **Opportunity**, **Quote**, **Project Contract**, and **Project** pages.
- **Resourcing unit** – The organizational unit that a resource belongs to or is assigned to. This organizational unit can provide its resources for some roles on statements of work (SOWs) and projects that are owned by the contracting unit.

![Contracting units and resourcing units.](media/OrgUnits.png)

### Organizational unit FAQ

Here are some of the most frequently asked questions about organizational units.

#### How is the Organizational Unit entity in Project Operations related to the Organization entity that already exists in Dynamics 365?

The Organization entity in Dynamics 365 represents the name of a global Dynamics 365 instance. This name is usually the name of the global enterprise.

The Organizational Unit entity represents a group or division in the global enterprise. This group or division has a set of roles and a cost price list for those roles, and those roles and price list differ from the roles and price list of other groups or divisions in the enterprise.

When Project Operations is installed, a default organizational unit is created based on the organization. All existing resources are assigned to the default organizational unit. If any new Active Directory users or resources are imported into Dynamics 365, the user import process assigns them to the default organizational unit in Project Operations.

#### How does the Organizational Unit entity differ from the Business Unit entity?

In Dynamics 365, the Business Unit entity is a security construct. The association of a user with a business unit determines the entities and entity records that the user has access to. It also determines the permissions (Create, Read, Write, Delete, Append, Append To, Assign, or Share) that the user has for those entity records.

The Organizational Unit entity represents a company group or division that has distinct cost rates for employees that are assigned to it. The association of a resource with an organizational unit determines the resource's cost to a project engagement.

When you implement Dynamics 365, optimize security authorization for the hierarchy of business units and the assignment of users to business units. Assign all users who must typically access the same set of records to the same business unit. The organizational unit has no effect on security authorization or access.

**Example that shows one potential difference in the modeling of organizational units and business units**

Contoso, Ltd. has a thriving Microsoft technology practice. Prakash and Tricia are both C\# developers, but Tricia is in the United States, whereas Prakash is in India. Most of the project engagements require resources from both Contoso India and Contoso US, and Prakash and Tricia require the same level of security access to projects in this practice area. However, the cost of developers from Contoso India differs significantly from the cost of developers from Contoso US.

Here is an optimal way to design for this scenario by using Dynamics 365 and Project Operations.

1. Create the Microsoft technology practice as a business unit, and associate Prakash and Tricia with it. In this way, you help ensure that both employees have the same level of security access to any projects in that practice area. They both will be able to check progress and report time, expenses, material usage, and task updates.
2. Create two organizational units to help ensure that the cost to the project is correctly reflected.
3. Associate Tricia with Contoso US and Prakash with Contoso India.
4. Assign appropriate cost price lists to both organizational units. In this way, you help ensure that the costs that are recorded on the project for Prakash and Tricia accurately reflect the difference in costs between Contoso US and Contoso India.

#### Are organizational units related to sales territories in Dynamics 365?

There is no association or relationship between sales territories and organizational units. A sales territory is typically a geographical area where sales occur. A sales price list can be associated with each sales territory.

An organizational unit is an internal group or division in the company that tracks costs for a set of roles that it sells to other divisions or to external customers.

**Example that shows one potential difference in the modeling of organizational units and sales territories**

Contoso, Ltd. has two development centers: Contoso US and Contoso India. The cost of resources differs greatly between these two development centers. Contoso sells its information technology (IT) services in many international markets, such as Latin America, North America, Asia-Pacific, Western Europe, and the Middle East. Bill rates for the same project roles can vary widely across these markets. Contoso US and Contoso India should be set up as organizational units, and each organizational unit should have its own cost price list. Asia-Pacific, Latin America, North America, Western Europe, and the Middle East should be set up as sales territories, and each sales territory should have its own sales price list.

#### Why is there a restriction on the association of price lists with organizational units?

Sales pricing is usually unique to the geographical areas or markets where services are sold. Internal divisions of a company don't usually have their own sales pricing for the same type of services. However, internal divisions have a different cost of goods sold (COGS), depending on the skills of the people that they employ and the labor conditions of the region where they operate. Because organizational units are modeled as internal divisions of a company, they can have only cost price lists.

#### Why can't we associate sales price lists with organizational units?

In Project Operations, sales price lists can be associated with customers and sales territories. Transactional entities such as Opportunity, Quote, Project Contract, and Project use sales price lists that are attached to the customer account or the sales territory to determine bill rates and potential revenue for the project engagement.

Cost price lists are associated with organizational units. Transactional entities such as Opportunity, Quote, Project Contract, and Project use cost price lists that are attached to the contracting unit to determine costs to a project engagement.

#### Are organizational units hierarchical in Project Operations?

No. In the current release of Project Operations, organizational units aren't hierarchical. Therefore, you can't perform the following tasks:

- Configure a pattern for entering default cost prices that traverses up a hierarchy.
- Report revenue or cost that is rolled up at different levels of the organizational unit hierarchy.

#### We're a big multinational firm that has a complex, multilevel hierarchy of cost centers, divisions, and billing offices. How can we best use the concept of organizational units in the current version of Project Operations?

When you have a complex hierarchy of cost centers, divisions, billing offices, and so on, set up the leaf nodes of that hierarchy as distinct organizational units.

The following example shows a typical hierarchy.

**Contoso India**

- SAP Practice

    - Technical Consultants
    - Functional Consultants

- Microsoft Technology Practice

    - Technical Consultants
    - Functional Consultants

**Contoso US**

- SAP Practice

    - Technical Consultants
    - Functional Consultants

- Microsoft Technology Practice

    - Technical Consultants
    - Functional Consultants

If your hierarchy resembles this example, you must set it up as a flat list, as shown here:

- Contoso India - SAP Practice - Technical Consultants
- Contoso India - SAP Practice - Functional Consultants
- Contoso India - Microsoft Technology Practice Functional Consultants
- Contoso India - Microsoft Technology Practice Functional Consultants
- Contoso US - SAP Practice - Technical Consultants
- Contoso US - SAP Practice - Functional Consultants
- Contoso US - Microsoft Technology Practice - Technical Consultants
- Contoso US - Microsoft Technology Practice - Functional Consultants

#### We're a small professional services company that operates as only one division. How can we best use the concept of organizational units in the current version of Project Operations?

If your company operates as one unit that has one cost price list, you don't have to set up any organizational units. The installation of Project Operations creates one default organizational unit that has the same name as the organization. By default, all users are assigned to this organizational unit. Whenever the system requires that an organizational unit be selected, this organizational unit is selected by default.

#### When a project is created from a quote or project contract line, the default contracting unit comes from the quote or project contract. What is the default contracting unit if a project is created before sales entities such as Quote or Project Contract?

When a project is created on its own, the default contracting unit of the project is based on the user who creates it. That user is also the default project manager. If the project is mapped to a sales entity such as a quote or project contract, the contracting unit of the project is based on the sales entity instead. In this case, project estimates might be recalculated, because the cost price list is used to calculate the cost estimate changes if the contracting unit is changed. The sales price list is used to calculate the sales estimates that will be changed so that they are in sync with the project price list of the quote.

The **Contracting Unit** and **Currency** fields of the project are locked for editing, because they must be in sync with the values of the sales entity (quote or project contract) that the project is mapped to.

## Create and maintain organizational units in Project Operations

To create an organizational unit in Project Operations, follow these steps:

1. Go to **Settings \> Organizational Units**.
2. Select **New**.
3. In the **General** area, in the **Name** field, enter a name for the organizational unit. Then set the other fields as required.
4. Select **Save** to create the record so that you can continue to edit it.
5. Under **Cost Price Lists**, select the plus sign (**+**) to add a price list. You can add only price lists that have the **Cost** context here.
6. In the **Name** field, select the **Search** button, and select a price list that you want to make available to the organizational unit. Continue to add price lists as required.
7. When you've finished adding price lists, select **Save** in the lower-right corner of the page.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
