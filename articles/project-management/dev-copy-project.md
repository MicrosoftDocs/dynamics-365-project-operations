---
title: Develop project templates with Copy Project
description: Learn how to create project templates in Dynamics 365 Project Operations using the Copy Project action. Simplify project management with reusable templates.
author: abriccetti
ms.date: 02/05/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Develop project templates with Copy Project

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

Dynamics 365 Project Operations supports the ability to copy a project and revert any assignments back to the generic resources that represent the role. Use this functionality to build basic project templates.

When you select **Copy Project**, the system updates the status of the target project. Use **Status Reason** to determine when the copy action is complete. Selecting **Copy Project** also updates the start date of the project to the current start date if the system doesn't detect a target date in the target project entity.

To add more columns to copy from the Project entity, add those columns to the **Copy Project Columns** view on the Project entity, and then run the **CopyProjectEntityAttributesRequest** API via a plugin or flow. This API copies the data in the columns in the **Copy Project Columns** view from the specified source project to the target project. You must call this API separately from the CopyProjectV3 or V4 API call.

To add more columns to copy from the Project Task entities, add those columns to the **Copy Project Task Columns** view on the **Project Task** table to ensure columns are copied to the new Project Tasks when you call CopyProjectV3 or V4.

## Copy Project v3 custom action

### Name

msdyn\_CopyProjectV3

### Input parameters

There are three input parameters:

- **ReplaceNamedResources** or **ClearTeamsAndAssignments** – Set only one of these options. Don't set both.

  - **\{"ReplaceNamedResources":true\}** – The default behavior for Project Operations. Replaces any named resources with generic resources. The only exception is assignments to the Project Manager on the source project are assigned to the Project Manager of the target project (a named resource is required, and not a generic resource).
  - **\{"ClearTeamsAndAssignments":true\}** – The default behavior for Project for the Web. Removes all assignments and team members.

- **SourceProject** – The entity reference of the source project to copy from. Don't set this parameter to null.
- **Target** – The entity reference of the target project to copy to. Don't set this parameter to null.

The following table provides a summary of the three parameters.

| Parameter                | Type             | Value                 |
|--------------------------|------------------|-----------------------|
| ReplaceNamedResources    | Boolean          | **True** or **False** |
| ClearTeamsAndAssignments | Boolean          | **True** or **False** |
| SourceProject            | Entity Reference | The source project    |
| Target                   | Entity Reference | The target project    |

For more defaults on actions, see [Use Web API actions](/powerapps/developer/common-data-service/webapi/use-web-api-actions).

### Validations

The system performs the following validations:

1. It checks for null values and retrieves the source and target projects to confirm both projects exist in the organization.
1. It validates that the target project is valid for copying by verifying the following conditions:

    - The project is new and doesn't have any previous activity, including selection of the **Tasks** tab.
    - The project doesn't have a previous copy, no import was requested on this project, and the project doesn't have a **Failed** status.

1. The operation isn't called by using HTTP.

## Copy Project v4 custom action

### Name

msdyn\_CopyProjectV4

### Input parameters

Use five input parameters:

- **SourceProject** – The entity reference of the source project to copy from. Don't set this parameter to null.
- **Target** – The entity reference of the target project to copy to. Don't set this parameter to null.
- **TeamMemberOption** – The option for copying team members to the target project. Don't set this parameter to null.

  - **0** – Don't copy team members.
  - **1** – Copy team members as generic resources (behaves the same as in V3).
  - **2** – Copy team members to specified named or generic resources.

- **TeamMembers** – The entity collection of named or generic team members to replace the existing team members. Set this parameter to null if you select **0** or **1** for the **TeamMemberOption** parameter. Don't set this parameter to null if you select **2**.
- **TeamMembersMapping** – The JavaScript Object Notation (JSON) string dictionary that maps team members from the source project to the target project. For each entry, the key is the **ProjectTeamID** value of the source project team member, and the value is the **ProjectTeamID** value of the target project team member. All assignments on the source project of the identified source project team member are assigned to the identified target project team member in the target project. Multiple source project team members can be mapped to one target project team member. Set this parameter to null if you select **0** or **1** for the **TeamMemberOption** parameter. It's optional if you select **2**.

The following table provides a summary of the five parameters.

