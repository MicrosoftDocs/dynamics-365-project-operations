---
title: Manage project-based leads
description: This article provides information about managing project-based leads.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Manage project-based leads

_**Applies To:** Project Operations Integrated with ERP_

You can manage and qualify project-based leads in Project Operations. The lead management process includes creating work-based leads and qualifying those leads.

In the **Sales** section of the left navigation pane, open the **Leads** list page to view a list of all lead records in the system. The list of leads shown are work-based and other types of leads that you can create if you also have the Dynamics 365 Sales or Dynamics 365 Field Service applications.

You can create a filtered view to see only project-based leads by creating a filter on the **Type** value. For example, you can select to show only work-based leads.

## Create a new project-based lead

When you qualify a project-based lead, you create an opportunity and an account. A project-based opportunity is the starting point for sales pursuit activities in the Opportunity phase. Project-based opportunities have unique capabilities that are required for selling project work. These capabilities include:

- Time and material and Fixed Price billing methods
- Multiple date effective price lists for human resources, expenses, and material incurred on projects

To automatically create an opportunity for a qualified lead, set the **Type** attribute to **Work-based** when you create the lead. If you choose a different type, the lead doesn't create a project-based opportunity when you qualify it. If the project-based opportunity isn't created, the project-specific capabilities aren't available in the downstream sales processes.

The following table includes important field information for a lead, and the downstream implications of those fields.

| **Field** | **Location** | **Description** | **Downstream impact** |
| --- | --- | --- | --- |
| Topic | General tab | This text field should contain a short description of the deal. | The topic of the lead defaults as the topic of the Opportunity, and the Name of Quote and Project contract. |
| Type | General tab | This option set field has the following options:</br>- Work-based (available only when Project Operations is installed)</br>- Item-based (available only when Project Operations and Sales are installed)</br>- Service maintenance-based (available when Field Service is installed) | When you set this field to **Work-based** on the lead, you qualify the lead to create a Project-based Opportunity. A project-based opportunity is required to enable all project-specific extensions and functionality in the downstream sales process for this deal. |
| First name | General tab | First name of the prospect's contact | When you qualify the lead, you create an account, contact, and opportunity. The first name of the contact is the value set here. |
| Last name | General tab | Last name of the prospect's contact | When you qualify the lead, you create an account, contact, and opportunity. The last name of the contact is the value set here. |
| Company | General tab | Name of the prospect customer's company | When you qualify the lead, you create an account, contact, and opportunity. The name of the account created is the value set here. |
| Currency | Details tab | Prospect customer's currency | When you qualify the lead, you create an account, contact, and opportunity. The currency of the account created is the value set here. |

## Qualify a new project-based lead

Set the **Type** value to **Work-based** for project-based leads. When you qualify a project-based lead, the process creates the following records:

- An account that uses the **Company** field from the lead.
- A contact record associated to the account based on the values in the **First Name** and **Last Name** fields on the lead.
- A project-based opportunity that has the **Type** field set to **Work-based**.

For more detailed information on qualifying leads, see [Qualify or convert leads](/dynamics365/sales-enterprise/qualify-lead-convert-opportunity-sales).

## Lead qualification and legal entity information

When you run Project Operations by using the deployment mode, Project Operations Integrated with ERP, each customer and opportunity requires the **Owning Company** field to be set. The owning company is a legal entity in your organization that owns the delivery of the project. Each customer or account with a relationship type of customer must have the **Owning Company** field set to the legal entity that contracts and negotiates with this customer. A customer can only be in one legal entity.

When you qualify a lead, the process sets the **Owning Company** field on the customer and opportunity records to the company of the current user's bookable resource record.

If the current user's bookable resource record is empty, the process uses the **Owning Company** field value on the user record to default the customer and the opportunity records.

## Business process flow for project-based deals

Project Operations supports the following business process flows for project-based deals:

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
