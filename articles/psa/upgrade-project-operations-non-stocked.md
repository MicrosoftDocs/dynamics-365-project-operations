---
title: Upgrade from Project Service Automation to Project Operations
description: This article provides an overview of the process to upgrade from Microsoft Dynamics 365 Project Service Automation to Dynamics 365 Project Operations.
author: dishantpopli
ms.date: 07/02/2025
ms.topic: overview
ms.custom: 
  - bap-template
  - dyn365-projectservice
  - evergreen
ms.author: dishantpopli
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
ms.reviewer: johnmichalak
---

# Upgrade from Project Service Automation to Project Operations

We're excited to announce the second of three phases for upgrade from Microsoft Dynamics 365 Project Service Automation to Microsoft Dynamics 365 Project Operations. This article provides an overview for customers who are embarking on this exciting journey. 

The upgrade delivery program is split into three phases. Phase 3 is now live for customers.

| Upgrade delivery | Phase 1 (January 2022) | Phase 2 (November 2022) | Phase 3 (November 2023)  |
|------------------|------------------------|---------------------------|---------------------------|
| No dependency on the work breakdown structure (WBS) for projects | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| A WBS within the currently supported limits of Project Operations | | :heavy_check_mark: | :heavy_check_mark: |
| A WBS outside the currently supported limits of Project Operations, including support for the Project desktop client | | | :heavy_check_mark: |

## Upgrade process features 

As part of the upgrade process, upgrade logs are added to the site map to enable administrators to more easily diagnose failures. In addition to the new interface, new validation rules are added to ensure data integrity after an upgrade. The following validations are added to the upgrade process.

| Validations | Phase 1 (January 2022) | Phase 2 (November 2022) | Phase 3 (November 2023) |
|-------------|------------------------|---------------------------|---------------------------|
| The WBS is validated against common data integrity violations (for example, resource assignments that are associated with the same parent task but have different parent projects). | | :heavy_check_mark: | :heavy_check_mark: |
| The WBS is validated against the [known limits of Project for the Web](/project-for-the-web/project-for-the-web-limits-and-boundaries). | | :heavy_check_mark: | :heavy_check_mark: |
| The WBS is validated against the known limits of the Project desktop client. | |  | :heavy_check_mark: |
| Bookable resources and project calendars is evaluated against common incompatible calendar rule exceptions. | | :heavy_check_mark: | :heavy_check_mark: |


## Prerequisites


To be eligible for upgrade, you must meet the following criteria:

- Valid Project Operations licenses must be assigned to all active users. 
- You must validate the upgrade process in at least one nonproduction environment that contains a representative dataset that is aligned with your production environment.
- The target environment must be updated to the latest Project Service Automation available Release.
- Environments that contain projects that violate the [limits](../project-management/project-and-task-limitations.md) of Project for the Web are allowed to use the Microsoft Project desktop add-in for Project Operations (documentation [here](plan-work-in-project-operations-add-in.md)). Environments that don't contain a project with >500 tasks can't use the add-in.

With the release of phase 3 upgrade, individual projects need to upgrade separately from the environment. When a project is upgraded, it's built in Microsoft Project for the Web and is editable from the tasks tab within Project Operations. When the upgrade button is selected while viewing a project entity, validation checks commence to ensure the project conforms to the project and task [limits](../project-management/project-and-task-limitations.md) of Project for the Web. Projects that aren't or can't be upgraded can still be managed using [external scheduling](../project-management/external-scheduling.md) or the Project desktop add-in for Project Operations. Upgraded projects will no longer be editable using the Project desktop add-in.

## Licensing

If you have active licenses for Project Service Automation, you can install and use Project Operations, which includes all the capabilities of Project Service Automation and more. In this way, you can test the capabilities of Project Operations while you continue to use Project Service Automation in production. After your Project Service Automation licenses expire, you must transition to Project Operations. When you plan this transition, you must account for the fact that the Project Operations license doesn't include a Project Service Automation license.

## Testing and refactoring customizations

As a starting point, import all customizations into a clean Project Operations Lite environment to confirm that import is successful, and that business operations behave as expected.

Here are some things to watch out for:

- Import might fail because of missing dependencies. In other words, the customizations reference fields or other components that have been removed in Project Operations. In this case, remove these dependencies from the development environment.
- If your unmanaged and managed solutions include components that aren't customized, remove those components from the solution. For example, when you customize the **Project** entity, add only the entity header to your solution. Don't add all the fields. If you've previously added all subcomponents, you might have to manually create a new solution and add relevant components to it.
- Forms and views might not appear as expected. Under some circumstances, if you've customized any of the out-of-box forms or views, the customizations might prevent new updates in Project Operations from taking effect. To identify these issues, we recommend that you do a side-by-side review of a clean installation of Project Operations and an installation of Project Operations that includes your customizations. Compare the most commonly used forms in your business to confirm that your version of the form still makes sense and isn't missing something from the clean version of the form. Do the same type of side-by-side review for any views that you've customized.
- Business logic might fail at runtime. Because references to fields in your plug-ins aren't validated at the time of import, business logic might fail because of references to fields that no longer exist, and you might receive an error message that resembles the following example: "'Project' entity doesn't contain attribute with Name = 'msdyn_plannedhours' and NameMapping = 'Logical'." In this case, modify your customizations so that they use the new fields. If you use automatically generated proxy classes and strong type references in your plug-in logic, consider regenerating those proxies from a clean installation. In this way, you can easily identify all the places where your plug-ins depend on deprecated fields.

