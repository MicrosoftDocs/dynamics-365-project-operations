---
title: Responding to Data Subject Rights (DSR) requests for Dynamics 365 Project Operations
description: This article provides instructions for exporting and deleting personal data for exporting and deleting personal data from the service and can help meet your needs for GDPR. 
author: ryansandness
ms.author: ryansandness
ms.date: 09/12/2024
ms.topic: conceptual
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Responding to Data Subject Rights (DSR) requests for Dynamics 365 Project Operations

[!INCLUDE[banner](../includes/banner.md)]

This guide provides resources on how to use Microsoft's products, services, and administrative tools to help our controller customers find and act on personal data to respond to DSR requests for Dynamics 365 Project Operations. Specifically, this includes how to find, access, and act on personal data or personal information that reside in Microsoft's cloud. Here's a quick overview of the processes this guide will help you locate:

- **Discover**: Use search and discovery tools to more easily find customer- data that may be the subject of a DSR request. Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request. Alternatively, you may determine that the request doesn't meet your organizations guidelines for responding to DSR requests.
- **Access**: Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that is available to the data subject.
- **Rectify**: Make changes or implement other requested actions on the personal data, where applicable.
- **Restrict**: Restrict the processing of personal data, either by removing licenses for various online services or turning off the desired services where possible.
- **Delete**: Permanently remove personal data that resided in Microsoft's cloud.
- **Export/Receive** (Portability): Provide an electronic copy (in a machine-readable format) of personal data or personal information to the data subject.

This guide outlines the technical procedures that a data controller organization can take to respond to a DSR request for personal data in Microsoft's cloud.
For more details on data subject rights like the European Union General Data Protection Regulation (GDPR), and the California Consumer Privacy Act (CCPA) please visit the [California Consumer Privacy Act](https://learn.microsoft.com/compliance/regulatory/offering-ccpa).

## How this guide can help you meet your controller responsibilities

The guide, divided into two parts, describes how to use Microsoft products, services, and administrative tools to help you find and act on data in the Microsoft cloud in response to requests by data subjects who are exercising their rights under the GDPR. The first part addresses personal data that is included in customer data, followed by a part addressing other pseudonymized personal data captured in system-generated logs.

- **Part 1: Responding to Data Subject Rights (DSR) requests for Personal Data included in Customer Data**: Part 1 of this guide discusses how to access, rectify, restrict, delete, and export personal data from Dynamics 365 Project Operations (software as a service), which is processed as part of the customer data you have provided to the online service.
- **Part 2: Responding to data subject rights requests for Pseudonymized Data**: When you use Dynamics 365 Project Operations, Microsoft generates some information (referred to within this document as system-generated logs) to provide the service, which is limited to the usage footprint left behind by end users to identify their actions in the system. Although this data cannot be attributed to a specific data subject without the use of additional information, some of it may be deemed personal under the GDPR. Part 2 of this guide discusses how to access, delete, and export system-generated logs produced by Dynamics 365 Project Operations.

## Preparing for data subject rights investigations

When data subjects exercise their rights and make requests, consider the following points:

- Properly identify the person and role—such as employee, customer, vendor—by using information that the data subject gave you as part of his or her request. This information might be a name, an employee ID or customer number, or other identifier.
- Record the data and time of the request. (You have 30 days to complete the request.)
- firm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Verify that you have the information that is related to the request.

## Part 1: DSR Guide for customer data

### Executing DSRs against customer data

Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as in-product experiences). Details regarding such in-product experiences for Dynamics 365 Project Operations are described in this guide.