| Parameter          | Type             | Value |
|--------------------|------------------|-------|
| SourceProject      | Entity Reference | The source project |
| Target             | Entity Reference | The target project |
| TeamMemberOption   | Option Set       | **0**, **1**, or **2** |
| TeamMembers        | Entity Collection| Named or generic team members for the target project |
| TeamMembersMapping | Json String      | The dictionary that maps team members from the source project to the target project |

For more defaults on actions, see [Use Web API actions](/powerapps/developer/common-data-service/webapi/use-web-api-actions).

### Validations

The system performs the following validations:

1. It checks for null values and retrieves the source and target projects to confirm both projects exist in the organization.
1. It validates that all team members in both the **TeamMembers** parameter and the **TeamMemberMapping** parameter are valid.
1. It validates that the target project is valid for copying by verifying the following conditions:

    - The project is new and doesn't have any previous activity, including selection of the **Tasks** tab.
    - The project doesn't have any previous copy, no import was requested on this project, and the project doesn't have a **Failed** status.

1. It checks that the operation isn't called by using HTTP.

## Specify fields to copy

When you call the action, **Copy Project** checks the **Copy Project Columns** project view to determine which fields to copy when the project is copied.

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

### Example

The following example shows how to call the **CopyProjectV4** custom action where the **TeamMemberOption** parameter is set to **2**, and both **TeamMembers** and **TeamMembersMapping** values are sent.

```C#
/* To simplify, the sample code below does not contain code to setup source project, create target project, etc.
 * The sample code demonstrates calling Copy Project V4 with option to pass in team members for creation and mapping.
 * 
 * IN THE BELOW CODE EXAMPLE:
 * sourceProjectRef is the EntityReference of the source project to copy.
 * targetProjectRef is the target project, target project must be created before calling the API.
 * Target project should be created empty without doing any further setup like adding team members, tasks, etc.
 * toBeCreatedTargetTeamMembers is an EntityCollection of team members to be created in the target project
 * as part of the copy and mapping.
 * teamMembersMapping is a Dictionary<Guid, Guid> of the team member mapping between source and target project.
 * Key is the ID of a source team member; Value is the ID of the target team member.
 * */

var request = new OrganizationRequest("msdyn_CopyProjectV4");
request["Target"] = targetProjectRef;
request["SourceProject"] = sourceProjectRef;
request["TeamMemberOption"] = new OptionSetValue(2); // 0: None, 1: CopyAsGeneric, 2: Specify
request["TeamMembers"] = toBeCreatedTargetTeamMembers;
request["TeamMembersMapping"] = SerializeJson(teamMembersMapping); // See implementation of SerializeJson() method below

OrganizationService.Execute(request);

/* Sample serialized json for team member mapping:
'[
{"Key":"a2cee002-cca1-41a4-8821-09d8327741e9","Value":"32c55ac0-06d6-4809-bcdb-566635576e1e"},
{"Key":"b2cee002-cca1-41a4-8821-09d8327741e0","Value":"42c55ac0-06d6-4809-bcdb-566635576e10"},
]'
*/
string SerializeJson<T>(T obj)
{
    var serializer = new System.Runtime.Serialization.Json.DataContractJsonSerializer(typeof(T));

    using (Stream stream = new MemoryStream())
    {
        serializer.WriteObject(stream, obj);
        stream.Position = 0;

        StreamReader streamReader = new StreamReader(stream);
        return streamReader.ReadToEnd();
    }
}

/* Optional code to wait for the copy to complete as the main work is done in Async service.
 * To see details on error, go to PSS Error Logs and/or Settings > System Jobs.
 * */
EnsureProjectCopySuccessful(targetProjectRef);

void EnsureProjectCopySuccessful(EntityReference project)
{
    var start = DateTime.Now;

    do
    {
        Thread.Sleep(TimeSpan.FromSeconds(10));
        var updatedProject = OrganizationService.Retrieve(Project.EntityLogicalName, project.Id, new ColumnSet(Project.AttributeStatuscode))
            .ToEntity<Project>();

        if (updatedProject.statuscode.Value == (int)project_statuscode.Projectcopyfailed)
        {
            throw new Exception("Project Copy failed.");
        }
        else if (updatedProject.statuscode.Value == (int)project_statuscode.Active)
        {
            break;
        }

        if (DateTime.Now > start + TimeSpan.FromMinutes(5))
        {
            throw new TimeoutException("Copy Project timed out");
        }
    }
    while (true);
}
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
