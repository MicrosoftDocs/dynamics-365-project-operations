---
title: Manage project-based leads
description: This article provides information about managing project-based leads.
author: poojafandan
ms.author: poojafandan
ms.date: 06/10/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage project-based leads

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Project-based leads can be managed and qualified in Project Operations. The process of lead management includes creating work-based leads and qualifying those leads. 

In the **Sales** section, in the left navigation pane, open the **Leads** list page to view a list of all lead records in the system. The list of leads shown are work-based and other types of leads that can be created if you also have the Dynamics 365 Sales or Dynamics 365 Field Service applications.

You can create a filtered view to see only project-based leads by creating a filter on the **Type** value. For example, you can select to show only work-based leads.

## Create a new project-based lead 

When a project-based lead is qualified, an opportunity and an account are created. A project-based opportunity is the starting point for sales pursuit activities in the Opportunity phase. Project-based opportunities have unique capabilities that are required for selling project work. These capabilities include:

- Time and material and Fixed Price billing methods
- Multiple date effective price lists for human resources, expenses, and material incurred on projects

For qualified lead to automatically create an opportunity, set the **Type** attribute to **Work-based** when you create the lead. If you choose a different type, the lead won't create a project-based opportunity when it is qualified. If the project-based opportunity isn't created, the project-specific capabilities won't be available in the downstream sales processes.

The following table includes important field information for a lead, and the downstream implications of those fields.
 
| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Topic | General tab | This text field should contain a short description of the deal. | The topic of the lead will default as the topic of the Opportunity, and the Name of Quote and Project contract. |
| Type | General tab | This option set field has the following options:</br>- Work-based (available only when Project Operations is installed)</br>- Item-based (available only when Project Operations and Sales are installed)</br>- Service maintenance-based (available when Field Service is installed) | When the value of this field is set to **Work-based** on the lead, the lead is qualified to create a Project-based Opportunity. A project-based opportunity is required to enable all project-specific extensions and functionality in the downstream sales process for this deal. |
| First name | General tab | First name of the prospect's contact | When the lead is qualified, an account, contact, and opportunity are created. The first name of the contact is the value set here. |
| Last name | General tab | Last name of the prospect's contact | When the lead is qualified, an account, contact, and opportunity are created. The last name of the contact the value set here. |
| Company | General tab | Name of the prospect customer's company | When the lead is qualified, an account, contact, and opportunity are created. The name of the account created the value set here. |
| Currency | Details tab | Prospect customer's currency | When the lead is qualified, an account, contact, and opportunity are created. The currency of the account created is the value set here. |

## Qualify a new project-based lead

Leads that have the **Type** value set to **Work-based** are called project-based leads. When a project-based lead is qualified, the following is created:

- An account that uses the **Company** field from the lead.
- A contact record associated to the account based on the values in the **First Name** and **Last Name** fields on the lead.
- A project-based opportunity that has the **Type** field set to **Work-based**.

For more detailed information on qualifying leads, see [Qualify or convert leads](/dynamics365/sales-enterprise/qualify-lead-convert-opportunity-sales).

## Lead qualification and legal entity information 

When you run Project Operations using the deployment mode, Project Operations for resource/non-stocked based scenarios, each customer and opportunity will require having the **Owning Company** field set. The Owning company is a legal entity in your organization that owns the delivery of the project. Each customer, or account with relationship type of customer, must have the **Owning Company** field value set to the legal entity that contracts and negotiates with this customer. A customer can only be in one legal entity.

When a lead is qualified, the customer and opportunity records created will have the **Owning Company** field set to the company of the current user's bookable resource record.

If the current user's bookable resource record is empty, then the **Owning Company** field value on the user record is used to default on the customer and the opportunity records.

## Business process flow for project-based deals

The following business process flows are supported for project-based deals in Project Operations:

- Lead to Opportunity business process
- Opportunity sales process

The Lead to Opportunity business process supports the following stages:

| Stage name | Mapped entity | Functionality |
| --- | --- | --- |
| Qualify | Lead | Qualify the lead to create an account, contact, and an opportunity. |
| Develop | Opportunity | Develop the opportunity to add more information on the work involved, key stakeholders, and competition. |
| Propose | Opportunity | Develop the proposal and get approval from the internal review team. |
| Close | Opportunity | Win the opportunity to close the deal. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
