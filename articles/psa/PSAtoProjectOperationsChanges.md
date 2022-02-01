---
title: Upgrade from Project Service Automation to Project Operations
description: This topic provides an overview of the process to upgrade from Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Project Operations.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 01/31/2022
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
---

# Upgrade from Project Service Automation to Project Operations

The upgrade from Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Project Operations Lite  will be delivered in three phases.  This article will outline all major changes customers can expect to see when the upgrade has completed.

| Upgrade delivery | Phase 1 (January 2022) | Phase 2 (April Wave 2022) | Phase 3 (April Wave 2022) |
|------------------|------------------------|---------------------------|---------------------------|
| No dependency on the work breakdown structure (WBS) for projects | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| The WBS within the currently supported limits of Project Operations | | :heavy_check_mark: | :heavy_check_mark: |
| The WBS outside the currently supported limits of Project Operations, including support for the Project desktop client | | | :heavy_check_mark: |

Project Management
==================

The most significant changes in the user experience for customer will be in the
area of Project Planning. Project Operations adopts a new modern experience for
managing a work breakdown structure by leveraging the scheduling capabilities
provided by [Project for the
Web](https://support.microsoft.com/en-us/office/what-is-project-for-the-web-c19b2421-3c9d-4037-97c6-f66b6e1d2eb5).

Differences in Scheduling Experience
------------------------------------

The table below summarizes the differences in scheduling in Project Service
Automation vs Project Operations.

|                                                                                                                               | **Project Operations** | **PSA** |
|-------------------------------------------------------------------------------------------------------------------------------|------------------------|---------|
| **Project Templates**                                                                                                         |                        | :heavy_check_mark:       |
| Ability to define project templates and apply them when a project is created.                                                 |                        |         |
| **Project work breakdown structure (WBS)**                                                                                    |                        |  :heavy_check_mark:     |
| WBS integration with desktop client                                                                                           |                        |         |
| **Constraints**                                                                                                               | :heavy_check_mark:                     |         |
| Start no earlier than, finish no later than                                                                                   |                        |         |
| **Milestones**                                                                                                                | :heavy_check_mark:                   |         |
| tasks with zero duration                                                                                                      |                        |         |
| **Resource Driven tasks**                                                                                                     |:heavy_check_mark:                     |         |
| tasks will respect the availability of assigned resources                                                                     |                        |         |
| **Time-Phased Editing**                                                                                                       |                        | :heavy_check_mark:       |
| Edit plans and work on a day-by-day basis.                                                                                    |                        |         |
| **Automatic / Manual Scheduling**                                                                                             |                        | :heavy_check_mark:       |
| Use the Project scheduling engine to automatically schedule tasks, or do it manually.                                         |                        |         |
| **Edit Large Projects directly in the user interface**                                                                        | 500 task limit         | :heavy_check_mark:       |
| No limit to the size of plans that are editable.                                                                              |                        |         |
| **% Complete**                                                                                                                | :heavy_check_mark:                      |         |
| Mark task progress as a percentage of the assigned work that is complete.                                                     |                        |         |
| [Project Schedule Modes](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/scheduling-modes) | :heavy_check_mark:                      |         |
| Define the project as fixed units, fixed effort or fixed duration                                                             |                        |         |
| **Timeline**                                                                                                                  | :heavy_check_mark:                      |         |
| Build and customize the timeline view to visualize schedule details and communicate with stakeholders.                        |                        |         |
| **Effort-Driven Tasks**                                                                                                       | :heavy_check_mark:                      |         |
| Scheduling engine support for scheduling a task as effort driven.                                                             |                        |         |
| **Task Information Dialog**                                                                                                   | :heavy_check_mark:                     |         |
| See task details by using a dialog interface.                                                                                 |                        |         |
| **Drag and Drop**                                                                                                             | :heavy_check_mark:                     |         |
| Multi-select tasks and modify their position on the WBS                                                                       |                        |         |
| **Flexible Persistent Views**                                                                                                 | :heavy_check_mark:                      |         |
| Allow users define more granular views of task attributes                                                                     |                        |         |
| **Sorting / Filtering**                                                                                                       | :heavy_check_mark:                     |         |
| Sort or filter the WBS                                                                                                        |                        |         |
| **Boards view**                                                                                                               | :heavy_check_mark:                      |         |
| Boards views for non-waterfall project delivery                                                                               |                        |         |
| **Timeline view**                                                                                                             | :heavy_check_mark:                      |         |
| Interactive gantt chart used to visualize and edit the WBS                                                                    |                        |         |
| **Keyboard Shortcuts**                                                                                                        | :heavy_check_mark:                      |         |
| Use keyboard shortcuts for common operations, such as indent or insert.                                                       |                        |         |
| **Multi-level Undo**                                                                                                          | :heavy_check_mark:                      |         |
| Perform what-if analysis and fully understand the impact of changes by reversing and reapplying an entire set of operations.  |                        |         |
| **Cut / Copy / Paste**                                                                                                        | :heavy_check_mark:                     |         |
| Collaborate on schedule development by copying/pasting schedule details between applications.                                 |                        |         |
| **Task checklists**                                                                                                           | :heavy_check_mark:                      |         |
| Add up to 20 checklist items to a task                                                                                        |                        |         |

Project Planning User Interface
-------------------------------

The default Project main form has a number of notable differences compared to
PSA as highlighted below:

The following ribbon actions have been removed as part of the Phase 1 upgrade:

-   Open in MS Project

-   Create Template

-   Unlink from MS Project

The main form now includes new tabs including:

-   Material Estimates

-   Task Billing Setup

The Status tab has been removed and the status field now appear on the summary
tab along with the project’s scheduling mode.

![updates to the project form](media/projectform.png)

The schedule tab has been renamed to the Task tab and features the new project
planning experience with Project for the Web.

![new project tasks tab](media/tasktab.png)

Scheduling Modes
----------------

Project Operations has introduced a new feature, [Scheduling
Modes](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/scheduling-modes).
All existing PSA Projects will be defaulted to **Fixed Duration**. However,
defaulting for new projects can be managed In **Settings \> Parameters \>
Parameter \> Schedule Mode.**

![Project Parameter settings for schedule mode](media/projectparameter.png)



Project Planning limits
-----------------------
Project Oeprations relies upon Project for the Web for all project shceduling operations.   Project for the Web manages the work breakdown structure with the limits outlined below:

| **Field**                                          | **Limit**            |
|----------------------------------------------------|----------------------|
| Maximum total tasks for a project                  | 500                  |
| Maximum total duration for a project               | 3650 days (10 years) |
| Maximum total resources for a project              | 300                  |
| Maximum total links (successor only) for a project | 600                  |
| Maximum total custom fields for a project          | 10                   |
| Maximum hierarchy level                 | 10 levels             |
| Maximum links (successor + predecessor) | 20                    |
| Maximum duration of leaf task           | 1250 days             |
| Maximum duration of a summary task      | 3650 days (10 years)  |
| Maximum resources assigned to a task    | 20 resources          |
| Supported date range for a task         | 1/1/2000 - 12/31/2149 |
| Checklist items                         | 20                    |

Project Templates
-----------------

Project Operations does not provide native support for project templates.
However, customers can replicate much of the core functionality with the use of
the [Project Copy
API](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/dev-copy-project).

Desktop Addin support
---------------------

Support for the Microsoft Project Desktop add-in will not be available in the
first 2 phases of the upgrade. In Phase 3, customers who have projects larger
than the currently supported limits of Project for the Web will be able to use

Editing Resource Assignment Contours
------------------------------------

The ability to edit resource assignment contours will be available when Phase 2
of upgrade is available.

Project Planning Extensibility and development
----------------------------------------------

Once upgraded to Project Operations, customers will be required to leverage
Project Scheduling APIs to execute create, update and delete operations on the
following entities:

| **Entity name**         | **Entity logical name**     |
|-------------------------|-----------------------------|
| Project                 | msdyn_project               |
| Project Task            | msdyn_projecttask           |
| Project Task Dependency | msdyn_projecttaskdependency |
| Resource Assignment     | msdyn_resourceassignment    |
| Project Bucket          | msdyn_projectbucket         |
| Project Team Member     | msdyn_projectteam           |

Customers who currently have customizations involving these entities should
refer to the [Project Scheduling API
documentation](https://docs.microsoft.com/en-us/dynamics365/project-operations/project-management/schedule-api-preview)
for implementation guidance.

Data Model Changes
------------------

As part of Upgrade Phase 1, there are changes to the data model (primarily field
changes to existing entities).  In Phase 1, the following entities are of 
refactoring of customizations: **msydn_project** and **msdyn_projectteam**.  Please note, this section will updated with other entities as future upgrade phases are completed.

The following fields have been replaced by the new fields.

| **Entity**        | **Old Logical Name** | **New Logical Name**  |
|-------------------|----------------------|-----------------------|
| msdyn_project     | msdyn_actualhours    | msdyn_effortcompleted |
| msdyn_project     | msdyn_plannedhours   | msdyn_effort          |
| msdyn_project     | msdyn_remaininghours | msdyn_effortremaining |
| msdyn_project     | msdyn_scheduledend   | msdyn_finish          |
| msdyn_project     | msdyn_wbsduration    | msdyn_duration        |
| msdyn_projectteam | msdyn_assignedhours  | msdyn_effort          |
| msdyn_projectteam | msdyn_from           | msdyn_start           |
| msdyn_projectteam | msdyn_to             | msdyn_finish          |

The following fields have been added:

| **Entity**        | **Logical Name**                             | **Description**                                                                                                                                                                   |
|-------------------|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| msdyn_project     | msdyn_actualfeesales                         | Shows the aggregate of actual fee sales on the project - For PSA use only                                                                                                         |
| msdyn_project     | msdyn_actualmaterialcost                     | Shows the aggregate of actual material cost on the project - For PSA use only                                                                                                     |
| msdyn_project     | msdyn_actualmaterialsales                    | Shows the aggregate of actual material sales on the project - For PSA use only                                                                                                    |
| msdyn_project     | msdyn_businesscase                           |                                                                                                                                                                                   |
| msdyn_project     | msdyn_contractlineproject                    | The Contract Line associated with this project                                                                                                                                    |
| msdyn_project     | msdyn_copyprojectcorrelationid               | This is an internal field, used for Copy Project related Correlation Identifier. System Field - For PSA Use Only.                                                                 |
| msdyn_project     | msdyn_copyprojectsessionid                   | This is an internal field, used for Copy Project related Session Identifier. System Field - For PSA Use Only.                                                                     |
| msdyn_project     | msdyn_globalrevisiontoken                    | Last sync xRM Global Revision Token from PSS                                                                                                                                      |
| msdyn_project     | msdyn_msprojectdocument                      | The MS Project document belonging to the project                                                                                                                                  |
| msdyn_project     | msdyn_plannedmaterialcost                    | Shows the aggregate of planned material cost on the project - For PSA use only                                                                                                    |
| msdyn_project     | msdyn_plannedmaterialsales                   | Shows the aggregate of planned material sales on the project - For PSA use only                                                                                                   |
| msdyn_project     | msdyn_program                                | The program this project is related to.                                                                                                                                           |
| msdyn_project     | msdyn_quotelineproject                       | The Quote Line associated with this project                                                                                                                                       |
| msdyn_project     | msdyn_replaylogheader                        | Header for the replay logs.                                                                                                                                                       |
| msdyn_project     | msdyn_schedulemode                           | Default Scheduling Mode used for all tasks on the project                                                                                                                         |
| msdyn_project     | msdyn_taskearlieststart                      | The earliest start date of any task in the project.                                                                                                                               |
| msdyn_project     | msdyn_valuestatement                         |                                                                                                                                                                                   |
| msdyn_projectteam | msdyn_copiedfromprojectteammember            | Shows the project team member that this project team member was copied from.                                                                                                      |
| msdyn_projectteam | msdyn_creategenericteammemberwithrequirement | Indicate whether to create the resource requirement for a newly created generic team member.                                                                                      |
| msdyn_projectteam | msdyn_deletestatus                           | The delete status of the team member to track whether there is a delete request sent to PSS and whether PSS sends back response successfully and within the expected time window. |
| msdyn_projectteam | msdyn_effortcompleted                        | Completed hours tracks the effort accomplished by the team member on their assignments.                                                                                           |
| msdyn_projectteam | msdyn_effortremaining                        | Remaining hours tracks the effort yet to be completed by the team member on their assignments.                                                                                    |
| msdyn_projectteam | msdyn_markedfordeletiontimer                 | The waiting period from team member delete request is sent to PSS till the team member is actually deleted on CDS.                                                                |
| msdyn_projectteam | msdyn_markedfordeletiontimestamp             | The timestamp to record when team member delete request is sent to PSS.                                                                                                           |
| msdyn_projectteam | msdyn_copiedfromprojectteammember            | Shows the project team member that this project team member was copied from.                                                                                                      |


Billing and Pricing
===================

The following new features have been added in Project Operations, these features
are additive in nature and do not impact the data model of PSA:

-   [Recording material usage on projects and project
    tasks](https://docs.microsoft.com/en-us/dynamics365/project-operations/material/material-usage-log)

-   [Subcontract
    management](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/subcontracting/managing-subcontracts-overview)

-   [Advances and retainer-based
    contracts](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/sales/set-up-advances-retainer-based-contracts-sales)

-   [Contract not-to-exceed status and validations
    ](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/proforma-invoicing/manage-nte-status-validations-sales)

-   [Task based
    billing](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/sales/mapping-projects-tasks-quote-line-sales)

Deprecated Components
=====================

The following tables document all deprecated fields that are moved to the
deprecated components solution post upgrade, see [this
article](https://github.com/microsoft/Dynamics365-Project-Operations-PowerApps/tree/main/3x-4x-deprecated-solution)
for more details and a link to the solution.

| Fields                                                    |
|-----------------------------------------------------------------------------------------------|
|invoicedetail.msdyn_contractline    |
| msdyn_actual.msdyn_salescontractline                                                          |
| msdyn_characteristicreqforteammember.msdyn_characteristic                                     |
| msdyn_characteristicreqforteammember.msdyn_characteristicreqforteammemberid                   |
| msdyn_characteristicreqforteammember.msdyn_characteristictype                                 |
| msdyn_characteristicreqforteammember.msdyn_name                                               |
| msdyn_characteristicreqforteammember.msdyn_ratingvalue                                        |
| msdyn_characteristicreqforteammember.msdyn_resourcerequirementid                              |
| msdyn_contractlineinvoiceschedule.msdyn_contractline                                          |
| msdyn_contractlinescheduleofvalue.msdyn_contractline                                          |
| msdyn_dataexport.msdyn_dataexportid                                                           |
| msdyn_dataexport.msdyn_datatoken                                                              |
| msdyn_dataexport.msdyn_entityname                                                             |
| msdyn_dataexport.msdyn_exportedrecordcount                                                    |
| msdyn_dataexport.msdyn_exportstatus                                                           |
| msdyn_dataexport.msdyn_linkedentitydata                                                       |
| msdyn_dataexport.msdyn_name                                                                   |
| msdyn_dataexport.msdyn_pagingdata                                                             |
| msdyn_fact.msdyn_salescontractline                                                            |
| msdyn_findworkevent.msdyn_bookableresource                                                    |
| msdyn_findworkevent.msdyn_findworkeventid                                                     |
| msdyn_findworkevent.msdyn_name                                                                |
| msdyn_findworkevent.msdyn_timestamp                                                           |
| msdyn_findworkevent.msdyn_type                                                                |
| msdyn_findworkevent.msdyn_value                                                               |
| msdyn_findworkevent.msdyn_work                                                                |
| msdyn_invoicelinetransaction.msdyn_invoiceline                                                |
| msdyn_invoicelinetransaction.msdyn_salescontractline                                          |
| msdyn_journalline.msdyn_salescontractline                                                     |
| msdyn_opportunitylineresourcecategory.msdyn_billingtype                                       |
| msdyn_opportunitylineresourcecategory.msdyn_description                                       |
| msdyn_opportunitylineresourcecategory.msdyn_opportunitylineresourcecategoryid                 |
| msdyn_opportunitylineresourcecategory.msdyn_opportunitylinetransactionclassification          |
| msdyn_opportunitylineresourcecategory.msdyn_resourcecategory                                  |
| msdyn_opportunitylinetransaction.msdyn_accountcustomer                                        |
| msdyn_opportunitylinetransaction.msdyn_accountingdate                                         |
| msdyn_opportunitylinetransaction.msdyn_accountvendor                                          |
| msdyn_opportunitylinetransaction.msdyn_amount                                                 |
| msdyn_opportunitylinetransaction.msdyn_amount_base                                            |
| msdyn_opportunitylinetransaction.msdyn_amountmethod                                           |
| msdyn_opportunitylinetransaction.msdyn_basisamount                                            |
| msdyn_opportunitylinetransaction.msdyn_basisamount_base                                       |
| msdyn_opportunitylinetransaction.msdyn_basisprice                                             |
| msdyn_opportunitylinetransaction.msdyn_basisprice_base                                        |
| msdyn_opportunitylinetransaction.msdyn_basisquantity                                          |
| msdyn_opportunitylinetransaction.msdyn_billingtype                                            |
| msdyn_opportunitylinetransaction.msdyn_bookableresource                                       |
| msdyn_opportunitylinetransaction.msdyn_contactcustomer                                        |
| msdyn_opportunitylinetransaction.msdyn_contactvendor                                          |
| msdyn_opportunitylinetransaction.msdyn_customertype                                           |
| msdyn_opportunitylinetransaction.msdyn_description                                            |
| msdyn_opportunitylinetransaction.msdyn_documentdate                                           |
| msdyn_opportunitylinetransaction.msdyn_enddatetime                                            |
| msdyn_opportunitylinetransaction.msdyn_exchangeratedate                                       |
| msdyn_opportunitylinetransaction.msdyn_opportunityline                                        |
| msdyn_opportunitylinetransaction.msdyn_opportunitylinetransactionid                           |
| msdyn_opportunitylinetransaction.msdyn_percent                                                |
| msdyn_opportunitylinetransaction.msdyn_price                                                  |
| msdyn_opportunitylinetransaction.msdyn_price_base                                             |
| msdyn_opportunitylinetransaction.msdyn_pricelist                                              |
| msdyn_opportunitylinetransaction.msdyn_product                                                |
| msdyn_opportunitylinetransaction.msdyn_project                                                |
| msdyn_opportunitylinetransaction.msdyn_quantity                                               |
| msdyn_opportunitylinetransaction.msdyn_resourcecategory                                       |
| msdyn_opportunitylinetransaction.msdyn_resourceorganizationalunitid                           |
| msdyn_opportunitylinetransaction.msdyn_startdatetime                                          |
| msdyn_opportunitylinetransaction.msdyn_task                                                   |
| msdyn_opportunitylinetransaction.msdyn_transactioncategory                                    |
| msdyn_opportunitylinetransaction.msdyn_transactionclassification                              |
| msdyn_opportunitylinetransaction.msdyn_transactiontypecode                                    |
| msdyn_opportunitylinetransaction.msdyn_unit                                                   |
| msdyn_opportunitylinetransaction.msdyn_unitschedule                                           |
| msdyn_opportunitylinetransaction.msdyn_vendortype                                             |
| msdyn_opportunitylinetransactioncategory.msdyn_billingtype                                    |
| msdyn_opportunitylinetransactioncategory.msdyn_description                                    |
| msdyn_opportunitylinetransactioncategory.msdyn_opportunitylinetransactioncategoryid           |
| msdyn_opportunitylinetransactioncategory.msdyn_opportunitylinetransactionclassification       |
| msdyn_opportunitylinetransactioncategory.msdyn_transactioncategory                            |
| msdyn_opportunitylinetransactionclassificatio.msdyn_billingtype                               |
| msdyn_opportunitylinetransactionclassificatio.msdyn_description                               |
| msdyn_opportunitylinetransactionclassificatio.msdyn_include                                   |
| msdyn_opportunitylinetransactionclassificatio.msdyn_opportunityline                           |
| msdyn_opportunitylinetransactionclassificatio.msdyn_opportunitylinetransactionclassificatioid |
| msdyn_opportunitylinetransactionclassificatio.msdyn_transactionclassification                 |
| msdyn_orderlineresourcecategory.msdyn_contractline                                            |
| msdyn_orderlinetransaction.msdyn_salescontractline                                            |
| msdyn_orderlinetransactioncategory.msdyn_contractline                                         |
| msdyn_orderlinetransactionclassification.msdyn_contractline                                   |
| msdyn_project.msdyn_actualdurationminutes                                                     |
| msdyn_project.msdyn_actualhours                                                               |
| msdyn_project.msdyn_istemplate                                                                |
| msdyn_project.msdyn_plannedhours                                                              |
| msdyn_project.msdyn_projecttemplate                                                           |
| msdyn_project.msdyn_remaininghours                                                            |
| msdyn_project.msdyn_scheduleddurationminutes                                                  |
| msdyn_project.msdyn_scheduledend                                                              |
| msdyn_project.msdyn_stagename                                                                 |
| msdyn_project.msdyn_wbsduration                                                               |
| msdyn_projecttask.msdyn_actualdurationminutes                                                 |
| msdyn_projecttask.msdyn_actualeffort                                                          |
| msdyn_projecttask.msdyn_aggregationdirection                                                  |
| msdyn_projecttask.msdyn_assignedresources                                                     |
| msdyn_projecttask.msdyn_assignedteammembers                                                   |
| msdyn_projecttask.msdyn_autoscheduling                                                        |
| msdyn_projecttask.msdyn_costestimatecontour                                                   |
| msdyn_projecttask.msdyn_effortcontour                                                         |
| msdyn_projecttask.msdyn_islinetask                                                            |
| msdyn_projecttask.msdyn_numberofresources                                                     |
| msdyn_projecttask.msdyn_remaininghours                                                        |
| msdyn_projecttask.msdyn_resourceutilization                                                   |
| msdyn_projecttask.msdyn_salesestimatecontour                                                  |
| msdyn_projecttask.msdyn_scheduledhours                                                        |
| msdyn_projecttask.msdyn_wbsid                                                                 |
| msdyn_projecttaskstatususer.msdyn_bookableresource                                            |
| msdyn_projecttaskstatususer.msdyn_description                                                 |
| msdyn_projecttaskstatususer.msdyn_expectedcompletiondate                                      |
| msdyn_projecttaskstatususer.msdyn_expectedhourstocomplete                                     |
| msdyn_projecttaskstatususer.msdyn_iscompleted                                                 |
| msdyn_projecttaskstatususer.msdyn_name                                                        |
| msdyn_projecttaskstatususer.msdyn_percentcomplete                                             |
| msdyn_projecttaskstatususer.msdyn_projecttaskid                                               |
| msdyn_projecttaskstatususer.msdyn_projecttaskstatusindicator                                  |
| msdyn_projecttaskstatususer.msdyn_projecttaskstatususerid                                     |
| msdyn_projectteam.msdyn_applicantcount                                                        |
| msdyn_projectteam.msdyn_applicantsavailable                                                   |
| msdyn_projectteam.msdyn_assignedhours                                                         |
| msdyn_projectteam.msdyn_description                                                           |
| msdyn_projectteam.msdyn_from                                                                  |
| msdyn_projectteam.msdyn_hoursrequested                                                        |
| msdyn_projectteam.msdyn_membershipstatus                                                      |
| msdyn_projectteam.msdyn_number                                                                |
| msdyn_projectteam.msdyn_to                                                                    |
| msdyn_projectteammembersignup.msdyn_bookableresource                                          |
| msdyn_projectteammembersignup.msdyn_membershipstatus                                          |
| msdyn_projectteammembersignup.msdyn_name                                                      |
| msdyn_projectteammembersignup.msdyn_projectteammembersignupid                                 |
| msdyn_projectteammembersignup.msdyn_teammembership                                            |
| msdyn_projecttransactioncategory.msdyn_billingtype                                            |
| msdyn_projecttransactioncategory.msdyn_name                                                   |
| msdyn_projecttransactioncategory.msdyn_project                                                |
| msdyn_projecttransactioncategory.msdyn_projecttransactioncategoryid                           |
| msdyn_projecttransactioncategory.msdyn_transactioncategory                                    |
| msdyn_quotelineinvoiceschedule.msdyn_quoteline                                                |
| msdyn_quotelineresourcecategory.msdyn_quoteline                                               |
| msdyn_quotelinescheduleofvalue.msdyn_quoteline                                                |
| msdyn_quotelinetransaction.msdyn_quoteline                                                    |
| msdyn_quotelinetransactioncategory.msdyn_quoteline                                            |
| msdyn_quotelinetransactionclassification.msdyn_quoteline                                      |
| msdyn_resourceassignment.msdyn_hours                                                          |
| msdyn_resourceassignment.msdyn_fromdate                                                       |
| msdyn_resourceassignment.msdyn_msprojectclientid                                              |
| msdyn_resourceassignment.msdyn_todate                                                         |
| msdyn_resourceassignmentdetail.msdyn_duration                                                 |
| msdyn_resourceassignmentdetail.msdyn_from                                                     |
| msdyn_resourceassignmentdetail.msdyn_name                                                     |
| msdyn_resourceassignmentdetail.msdyn_resourceassignmentdetailid                               |
| msdyn_resourceassignmentdetail.msdyn_resourceassignmentid                                     |
| salesorderdetail.msdyn_quoteline                                                              |

