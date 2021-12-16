---
title: Project Service Automation Upgrade to Project Operations Overview
description: This topic provides an overview of the process to upgrade from Project Service Automation to Project Operations.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 12/19/2021
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
Introduction
============

As a team we are excited to announce the first of three phases of upgrade to
Project Operations from our existing Project Service Automation (PSA). For
customers embarking on this exciting journey we are providing this documentation
along with future articles which include developer considerations and details on
the feature enhancements to provide guidance on not only how to prepare for your
upgrade but what to expect once you have upgraded to Project Operations. The
upgrade delivery program will be split into the 3 phases as described below:

|                                                                                                                     | **Phase 1 (January 2022)** | **Phase 2 (April Wave 2022)** | **Phase 3 (April Wave 2022)** |
|---------------------------------------------------------------------------------------------------------------------|----------------------------|-------------------------------|-------------------------------|
| No dependency on WBS for projects                                                                                   | :heavy_check_mark:                          | :heavy_check_mark:                          | :heavy_check_mark:                            |
| WBS within the currently supported limits of Project Operations                                                     |                            | :heavy_check_mark:                            | :heavy_check_mark:                             |
| WBS outside the currently supported limits of Project Operations including support for the Microsoft Desktop client |                            |                               | :heavy_check_mark:                             |

Features of the upgrade process
===============================

As part of the upgrade process, we have added upgrade logs to the site map to
make it easier for administrators to diagnose failures. Along with the new
interface, there are new validation rules which will be added to ensure valid
data is store post upgrade. The following validations will be added to the
upgrade process:

|                                                                                                                                                                                                   | **Phase 1 (January 2022)** | **Phase 2 (April Wave 2022)** | **Phase 3 (April Wave 2022)** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|-------------------------------|-------------------------------|
| The work breakdown structure will be validated against common data integrity violations (e.g. Resource assignments are associated with the same parent task but have a different parent projects) |                            | ü                             | ü                             |
| The work breakdown structure will be validated against the [known limits of Project for the Web](https://docs.microsoft.com/en-us/project-for-the-web/project-for-the-web-limits-and-boundaries)  |                            | ü                             | ü                             |
| The work breakdown structure will be validated against the know limits of the Microsoft Project Desktop Client                                                                                    |                            | ü                             | ü                             |
| Bookable resources and project calendars will be evaluated against common incompatible calendar rule exceptions                                                                                   |                            | ü                             | ü                             |

In Phase 2, Customers who choose to upgrade to Project Operations will have
their existing projects upgraded to a read only experience in project planning.
To edit their work breakdown structures (WBS), Project Managers will select
**Convert** from the project main form. This background process will update the
project to support the new project scheduling experience from Project for the
Web. This phase is appropriate for customers who have projects that fit within
the [known limits of Project for the
Web](https://docs.microsoft.com/en-us/project-for-the-web/project-for-the-web-limits-and-boundaries).
In Phase 3, supported will be added for the desktop client and customers who
wish to continue editing their projects from the desktop client will be afforded
that option. However, if they choose to convert their existing projects to the
new Project for the Web experience, access to the add-in will be disabled.

Prerequisites
=============

To be eligible for the Phase 1 upgrade, customers must meet the following
criteria:

1.  The target environments must not contain any records in the
    **msdyn_projecttask** entity.

2.  Customers must have valid Project Operations licenses assigned to all active
    users.
    
3.  Customers must validate upgrade process in at least one non-production
    environment with a representative dataset aligned to production data.

4.  The target environment must be updated to Project Service Automation Update Release 38 or newer.

Prerequisites for Phase 2 and Phase 3 will be updated as we approach the general
availability dates.

Licensing
=========

Currently licensed Project Service Automation customers are entitled through
grandfathering to install and use Project Operations, this allows you to install
and test the Project Operations capabilities while continuing to utilize PSA in
production. Once your PSA license expires you will need to transition over to
Project Operations which includes all the capabilities of PSA and more. However,
the Project Operations license does not include a license to PSA 3.x, this
should be accounted for in planning for your transition.


Testing and Refactoring Customizations
--------------------------------------

As a starting point, in a clean Project Operations (lite) environment, customers should import
all customizations to confirm import is successful and that business operations
are behaving as expected.

Things to be on the lookout for

1.  Import may fail due to missing dependencies.

>   This will happen if the customizations reference fields or other components
>   that have been removed in Project Operations. In such cases, customers should revisit their development environment and remove these dependencies.

1.  If your unmanaged and managed solutions include components that are not
    customized, remove those components form the solution. For
    instance, when customizing the Project entity, it is important to
    add only the entity header itself and not all fields to your solution. If
    you have previously added all sub components, you may have to manually
    create a new solution and readd relevant components to that solution.

2.  Forms and views may not appear as unexpected.

    If you have customized any of the forms or views we ship out of the box,
    such customizations may under certain circumstances block new updates in
    Project Operations from taking effect.

    In order to identify such issues, we recommend reviewing side by side a
    clean install of Project Operations with an install of Project Operations
    with your customizations on top. Compare the most commonly used forms in
    your business, to confirm that your version of the form still makes sense
    and is not missing something from the clean version of the form.

    Do the same for any views that you have customized.

3.  Business logic may fail at runtime

    Since references to fields in your plugins are not validated at import time,
    it is possible that you will have business logic failing due to references
    to fields that no longer exist.

    In this case you might see an error similar to “**'Project' entity
    doesn't contain attribute with Name = 'msdyn_plannedhours' and NameMapping =
    'Logical'**".

    In such cases, modify your customizations to use the new fields as per the
    table shared elsewhere in this document.

    If you use auto-generated proxy classes and strong type references in your
    plugin logic, you may consider regenerating those proxies from a clean
    installation. This would allow you to easily identify all the places where
    your plugins depend on deprecated fields.

Once you have updated your customizations to cleanly import on Project
Operations, you can proceed to the next steps.

Testing end to end in lower environments
----------------------------------------

Executing upgrade in production
-------------------------------

1.  In the Power Platform Admin Center (PPAC), locate your environment, then go to applications and find **Dynamics 365 Project
    Operations**. Click **Install** to initiate the upgrade. Note that PPAC will
    present this as a new install, but behind the scenes we will detect the
    presence of an earlier version of Project Service Automation, and the
    existing installation will be upgrade.

    Once upgrade is completed, the environment should show Project Operations as
    being installed, while Project Service Automation will show as not
    installed.

    Note: Depending on the amount of data in the environment, this upgrade may
    take several hours to complete. The core team managing the upgrade should plan accordningly and execute the upgrade in non-business hours.  In som einstances, if the data volume is large, the upgrade run should be executed during the weekend.   The scheduling of this decision should be based on testing in lower
    environments.

2.  Upgrade any custom solutions as applicable. You will likely have made
    changes to your customizations in the “Testing and Refactoring
    Customizations” step above, and now is the time to deploy these.

3.  Uninstall the Project Operations Deprecated Components solution.

    This solution is meant as a temporary solution that existing data model and
    components are present during upgrade. Step 2 above should remove all
    dependencies on these components. By removing this solution, you remove all
    the fields and components no longer used, which allows for a simpler
    interface and easier integration/extension.

Overview of major changes between Project Service Automation (PSA) and Project Operations
=========================================================================================

The [Feature Changes](docs.microsoft.com) article provides an in-depth analysis
of all the changes between PSA and Project Operations. The list below is a
summary of what users can expect.

Project Planning
----------------

The project planning capabilities in Project Operations no longer rely upon
combination client side and server side logic, rather, Project Operations
leverages Project for the Web as its scheduling engine. This change in
scheduling capabilities enables several new features including but not limited
to: Board and Gantt Views, Resource Driven Planning, [Task Checklist
Items](https://support.microsoft.com/en-us/office/use-task-checklists-in-microsoft-project-for-the-web-c69bcf73-5c75-4ad3-9893-6d6f92360e9c)
and Project Scheduling Modes. The new scheduling capabilities are also supported
by a rich set of new APIs geared towards ensuring that any programmatic
operations to create, update or delete an entity in the work breakdown structure
do not corrupt the calculated fields in the schedule.

Billing and Pricing
-------------------

As part of our continuing investments in Project Operations we have launch a
number new capabilities in Billing and Pricing, including the following:

-   [Recording material usage on projects and project
    tasks](https://docs.microsoft.com/en-us/dynamics365/project-operations/material/material-usage-log)

-   [Subcontract
    management](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/subcontracting/managing-subcontracts-overview)

-   [Advances and retainer-based
    contracts](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/sales/set-up-advances-retainer-based-contracts-sales)

-   [Contract not-to-exceed status and
    validations](https://docs.microsoft.com/en-us/dynamics365/project-operations/pro/proforma-invoicing/manage-nte-status-validations-sales)

-   Task based billing

Frequently Asked Questions
==========================

**Which deployment types are currently supported for upgrade?**

| **Source**                                     | **Target**                                                | **Status**              |
|------------------------------------------------|-----------------------------------------------------------|-------------------------|
| Project Service Automation                     | Project Operations Lite Deployment                        | Supported               |
| D365 Finance Project Management and Accounting | Project Operations Lite Deployment                        | Not currently supported |
| D365 Finance Project Management and Accounting | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| D365 Finance Project Management and Accounting | Project Operations for stocked/production order scenarios | Not currently supported |
| Project Service Automaton (PSA 3.x)            | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| Project for the Web (dedicated environment)    | Project Operations Lite Deployment                        | Not currently supported |

**How can install Project Operations before the upgrade tooling is available?**

There are two options:

1.  Provision a new environment or deploy Project Operations separately on any
    sales org where Project Service Automation (PSA) is not present.

2.  If Project Service Automation is installed on an organization but was not
    used, it can be uninstalled. Once the removal of PSA is complete, Project
    Operations can be installed on the same organization.
