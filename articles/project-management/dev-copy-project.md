---
title: Develop project templates with Copy Project
description: This article provides information about how to create project templates using the Copy Project custom action.
author: stsporen
ms.date: 03/10/2022
ms.topic: article
ms.reviewer: johnmichalak
ms.author: stsporen
---

# Develop project templates with Copy Project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations supports the ability to copy a project and revert any assignments back to the generic resources that represent the role. Customers can use this functionality to build basic project templates.

When you select **Copy Project**, the status of the target project is updated. Use **Status Reason** to determine when the copy action is complete. Selecting **Copy Project** also updates the start date of the project to the current start date if no target date is detected in the target project entity.

## Copy Project custom action

### Name 

msdyn\_CopyProjectV3

### Input parameters

There are three input parameters:

- **ReplaceNamedResources** or **ClearTeamsAndAssignments** – Set only one of the options. Don't set both.

    - **\{"ReplaceNamedResources":true\}** – The default behavior for Project Operations. Any named resources are replaced with generic resources.
    - **\{"ClearTeamsAndAssignments":true\}** – The default behavior for Project for the Web. All assignments and team members are removed.

- **SourceProject** – The entity reference of the source project to copy from. This parameter can't be null.
- **Target** – The entity reference of the target project to copy to. This parameter can't be null.

The following table provides a summary of the three parameters.

| Parameter                | Type             | Value                 |
|--------------------------|------------------|-----------------------|
| ReplaceNamedResources    | Boolean          | **True** or **False** |
| ClearTeamsAndAssignments | Boolean          | **True** or **False** |
| SourceProject            | Entity Reference | The source project    |
| Target                   | Entity Reference | The target project    |

For more defaults on actions, see [Use Web API actions](/powerapps/developer/common-data-service/webapi/use-web-api-actions).

### Validations

The following validations are done.

1. Null checks and retrieves the source and target projects to confirm the existence of both projects in the organization.
2. The system validates that the target project is valid for copying by verifying the following conditions:

    - There is no previous activity on the project (including selection of the **Tasks** tab), and the project is newly created.
    - There is no previous copy, no import has been requested on this project, and the project doesn't have a **Failed** status.

3. The operation isn't called by using HTTP.

## Specify fields to copy

When the action is called, **Copy Project** will look at the project view **Copy Project Columns** to determine which fields to copy when the project is copied.

### Example

The following example shows how to call the **CopyProjectV3** custom action with the **removeNamedResources** parameter set.

```C#
{
    using System;
    using System.Runtime.Serialization;
    using Microsoft.Xrm.Sdk;
    using Newtonsoft.Json;

    public class CopyProjectSample
    {
        private IOrganizationService organizationService;

        public CopyProjectSample(IOrganizationService organizationService)
        {
            this.organizationService = organizationService;
        }

        public void SampleRun()
        {
            // Example source project GUID
            Guid sourceProjectId = new Guid("11111111-1111-1111-1111-111111111111");
            var sourceProject = new Entity("msdyn_project", sourceProjectId);

            Entity targetProject = new Entity("msdyn_project");
            targetProject["msdyn_subject"] = "Example Project - Copy";
            targetProject.Id = organizationService.Create(targetProject);

            CallCopyProjectAPI(sourceProject.ToEntityReference(), targetProject.ToEntityReference(), copyOption, true, false);
            Console.WriteLine("Done ...");
        }

        private void CallCopyProjectAPI(EntityReference sourceProject, EntityReference TargetProject, bool replaceNamedResources = true, bool clearTeamsAndAssignments = false)
        {
            OrganizationRequest req = new OrganizationRequest("msdyn_CopyProjectV3");
            req["SourceProject"] = sourceProject;
            req["Target"] = TargetProject;

            if (replaceNamedResources)
            {
                req["ReplaceNamedResources"] = true;
            }
            else
            {
                req["ClearTeamsAndAssignments"] = true;
            }

            OrganizationResponse response = organizationService.Execute(req);
        }
    }
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