After you update your customizations to cleanly import Project Operations, move on to the next steps.

## End-to-end testing in development environments

### Initiate upgrade 

1. In the Power Platform admin center, find and select your environment. Then, in the applications, find and select **Dynamics 365 Project Operations**.
2. Select **Install** to start the upgrade. The Power Platform admin center presents this installation as a new installation. However, the presence of an earlier version of Project Service Automation is detected, and the existing installation will be upgraded.

    After the upgrade is completed, the environment should show that Project Operations is installed, and that Project Service Automation isn't installed.

    Depending on the amount of data in the environment, the upgrade might take several hours. The core team that is managing the upgrade should plan accordingly and run the upgrade during nonbusiness hours. In some cases, if the data volume is large, the upgrade should be run during the weekend. The decision about scheduling should be based on the testing results in lower environments.

3. Upgrade custom solutions as appropriate. At this point, deploy any changes that you made to your customizations in the [Testing and refactoring customizations](#testing-and-refactoring-customizations) section of this article.
4. Go to **make.powerapps.com**, select your environment from the drop-down in the top right of the portal, select **Solutions** from the left menu, select the **Project Operations Deprecated Components** solution and **Uninstall**.

    This solution is a temporary solution that holds the existing data model and components that are present during the upgrade. By removing this solution, you remove all the fields and components that are no longer used. In this way, you help simplify the interface and make integration and extension easier.
    
### Upgrade to Project Operations Lite

The following steps describe the upgrade process and associated error logging:

1. **PSA Version check:** To install Project Operations, you must have the latest Project Service Automation Release installed.
1. **Pre-validation:** When an administrator initiates an upgrade, the system runs a pre-validation operation on each entity that is core to the Project Operations solution. This step verifies that all entities references are valid, and it ensures that data that is related to the WBS is within the published limits of Project for the Web.
1. **Metadata upgrade:** After successful pre-validation, the system initiates changes to the schema and creates a deprecated components solution. You can remove this deprecated solution after you've completed all required refactoring of customizations. This step is the longest part of the upgrade process and can take up to four hours to be completed.
1. **Data upgrade:** After all required schema changes have been completed in the metadata upgrade step, your data is migrated to the new schema, and any required defaulting and recalculation are done.
1. **Project schedule engine update:** After successful data upgrade, the **Schedule** tab on the main page is relabeled **Tasks**. When a user selects this tab after the upgrade, they're directed to navigate to the tracking grid to view a read-only version of the WBS. To edit the WBS, they must initiate the schedule [conversion process](psa-upgrade-project-conversion.md). All projects without a pre-existing WBS can use the new scheduling experience directly, without conversion.
 
### Validate common scenarios

When you validate your specific customizations, we recommend that you also review the business processes that are supported across the applications. These business processes include, but aren't limited to, the creation of sales entities such as quotations and contracts, and the creation of projects that include WBSs and approval of actuals.

## Major changes between Project Service Automation and Project Operations

This section provides a summary of the major changes that you can expect between Project Service Automation and Project Operations.

### Project planning

The project planning capabilities in Project Operations no longer rely on a combination client-side logic and server-side logic. Instead, Project Operations uses Project for the Web as its scheduling engine. This change in scheduling capabilities enables several new features, such as Board and Gantt views, resource-driven planning, [task checklist items](https://support.microsoft.com/office/use-task-checklists-in-microsoft-project-for-the-web-c69bcf73-5c75-4ad3-9893-6d6f92360e9c), and project scheduling modes. The new scheduling capabilities are also supported by a rich set of new [application programming interfaces (APIs)](../project-management/schedule-api-preview.md). These APIs are intended to help ensure that no programmatic operation for creating, updating, or deleting an entity in the WBS corrupts the calculated fields in the schedule.

### Billing and pricing

As part of continuing investments in Project Operations, several new capabilities are available in Billing and pricing. Here are some examples:

- [Recording material usage on projects and project tasks](../material/material-usage-log.md)
- [Subcontract management](../pro/subcontracting/managing-subcontracts-overview.md)
- [Advances and retainer-based contracts](../pro/sales/set-up-advances-retainer-based-contracts-sales.md)
- [Contract not-to-exceed status and validations](../pro/proforma-invoicing/manage-nte-status-validations-sales.md)
- Task-based billing

### Resource management

Project Operations provides optional support for the Universal Resource Scheduling (URS) board and scheduling assistant. This new experience becomes mandatory in the April 2023 wave.

## Frequently asked questions

### Which deployment types are currently supported for upgrade?

| Source                                                 | Target                                                    | Status                  |
|--------------------------------------------------------|-----------------------------------------------------------|-------------------------|
| Project Service Automation                             | Project Operations Lite Deployment                        | Supported               |
| Dynamics 365 Finance Project Management and Accounting | Project Operations Lite Deployment                        | Not currently supported |
| Finance Project Management and Accounting              | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| Project Service Automation 3.x                         | Project Operations for resource/non-stocked scenarios     | Not currently supported |
| Project for the Web (dedicated environment)            | Project Operations Lite Deployment                        | Not currently supported |

### How can I install Project Operations before the upgrade tooling is available?

There are two options for installing Project Operations before the upgrade tooling is available:

- Provision a new environment.
- Deploy Project Operations separately on any sales organization where Project Service Automation isn't present.

If Project Service Automation is installed on an organization, but it wasn't used, it can be uninstalled. After you completely remove Project Service Automation, Project Operations can be installed on the same organization.
