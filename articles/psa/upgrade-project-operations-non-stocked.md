---
title: Upgrade from Project Service Automation to Project Operations
description: This topic provides an overview of the process to upgrade from Project Service Automation to Project Operations.
author: ruhercul
ms.custom: dyn365-projectservice
ms.date: 01/03/2022
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

We are excited to announce the first of three phases of upgrade from Project Service Automation (PSA) to Project Operations. For customers embarking on this exciting journey, we are providing this overview along with future articles which will include developer considerations and details on the feature enhancements to provide guidance on not only how to prepare for your upgrade but also what to expect once you have upgraded to Project Operations. The upgrade delivery program will be split into the three phases.

|          Upgrade delivery                                                                                                |   Phase 1 (January 2022)   |   Phase 2 (April Wave 2022)   |  Phase 3 (April Wave 2022)   |
|---------------------------------------------------------------------------------------------------------------------|----------------------------|-------------------------------|-------------------------------|
| No dependency on work breakdown structure for projects.                                                                                   | :heavy_check_mark:                          | :heavy_check_mark:                          | :heavy_check_mark:                            |
| Work breakdown structure within the currently supported limits of Project Operations.                                                    |                            | :heavy_check_mark:                            | :heavy_check_mark:                             |
| Work breakdown structure outside the currently supported limits of Project Operations including support for the Microsoft Desktop client. |                            |                               | :heavy_check_mark:                             |

## Upgrade process features 

As part of the upgrade process, we have added upgrade logs to the site map to make it easier for administrators to diagnose failures. Along with the new interface, there are new validation rules which will be added to ensure data integrity post upgrade. The following validations will be added to the upgrade process.

|    Validations                                                                                                                                                                                    |   Phase 1 (January 2022)   |   Phase 2 (April Wave 2022)   |   Phase 3 (April Wave 2022)   |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|-------------------------------|-------------------------------|
| The work breakdown structure will be validated against common data integrity violations. For example, Resource assignments are associated with the same parent task but have a different parent projects. |                            | :heavy_check_mark:                              | :heavy_check_mark:                            |
| The work breakdown structure will be validated against the [known limits of Project for the Web](/project-for-the-web/project-for-the-web-limits-and-boundaries).  |                            | :heavy_check_mark:                            | :heavy_check_mark:                             |
| The work breakdown structure will be validated against the know limits of the Microsoft Project Desktop Client.                                                                                    |                            | :heavy_check_mark:                             | :heavy_check_mark:                            |
| Bookable resources and project calendars will be evaluated against common incompatible calendar rule exceptions.                                                                                   |                            | :heavy_check_mark:                             | :heavy_check_mark:                            |

In Phase 2, Customers who choose to upgrade to Project Operations will have their existing projects upgraded to a read-only experience for project planning where the full work breakdown structure will be visible in the tracking grid. To edit the work breakdown structures (WBS), Project managers can select **Convert** from the main **Projects** page. This background process will update the project to support the new project scheduling experience from Project for the Web. This phase is appropriate for customers who have projects that fit within the [known limits of Project for the Web](/project-for-the-web/project-for-the-web-limits-and-boundaries). In Phase 3, support will be added for the Microft Project desktop client for customers who want to continue editing their projects from that application. However, if existing projects are converted to the new Project for the Web experience, access to the add-in will be disabled for each converted project.

## Prerequisites

To be eligible for the Phase 1 upgrade, customers must meet the following criteria:

- The target environments must not contain any records in the **msdyn_projecttask** entity.
- Customers must have valid Project Operations licenses assigned to all active users. 
- Customers must validate the upgrade process in at least one non-production environment with a representative dataset aligned to production data.
- The target environment must be updated to Project Service Automation Update Release 38 or later.

Prerequisites for Phase 2 and Phase 3 will be updated as we approach the general availability dates.

## Licensing

If you have active licenses for Project Service Automation, you can install and use Project Operations. This allows you to test capabilities while continuing to utilize Project Service Automation in production. After your Project Service Automation licenses expire, you will need to transition to Project Operations which includes all the capabilities of Project Service Automation and more. However, the Project Operations license doesn't include a Project Service Automation license, so this should be accounted for in planning for your transition.

## Testing and refactoring customizations

As a starting point, in a clean Project Operations (lite) environment, import all customizations to confirm import is successful and that business operations are behaving as expected.

Things to be on the lookout for:

- Import may fail because of missing dependencies. Import might fail if the customizations reference fields or other components that have been removed in Project Operations. In this case, remove these dependencies from the development environment.
- If your unmanaged and managed solutions include components that are not customized, remove those components from the solution. For example, when customizing the Project entity, add only the entity header to your solution and not all of the fields. If you have previously added all sub-components, you may have to manually create a new solution and re-add relevant components to that solution.
- Forms and views may not appear as unexpected. If you have customized any of the forms or views that are shipped out-of-the-box, under certain circumstances, the customizations may block new updates in Project Operations from taking effect. To identify such issues, we recommend completing a side-by-side review of a clean install of Project Operations with an install of Project Operations with your customizations on top. Compare the most commonly used forms in your business, to confirm that your version of the form still makes sense and is not missing something from the clean version of the form. Do the same side-by-side review for any views that you have customized.
- Business logic may fail at runtime. Because references to fields in your plug-ins aren't validated at import, it's possible that you will have business logic failing due to references to fields that no longer exist. In this case, you might see an error similar to “**'Project' entity doesn't contain attribute with Name = 'msdyn_plannedhours' and NameMapping = 'Logical'**". In this case, modify your customizations to use the new fields included in the table listed earlier in the topic. If you use auto-generated proxy classes and strong type references in your plug-in logic, consider regenerating those proxies from a clean installation. This allows you to easily identify all the places where your plug-ins depend on deprecated fields.

After you update your customizations to cleanly import Project Operations, proceed to the next steps.

## Testing end to end in lower environments

### Executing upgrade in production

1. In the Power Platform Admin Center (PPAC), locate your environment, and in the applications, find **Dynamics 365 Project Operations**. 
2. Select **Install** to initiate the upgrade. The PPAC will present this as a new install, but the presence of an earlier version of Project Service Automation will be detected, and the existing installation will be upgraded.

   After upgrade is complete, the environment should show that Project Operations is installed, and that Project Service Automation isn't installed.

   > [!NOTE]
   > Depending on the amount of data in the environment, this upgrade may take several hours to complete. The core team managing the upgrade should plan accordningly and complete the upgrade during non-business hours. In some instances, if the data volume is large, the upgrade run should be executed during the weekend. The scheduling of this decision should be based on the testing results in lower environments.

3. Upgrade any custom solutions as applicable. You will likely have made changes to your customizations in the **Testing and refactoring customizations** section above, and now it's the time to deploy these changes.
4. Go to **Settings** > **Solutions** and select to uninstall the **Project Operations Deprecated Components** solution.

    This solution is a temporary solution to house the existing data model and components that are present during upgrade. By removing this solution, you remove all the fields and components that are no longer used, which allows for a simpler interface and easier integration and extension.

## Major changes between Project Service Automation and Project Operations

The following sections provide a summary the major changes you can expect between Project Service Automation and Project Operations.

### Project planning

The project planning capabilities in Project Operations no longer rely on combination client-side and server-side logic. Instead, Project Operations leverages Project for the Web as its scheduling engine. This change in scheduling capabilities enables several new features including but not limited to, Board and Gantt views, Resource driven planning, [Task checklist items](https://support.microsoft.com/en-us/office/use-task-checklists-in-microsoft-project-for-the-web-c69bcf73-5c75-4ad3-9893-6d6f92360e9c), and Project scheduling modes. The new scheduling capabilities are also supported by a rich set of new [APIs](../project management/schedule-api-preview.md) that are geared towards ensuring that any programmatic operations to create, update, or delete an entity in the work breakdown structure don't corrupt the calculated fields in the schedule.

## Billing and pricing

As part of continuing investments in Project Operations, a number of new capabilities are available in Billing and pricing. These capabilities include:

- [Recording material usage on projects and project tasks](../material/material-usage-log.md)
- [Subcontract management](../pro/subcontracting/managing-subcontracts-overview.md)
- [Advances and retainer-based contracts](../pro/sales/set-up-advances-retainer-based-contracts-sales.md)
- [Contract not-to-exceed status and validations](../pro/proforma-invoicing/manage-nte-status-validations-sales.md)
- Task based billing

## Frequently asked questions

### Which deployment types are currently supported for upgrade?

| **Source**                                     | **Target**                                                | **Status**              |
|------------------------------------------------|-----------------------------------------------------------|-------------------------|
| Project Service Automation                     | Project Operations Lite Deployment                        | Supported               |
| D365 Finance Project Management and Accounting | Project Operations Lite Deployment                        | Not currently supported |
| D365 Finance Project Management and Accounting | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| D365 Finance Project Management and Accounting | Project Operations for stocked/production order scenarios | Not currently supported |
| Project Service Automaton (PSA 3.x)            | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| Project for the Web (dedicated environment)    | Project Operations Lite Deployment                        | Not currently supported |

### How can I install Project Operations before the upgrade tooling is available?

There are two options available to install Project Operations before the upgrade tooling is available:

- Provision a new environment
- Deploy Project Operations separately on any sales organization where Project Service Automation (PSA) isn't present.

> [!NOTE]
> If Project Service Automation is installed on an organization but was not used, it can be uninstalled. After you completely remove Project Service Automation, Project Operations can be installed on the same organization.
