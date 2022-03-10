---
title: Develop project templates with Copy Project
description: This topic provides information about how to create project templates using the Copy Project custom action.
author: stsporen
ms.date: 01/21/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: stsporen
---

# Develop project templates with Copy Project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_



Dynamics 365 Project Operations supports the ability to copy a project and revert any assignments back to the generic resources that represent the role. Customers can use this functionality to build basic project templates.

When you select **Copy Project**, the status of the target project is updated. Use **Status Reason** to determine when the copy action is complete. Selecting **Copy Project** also updates the start date of the project to the current start date if no target date is detected in the target project entity.

## Copy Project custom action 

### Name 

**msdyn_CopyProjectV3**

### Input parameters
There are three input parameters:

1.  **ReplaceNamedResources / ClearTeamsAndAssignments** - Only set either of
    the 2 options and not both.

    -   **{"ClearTeamsAndAssignments":true}:** The default behavior for Project
        for the Web and will remove all assignments and team members.

    -   **{"ReplaceNamedResources":true}**: The default behavior for Project
        Operations, and will replace any named resources with generic resources.

2.  **SourceProject** – Entity Reference of the source project to copy from,
    this cannot be null.

3.  **Target** – Entity Reference of the target project to copy to, this cannot
    be null.

INPUT PARAMETERS

| Parameter                | Type             | Values         |
|--------------------------|------------------|----------------|
| ReplaceNamedResources    | Boolean          | True/False     |
| ClearTeamsAndAssignments | Boolean          | True/False     |
| SourceProject            | Entity Reference | Source Project |
| Target                   | Entity Reference | Target Project |


For more defaults on actions, see [Use Web API actions](/powerapps/developer/common-data-service/webapi/use-web-api-actions)

## Specify fields to copy 
When the action is called, **Copy Project** will look at the project view **Copy Project Columns** to determine which fields to copy when the project is copied.


### Example
The following example shows how to call the **CopyProject** custom action with the **removeNamedResources** parameter set.
```C#
{
    using System;
    using System.Runtime.Serialization;
    using Microsoft.Xrm.Sdk;
    using Newtonsoft.Json;

    [DataContract]
    public class ProjectCopyOption
    {
        /// <summary>
        /// Clear teams and assignments.
        /// </summary>
        [DataMember(Name = "clearTeamsAndAssignments")]
        public bool ClearTeamsAndAssignments { get; set; }

        /// <summary>
        /// Replace named resource with generic resource.
        /// </summary>
        [DataMember(Name = "removeNamedResources")]
        public bool ReplaceNamedResources { get; set; }
    }

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
            targetProject["msdyn_subject"] = "Example Project";
            targetProject.Id = organizationService.Create(targetProject);

            ProjectCopyOption copyOption = new ProjectCopyOption();
            copyOption.ReplaceNamedResources = true;

            CallCopyProjectAPI(sourceProject.ToEntityReference(), targetProject.ToEntityReference(), copyOption);
            Console.WriteLine("Done ...");
        }

        private void CallCopyProjectAPI(EntityReference sourceProject, EntityReference TargetProject, ProjectCopyOption projectCopyOption)
        {
            OrganizationRequest req = new OrganizationRequest("msdyn_CopyProjectV2");
            req["SourceProject"] = sourceProject;
            req["Target"] = TargetProject;
            req["ProjectCopyOption"] = JsonConvert.SerializeObject(projectCopyOption);
            OrganizationResponse response = organizationService.Execute(req);
        }
    }
}
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
