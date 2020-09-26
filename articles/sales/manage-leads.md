---
title: Manage leads
description: This topic provides information about managing project-based leads.
author: rumant
manager: Annbe
ms.date: 10/01/2020
ms.topic: article
ms.service: dynamics-project-operations
ms.reviewer: kfend 
ms.author: runant
---

# Manage leads

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project-based leads can be managed and qualified in Project Operations. The process of lead management includes creating work-based leads and qualifying those leads. 

## Project sales leads

In the **Sales** section, in the left navigation pane, open the **Leads** list page to view a list of all lead records in the system. The list of leads shown are work-based leads and other types of leads that can be created if you also have the Dynamics 365 Sales or Dynamics 365 Field Service applications.

You can create a filtered view to see only project-based leads by creating a filter on the **Type** value. For example, you can select to show only work-based leads.

## Create a new lead for a project-based deal

When a project-based lead is qualified, an opportunity and an account is created. A project-based opportunity is the starting point for sales pursuit activities in the Opportunity phase. Project-based opportunities have unique capabilities that are required for selling project work. These capabilities include Time and material and Fixed Price billing methods, multiple date effective price lists for human resources, expenses, and material incurred on projects.

For a qualified lead to create an opportunity, when you create the lead, set the **Type** attribute to **Work-based**. If you choose a different type, the lead won't create a project-based opportunity when it is qualified. If the project-based opportunity isn't created, the project-specific capabilities won't be available in the downstream sales processes.

The following table includes some of the important field information for a lead and the downstream implications of those fields.
 
| **Field** | **Location** | **Relevance, purpose and guidance** | **Downstream impact** |
| --- | --- | --- | --- |
| Topic | General tab | This is a text field and should contain a short description of the deal | The topic of the lead will go on to get defaulted as the topic of the Opportunity and the Name of Quote and Project contract. |
| Type | General tab | This is an option set field with the following options:</br>- Work-based (Available only when Project Operations is installed)</br>- Item-based (Available only when Project Operations and Sales are installed)</br>- Service maintenance-based (Available when Field Service is installed) | When the value of this field is set to Work-based on the lead, the lead is qualified to create a Project-based Opportunity. A project-based opportunity is required for enabling all project- specific extensions and functionality in the downstream sales process for this deal. |
| First name | General tab | First name of the prospect&#39;s contact | When the lead is qualified, an account, contact and opportunity are created. The first name of the contact is set to the value set here. |
| Last name | General tab | Last name of the prospect&#39;s contact | When the lead is qualified, an account, contact and opportunity are created. The last name of the contact is set to the value set here. |
| Company | General tab | Name of the prospect customer&#39;s company | When the lead is qualified, an account, contact and opportunity are created. The name of the account created is set to the value set here. |
| Currency | Details tab | Prospect customer&#39;s currency | When the lead is qualified, an account, contact and opportunity are created. The currency of the account created is set to the value set here. |

## Qualifying a new project-based lead

Leads that have the &quot;Type&quot; value set to work-based are called project-based leads. Project-based leads on qualification create:

1. Account using the &quot;company&quot; field on the lead.
2. A contact record associated to that Account based on the first name and last name fields on the Lead.
3. A project-based opportunity i.e. an opportunity that has the &quot;Type&quot; field set to &quot;work-based&quot;.

For more detailed information on qualifying leads, please refer to the documentation in the D365 Sales application help here:[https://docs.microsoft.com/en-us/dynamics365/sales-enterprise/qualify-lead-convert-opportunity-sales](https://docs.microsoft.com/en-us/dynamics365/sales-enterprise/qualify-lead-convert-opportunity-sales)

## Lead qualification and Legal Entity information in integrated deployments

When running Project Operations in an integrated mode, each customer and opportunity will mandatorily need to have the Owning Company field set. Owning company is a legal entity of your enterprise that owns the delivery of the project. Each customer or account with relationship type of customer must have the company field value set to the Legal entity that contracts and negotiates with this customer. A customer can only be in one Legal entity.

When a lead is qualified, the customer and opportunity records created will have the company field set to the company of the current user&#39;s bookable resource record.

If the current user&#39;s bookable resource record is empty, then the company field value on the user record is used to default the owning company on the customer and the opportunity.

## Business Process flow for project-based deals

The following business process flows are supported for project-based deals in Project Operations:

1. Lead to Opportunity business process
2. Opportunity sales process

Lead to Opportunity business process supports the following stages:

| Stage name | Mapped entity | Functionality |
| --- | --- | --- |
| Qualify | Lead | Qualify the lead to create an account, contact and an opportunity |
| Develop | Opportunity | Develop the opportunity to add more information on the work involved, key stakeholders and competition |
| Propose | Opportunity | Develop the proposal and get approval from the internal review team |
| Close | Opportunity | Win the opportunity to close the deal |
