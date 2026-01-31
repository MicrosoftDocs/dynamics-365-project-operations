---
title: Respond to Data Subject Rights (DSR) requests for Microsoft Dynamics 365 Project Operations
description: This article provides instructions for exporting and deleting personal data for exporting and deleting personal data from the service and can help meet your needs for GDPR. 
author: ryansandness
ms.author: ryansandness
ms.date: 09/12/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Respond to Data Subject Rights (DSR) requests for Microsoft Dynamics 365 Project Operations

[!INCLUDE[banner](../includes/banner.md)]

This guide provides resources about how to use Microsoft's products, services, and administrative tools to help our controller customers find and act on personal data to respond to Data Subject Rights (DSR) requests for Microsoft Dynamics 365 Project Operations. Specifically, the information includes how to find, access, and act on personal data or personal information that resides in the Microsoft Cloud. This guide will help you with the following process:

- **Discover**: Use search and discovery tools to more easily find customer data that might be the subject of a DSR request. After potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request. Alternatively, you might determine that the request doesn't meet your organization's guidelines for responding to DSR requests.
- **Access**: Retrieve personal data that resides in the Microsoft Cloud and, if requested, make a copy of it that is available to the data subject.
- **Rectify**: Make changes or implement other requested actions on the personal data, where applicable.
- **Restrict**: Restrict the processing of personal data, either by removing licenses for various online services or by turning off the desired services where possible.
- **Delete**: Permanently remove personal data that resides in the Microsoft Cloud.
- **Export/Receive** (Portability): Provide an electronic copy (in a machine-readable format) of personal data or personal information to the data subject.

This guide outlines the technical procedures that a data controller organization can take to respond to a DSR request for personal data in the Microsoft Cloud.

For more details about data subject rights like the European Union General Data Protection Regulation (GDPR) and the California Consumer Privacy Act (CCPA), see [California Consumer Privacy Act](/compliance/regulatory/offering-ccpa).

## How this guide can help you meet your controller responsibilities

The guide, divided into two parts, describes how to use Microsoft products, services, and administrative tools to help you find and act on data in the Microsoft Cloud in response to requests by data subjects who are exercising their rights under the GDPR. The first part addresses personal data that is included in customer data. It's followed by a part addressing other pseudonymized personal data captured in system-generated logs.

- **Part 1: Responding to DSR requests for personal data included in customer data**: Part 1 of this guide discusses how to access, rectify, restrict, delete, and export from Dynamics 365 Project Operations (software as a service) personal data that is processed as part of the customer data that you've provided to the online service.
- **Part 2: Responding to DSR requests for pseudonymized data**: When you use Dynamics 365 Project Operations, Microsoft generates some information (referred to within this document as system-generated logs) to provide the service. This information is limited to the usage footprint left behind by end users to identify their actions in the system. Although this data can't be attributed to a specific data subject without the use of additional information, some of it might be deemed personal under the GDPR. Part 2 of this guide discusses how to access, delete, and export system-generated logs produced by Dynamics 365 Project Operations.

## Preparing for data subject rights investigations

When data subjects exercise their rights and make requests, consider the following points:

- Properly identify the person and role—such as employee, customer, or vendor—by using information that the data subject gave to you as part of their request. This information might be a name, an employee ID or customer number, or another identifier.
- Record the date and time of the request. (You have 30 days to complete the request.)
- Confirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Verify that you have the information that is related to the request.

## Part 1: DSR guide for customer data

### Executing DSRs against customer data

Microsoft provides the ability to access, delete, and export certain customer data through the Azure portal and also directly via preexisting application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as in-product experiences). Details about such in-product experiences for Dynamics 365 Project Operations are described in this guide.

> [!NOTE]
> Dynamics 365 Project Operations has multiple [deployment types](/dynamics365/project-operations/environment/determine-deployment-type) that can involve the use of Dataverse, the finance and operations architecture, or both. Depending on the deployment type, the DSR request process might vary.

#### Discover

The first step in responding to a DSR request is to find the personal data that is the subject of the request. This first step—finding and reviewing the personal data at issue—will help you determine whether a DSR request meets your organization's requirements for honoring or declining DSR requests. For example, after finding and reviewing the personal data at issue, you might determine that the request doesn't meet your organization's requirements, because honoring it might adversely affect the rights and freedoms of others.

After you find the data, you can perform the specific action to satisfy the request by the data subject.

Dataverse provides multiple methods for you to search for personal data within records, such as Advanced Find Search and Search for Records. These functions all enable you to identify (find) personal data.

- [Advanced Find Search](/dynamics365/customer-engagement/basics/save-advanced-find-search)
- [Search for Records across multiple record types](/dynamics365/customer-engagement/basics/search-records)

The finance and operations architecture provides several ways for you to search for customer data. As a tenant admin, you can perform the following actions to search for customer data:

- Organize your customer data in a way that serves the purpose of rapidly discovering personal data. See [how to classify data inventory](/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory) for this purpose.
- Use the [Person search report](/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report) to find and collect personal data.
[Extend the Person search report](/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report) by authoring a new entity or extending an existing entity.
- Use search and filter features to find specific personal data and export that data by using the Microsoft Office Export functionality, or print that information to a PDF by using browser extensions.
- Author a custom form that locates and exports personal data.
- Author an external portal or website that allows an authenticated customer to see their personal data.

#### Access

After you've found customer data containing personal data that is potentially responsive to a DSR, it's up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions that you've deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data. When providing a copy to the data subject, you might have to remove or redact personal information about other data subjects and any confidential information.

Customer data within Dataverse can be exported by using the comprehensive entity export capabilities. Customer data can be exported to a static Excel file to facilitate a data portability request. By using Excel, you can then edit the personal data to be included in the portability request and save it in a commonly used, machine-readable format such as .csv or .xml. Records also can be exported via the [Microsoft Dataverse Web API](/powerapps/developer/data-platform/webapi/overview).

Customer data in the finance and operations architecture can be exported by using the comprehensive entity export capabilities. [Data management and integration entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-management-integration-data-entity) let the tenant admin use provided entities, create new entities, or extend existing entities for a repeatable personal data export to Excel or a number of other common formats through [Data import and export jobs](/dynamics365/fin-ops-core/dev-itpro/gdpr/gdpr-guide#the-person-search-report). Alternatively, many lists can be exported to a static Excel file to facilitate a data portability request. When customer data is exported to Excel, you can then edit the personal data to be included in the portability request and save the file in a commonly used, machine-readable format such as .csv or .xml. You might also consider using the [Person search report](/dynamics365/fin-ops-core/dev-itpro/privacy/privacy-extend-person-search-report) to provide the data subject with data that you've classified as personal data.

#### Rectify

If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data might include taking actions such as editing, redacting, or removing personal data from a document or other type or item.

Dataverse gives you the following methods for correcting inaccurate or incomplete customer data, or erasing customer data:

- Search for customer data by using the capabilities mentioned in the "Discover" section, and directly edit data within Dataverse. Edits can be done at a single row level, or multiple rows can be modified directly.
- By bulk-editing multiple records, you can use the Microsoft Office add-in to export data to Excel, make your changes, and then import that modified data from Excel into Dataverse.

On the finance and operations architecture, you can also use customization tools, but the decision and implementation are your responsibility.

##### Brief note about modifying entries in business transactions

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning (ERP) system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 Project Operations restricts modifying data in such records.

#### Restrict

Data subjects might request that you restrict processing of their personal data.

When you receive a request from a data subject to restrict processing of customer data, you can easily extract the affected customer data from the online service and store it in a separate container (on-premises storage or a separate web service with data isolation capabilities) that is isolated from the processing functions offered by any cloud application.

#### Delete

The "right to erasure" through the removal of personal data from an organization's customer data is a key protection in the GDPR. Removing personal data includes system-generated logs but not audit log information.

When a data subject asks you to delete their customer data, there are several ways to do so:

- By bulk-editing multiple records in Dataverse, you can use the Microsoft Office add-in to export data to Excel, make your changes, and then import that modified data from Excel back into the online service.
- You can delete customer data stored in any field by locating the data that you want to delete and then manually deleting the data element containing the target customer data. For example, you can employ a hard delete on the contact record representing the data subject and other records that contain personal data.

Alternatively, on the finance and operations architecture, you can use customization tools to erase/modify customer data.

You must be a tenant admin to delete a user from the tenant.

#### Export

The "right of data portability" allows a data subject to request a copy of their personal data in an electronic format (that is, a "structured, commonly used, machine-readable and interoperable format") that can be transmitted to another data controller.

To respond to a data portability request, customer data in Dataverse can be exported by using the comprehensive entity export capabilities. Customer data can be exported to a static Excel file to facilitate a data portability request. By using Excel, you can then edit the personal data to be included in the portability request and save it as a commonly used, machine-readable format such as .csv or .xml.

The finance and operations architecture offers [Data management and integration entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-management-integration-data-entity) that enable provided entities, newly created entities, or extended entities for a repeatable personal data export to Excel or a number of other common formats through [Data import and export jobs](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job). Alternatively, many lists can be exported to a static Excel file to facilitate a data portability request. When customer data is exported to Excel in this way, you can then edit the personal data to be included in the portability request and save the file as a commonly used, machine-readable format such as .csv or .xml.

The Person search report can be used to provide the data subject with data that you've classified as personal data.

You must be a tenant admin to export user data from the tenant.

## Part 2: System-generated logs

Microsoft also provides you with the ability to access, export, and delete system-generated logs that might be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that might be deemed personal under the GDPR include:

- Product and service usage data, such as user activity logs
- User search requests and query data
- Data generated by products and services as a product of system functionality and interaction by users or other systems

> [!IMPORTANT]
> The ability to restrict or rectify data in system-generated logs isn't supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft Cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### Executing DSRs against system-generated logs

- [System-Generated logs Data Subject Rights Requests Processes](/compliance/regulatory/gdpr-dsr-dynamics365#part-2-responding-to-dsrs-for-system-generated-logs) for Dynamics 365 Project Operations