**Note**: Dynamics 365 Project Operations has multiple [deployment types](https://learn.microsoft.com/dynamics365/project-operations/environment/determine-deployment-type) that can involve the use of Dataverse, the finance and operations architecture, or both. Depending on the deployment type, the data subject rights request (DSR) process may vary.

#### Discover

The first step in responding to a DSR request is to find the personal data that is the subject of the request. This first step—finding and reviewing the personal data at issue—will help you determine whether a DSR request meets your organization's requirements for honoring or declining a DSR request. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.

After you find the data, you can then perform the specific action to satisfy the request by the data subject.

Dataverse provides multiple methods for you to search for personal data within records such as: Advanced Find Search and Search for Records. These functions all enable you to identify (find) personal data.

- [Advanced Find Search](https://learn.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Search for Records across multiple record types](https://learn.microsoft.com/dynamics365/customer-engagement/basics/search-records)

The finance and operations architecture provides several ways for you to search for customer data. You as a Tenant Admin can perform the following actions to search for customer data:

- Organize your customer data in a way that serves the purpose of rapidly discovering personal data, see [how to classify data inventory](https://learn.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory) for this purpose.
- Use the [Person search report](https://learn.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) to find and collect personal data.
[Extend the Person search report](https://learn.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) by authoring a new entity or extending an existing entity.
- Use search and filter features to find specific personal data and export that data by using the Microsoft Office Export functionality or print that information to a .pdf using browser extensions.
- Author a custom form that locates and exports personal data.
- Author an external portal or website that allows an authenticated customer to see his or her personal data.

#### Access

After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.
When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.

Customer data within Dataverse can be exported using the comprehensive entity export capabilities. Customer data can be exported to a static Excel file to facilitate a data portability request. Using Excel, you can then edit the personal data to be included in the portability request and then save as a commonly used, machine-readable format such as .csv or .xml. Records also can be exported via the [Microsoft Dataverse Web API](https://learn.microsoft.com/powerapps/developer/data-platform/webapi/overview).

Customer data in the finance and operations architecture can be exported using the comprehensive entity export capabilities. Using [Data management and integration entities](https://learn.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-management-integration-data-entity), the Tenant Admin may utilize provided entities, create new, or extend existing, entities for a repeatable personal data export to Excel or a number of other common formats using [Data import and export jobs](https://learn.microsoft.com/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-guide#the-person-search-report). Alternatively, many lists can be exported to a static Excel file to facilitate a data portability request. When customer data is exported to Excel, you can then edit the personal data to be included in the portability request and then save the file as a commonly used, machine-readable format such as .csv or .xml. You may also consider using the [Person search report](https://learn.microsoft.com/dynamics365/fin-ops-core/dev-itpro/privacy/privacy-extend-person-search-report) to provide the data subject with data that you've classified as personal data.

#### Rectify

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

Dataverse gives you the following methods for correcting inaccurate or incomplete customer data, or erasing customer data:

Search for customer data using the capabilities mentioned in "Discover" and directly edit data within Dataverse. Edits can be done at a single row level or multiple rows can be modified directly.
Bulk editing multiple records, you can utilize the Microsoft Office add-in to export data to Microsoft Excel, make your changes, and then import that modified data from Excel into Dataverse.

On the finance and operations architecture, you may also use customization tools, but the decision and implementation is your responsibility.

##### Brief note about modifying entries in business transactions

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 Project Operations restricts modifying data in such records.

#### Restrict

Data subjects may request that you restrict processing of their personal data.

When you receive a request from a data subject to restrict processing of customer data, you can easily extract the affected customer data from the online service and store it in a separate container (that is, on-premises storage or separate web service with data isolation capabilities) isolated from the processing functions offered by any cloud application.

#### Delete

The "right to erasure" by the removal of personal data from an organization's customer data is a key protection in the GDPR. Removing personal data includes system-generated logs but not audit-log information.

When a data subject asks you to delete their customer data, there are several ways to do so:

Bulk editing multiple records in Dataverse, you can utilize the Microsoft Office add-in to export data to Microsoft Excel, make your changes, and then import that modified data from Excel back into the online service.
You can delete customer data stored in any field by locating the data you want to delete and then manually deleting the data element containing the target customer data, for example like employing a hard delete on the contact record representing the data subject and other records that contain personal data.

Alternatively, on the finance and operations architecture you may use customization tools to erase/modify customer data.

You must be a tenant administrator to delete a user from the tenant.

#### Export

The "right of data portability" allows a data subject to request a copy of their personal data in an electronic format (that's a "structured, commonly used, machine read-able and interoperable format") that may be transmitted to another data controller.

To respond to a data portability request, customer data in Dataverse can be exported using the comprehensive entity export capabilities. Customer data can be exported to a static Excel file to facilitate a data portability request. Using Excel, you can then edit the personal data to be included in the portability request and then save as a commonly used, machine-readable format such as .csv or .xml.

The finance and operations architecture offers [Data management and integration entities](https://learn.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-management-integration-data-entity) that enables provided entities, newly created entities, or extended entities for a repeatable personal data export to Excel or a number of other common formats using [Data import and export jobs](https://learn.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job). Alternatively, many lists can be exported to a static Excel file to facilitate a data portability request. When customer data is exported to Excel in this fashion, you can then edit the personal data to be included in the portability request and then save the file as a commonly used, machine-readable format such as .csv or .xml.

The Person search report can be used to provide the data subject with data that you've classified as personal data.

You must be a tenant administrator to export user data from the tenant.

## Part 2: System-Generated Logs

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Product and service usage data such as user activity logs
- User search requests and query data
- Data generated by product and services as a product of system functionality and interaction by users or other systems
Important

The ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### Executing DSRs against System-Generated Logs

- [System-Generated logs Data Subject Rights Requests Processes](https://learn.microsoft.com/compliance/regulatory/gdpr-dsr-dynamics365#part-2-responding-to-dsrs-for-system-generated-logs) for Dynamics 365 Project Operations
