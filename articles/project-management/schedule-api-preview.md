---
title: Use Project schedule APIs to perform operations with Scheduling entities
description: This article provides information and samples for using Project schedule APIs.
author: abriccetti
ms.date: 08/19/2025
ms.topic: how-to
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Use Project schedule APIs to perform operations with Scheduling entities

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._


**Scheduling entities**

Project schedule APIs provide the ability to perform create, update, and delete operations with **Scheduling entities**. These entities are managed through the Scheduling engine in Project for the web. Create, update, and delete operations with **Scheduling entities** were restricted in earlier Dynamics 365 Project Operations releases.

The following table provides a full list of the Project schedule entities.

| Entity name             | Entity logical name         |
|-------------------------|-----------------------------|
| Project                 | msdyn_project               |
| Project Task            | msdyn_projecttask           |
| Project Task Dependency | msdyn_projecttaskdependency |
| Resource Assignment     | msdyn_resourceassignment    |
| Project Bucket          | msdyn_projectbucket         |
| Project Team Member     | msdyn_projectteam           |
| Project Checklists      | msdyn_projectchecklist      |
| Project Label           | msdyn_projectlabel          |
| Project Task to Label   | msdyn_projecttasktolabel    |
| Project Sprint          | msdyn_projectsprint         |

**OperationSet**

OperationSet is a unit-of-work pattern that can be used when several schedule impacting requests must be processed within a transaction.

**Project schedule APIs**

The following is a list of current Project schedule APIs.

| API                                     | Description |
|-----------------------------------------|-------------|
| **msdyn_CreateProjectV1**               | This API is used to create a project. The project and default project bucket are created immediately. Project creation can also be done by adding a row to the project table using standard Dataverse APIs. This process doesn't create a default bucket for the project but may have better performance.|
| **msdyn_CreateTeamMemberV1**            | This API is used to create a project team member. The team member record is created immediately. Team Member creation can also be done by adding a row to the Project Team Member table using standard Dataverse APIs. |
| **msdyn_CreateOperationSetV1**          | This API is used to schedule several requests that must be performed within a transaction. |
| **msdyn_PssCreateV1**                   | This API is used to create an entity. The entity can be any of the Project scheduling entities that support the create operation. |
| **msdyn_PssCreateV2**                   | This API is used to create an entity. It works like **msdyn_PssCreateV1**, but multiple entities can be created in one action. |
| **msdyn_PssUpdateV1**                   | This API is used to update an entity. The entity can be any of the Project scheduling entities that support the update operation. |
| **msdyn_PssUpdateV2**                   | This API is used to updated entities. It works like **msdyn_PssUpdateV1**, but multiple entities can be updated in one action. |
| **msdyn_PssDeleteV1**                   | This API is used to delete an entity. The entity can be any of the Project scheduling entities that support the delete operation. |
| **msdyn_PssDeleteV2**                   | This API is used to delete entities. It works like **msdyn_PssDeleteV1**, but multiple entities can be deleted in one action. |
| **msdyn_ExecuteOperationSetV1**         | This API is used to execute all the operations within the given operation set. |
| **msdyn_PssUpdateResourceAssignmentV1** | This API is used to update a Resource Assignment planned work contour. |

**Using Project schedule APIs with OperationSet**

Because records are created immediately for both **CreateProjectV1** and **CreateTeamMemberV1**, these APIs can't be used directly in the **OperationSet**. However, you can use them to create the required records, create an **OperationSet**, and then use the precreated records in the **OperationSet**.

**Supported operations**

| Scheduling entity       | Create     | Update     | Delete     | Important considerations |
|-------------------------|------------|------------|------------|--------------------------|
| Project task            | Yes        | Yes        | Yes        | The **EffortCompleted**, and **EffortRemaining** fields can be edited in Project for the Web, but they can't be edited in Project Operations. |
| Project task dependency | Yes        | No         | Yes        | Project task dependency records aren't updated. Instead, an old record can be deleted, and a new record can be created. |
| Resource assignment     | Yes        | Yes\*      | Yes        | Operations with the following fields aren't supported: **BookableResourceID**, **Effort**, **EffortCompleted**, **EffortRemaining**, and **PlannedWork**.  |
| Project bucket          | Yes        | Yes        | Yes        | The default bucket is created by using the **CreateProjectV1** API. Support for creating and deleting project buckets was added in Update Release 16. |
| Project team member     | Yes        | Yes        | Yes        | For the create operation, use the **CreateTeamMemberV1** API. |
| Project                 | Yes        | Yes        | No         | Operations with the following fields aren't supported: **StateCode**, **BulkGenerationStatus**, **GlobalRevisionToken**, **CalendarID**, **Effort**, **EffortCompleted**, **EffortRemaining**, **Progress**, **Finish**, **TaskEarliestStart**, and **Duration**. |
| Project Checklists      | Yes        | Yes        | Yes        | |
| Project Label           | No         | Yes        | No         | Label names can be changed. This feature is only available for Project for the Web. Labels are created the first you open a project. |
| Project Task to Label   | Yes        | No         | Yes        | This feature is only available for Project for the Web. |
| Project Sprint          | Yes        | Yes        | Yes        | The **Start** field must have a date earlier than the **Finish** field. Sprints for the same project can't overlap each other. This feature is only available for Project for the Web. |
| Project Goal            | Yes        | Yes        | Yes        | Operations with the following fields aren't supported: DescriptionPlainText, TaskDisplayOrder |
| Project Task to Goal    | Yes        | No         | Yes        | Operations with the following fields aren't supported: TaskDisplayOrder |

\* Resource assignment records aren't updated. Instead, the old record can be deleted, and a new record can be created. A separate API is provided to update Resource Assignment contours.

The ID property is optional. If the ID property is provided, the system tries to use it and throws an exception if it can't be used. If it isn't provided, the system generates it.

**Limitations and known issues**

The following list shows limitations and known issues:

- Project Schedule APIs can only be used by **Users with Microsoft Project License**. They can't be used by:

    - Application users
    - System users
    - Integration users
    - Other users that don't have the required license

- Each **OperationSet** can only have a maximum of 200 operations.
- Each user can only have a maximum of 10 open **OperationSets**.
- Each Update Resource Assignment Contour operation counts as a single operation.
- Each list of updated contours can contain a maximum of 100 time slices.
- **OperationSet** failure status and failure logs aren't currently available.
- There's a maximum of 400 sprints per project.
- [Limits and boundaries on projects and tasks](/project-for-the-web/project-for-the-web-limits-and-boundaries).

**Error handling**

- To review errors generated from the Operation Sets, go to **Settings** \> **Schedule Integration** \> **Operations Sets**.
- To review errors generated from the Project schedule Service, go to **Settings** \> **Schedule Integration** \> **PSS Error Logs**.

**Editing Resource Assignment Contours**

Unlike all other project scheduling APIs that update an entity, the resource assignment contour API is solely responsible for updates to a single field, msdyn_plannedwork, on a single entity, msydn_resourceassignment.

Given schedule mode is:

- **fixed units**.
- The project calendar is from 9:00 to 5:00 PM (Pacific Time) Monday, Tuesday, Thursday, and Friday. (*There's no work on Wednesdays.*)
- The resource calendar is from 9:00 AM to 1:00 PM (Pacific Time) Monday through Friday.

This assignment is for one week, four hours a day because the resource calendar is from 9:00 AM to 1:00 PM (Pacific Time), or four hours a day.

| &nbsp;     | Task | Start Date | End Date  | Quantity | 6/13/2022 | 6/14/2022 | 6/15/2022 | 6/16/2022 | 6/17/2022 |
|------------|------|------------|-----------|----------|-----------|-----------|-----------|-----------|-----------|
| 9-1 worker |  T1  | 6/13/2022  | 6/17/2022 | 20       | 4         | 4         | 4         | 4         | 4         |

For example, if you want the worker to only work three hours each day this week and allow for one hour for other tasks.

#### UpdatedContours sample payload

```json
[{

"minutes":900.0,

"start":"2022-06-13T00:00:00-07:00",

"end":"2022-06-18T00:00:00-07:00"

}]
```

This is the assignment after the Update Contour Schedule API is run.

| &nbsp;     | Task | Start Date | End Date  | Quantity | 6/13/2022 | 6/14/2022 | 6/15/2022 | 6/16/2022 | 6/17/2022 |
|------------|------|------------|-----------|----------|-----------|-----------|-----------|-----------|-----------|
| 9-1 worker | T1   | 6/13/2022  | 6/17/2022 | 15       | 3         | 3         | 3         | 3         | 3         |


**Sample scenario**

In this scenario, you create a project, a team member, four tasks, and two resource assignments. Next, you update one task, update the project, update a resource assignment contour, delete one task, delete one resource assignment, and create a task dependency.

```csharp
Entity project = CreateProject();
project.Id = CallCreateProjectAction(project);
var projectReference = project.ToEntityReference();

var teamMember = new Entity("msdyn_projectteam", Guid.NewGuid());
teamMember["msdyn_name"] = $"TM {DateTime.Now.ToShortTimeString()}";
teamMember["msdyn_project"] = projectReference;
var createTeamMemberResponse = CallCreateTeamMemberAction(teamMember);

var description = $"My demo {DateTime.Now.ToShortTimeString()}";
var operationSetId = CallCreateOperationSetAction(project.Id, description);

var task1 = GetTask("1WW", projectReference);
var task2 = GetTask("2XX", projectReference, task1.ToEntityReference());
var task3 = GetTask("3YY", projectReference);
var task4 = GetTask("4ZZ", projectReference);

var assignment1 = GetResourceAssignment("R1", teamMember, task2, project);
var assignment2 = GetResourceAssignment("R2", teamMember, task3, project);

var task1Response = CallPssCreateAction(task1, operationSetId);
var task2Response = CallPssCreateAction(task2, operationSetId);
var task3Response = CallPssCreateAction(task3, operationSetId);
var task4Response = CallPssCreateAction(task4, operationSetId);

var assignment1Response = CallPssCreateAction(assignment1, operationSetId);
var assignment2Response = CallPssCreateAction(assignment2, operationSetId);

task2["msdyn_subject"] = "Updated Task";
var task2UpdateResponse = CallPssUpdateAction(task2, operationSetId);

project["msdyn_subject"] = $"Proj update {DateTime.Now.ToShortTimeString()}";
var projectUpdateResponse = CallPssUpdateAction(project, operationSetId);

List<UpdatedContour> updatedContours = new List<UpdatedContour>(); 
UpdatedContour updatedContour = new UpdatedContour(); 
updatedContour.Start = DateTime.UtcNow.Date; 
updatedContour.End = DateTime.UtcNow.Date.AddDays(1); 
updatedContour.Minutes = 120; 
updatedContours.Add(updatedContour); 

String serializedUpdate = JsonConvert.SerializeObject(updatedContours); 
var updateContoursResponse = CallPssUpdateContourAction(assignment1.Id, serializedUpdate, operationSetId); 

var task4DeleteResponse = CallPssDeleteAction(task4.Id.ToString(), task4.LogicalName, operationSetId);

var assignment2DeleteResponse = CallPssDeleteAction(assignment2.Id.ToString(), assignment2.LogicalName, operationSetId);

var dependency1 = GetTaskDependency(project, task2, task3);
var dependency1Response = CallPssCreateAction(dependency1, operationSetId);

CallExecuteOperationSetAction(operationSetId);
Console.WriteLine("Done....");
```

**Additional samples**

```csharp
#region Call actions --- Sample code ----

/// <summary>
/// Calls the action to create an operationSet
/// </summary>
/// <param name="projectId">project id for the operations to be included in this operationSet</param>
/// <param name="description">description of this operationSet</param>
/// <returns>operationSet id</returns>
private string CallCreateOperationSetAction(Guid projectId, string description)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_CreateOperationSetV1");
    operationSetRequest["ProjectId"] = projectId.ToString();
    operationSetRequest["Description"] = description;
    OrganizationResponse response = organizationService.Execute(operationSetRequest);
    return response["OperationSetId"].ToString();
}

/// <summary>
/// Calls the action to create an entity
/// </summary>
/// <param name="entity">Scheduling entity</param>
/// <param name="operationSetId">operationSet id</param>
/// <returns>OperationSetResponse</returns>

private OperationSetResponse CallPssCreateAction(Entity entity, string operationSetId)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_PssCreateV1");
    operationSetRequest["Entity"] = entity;
    operationSetRequest["OperationSetId"] = operationSetId;
    return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
}

/// <summary>
/// Calls the action to update an entity
/// </summary>
/// <param name="entity">Scheduling entity</param>
/// <param name="operationSetId">operationSet Id</param>
/// <returns>OperationSetResponse</returns>
private OperationSetResponse CallPssUpdateAction(Entity entity, string operationSetId)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_PssUpdateV1");
    operationSetRequest["Entity"] = entity;
    operationSetRequest["OperationSetId"] = operationSetId;
    return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
}

/// <summary>
/// Calls the action to update an entity
/// </summary>
/// <param name="recordId">Id of the record to be deleted</param>
/// <param name="entityLogicalName">Entity logical name of the record</param>
/// <param name="operationSetId">OperationSet Id</param>
/// <returns>OperationSetResponse</returns>
private OperationSetResponse CallPssDeleteAction(string recordId, string entityLogicalName, string operationSetId)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_PssDeleteV1");
    operationSetRequest["RecordId"] = recordId;
    operationSetRequest["EntityLogicalName"] = entityLogicalName;
    operationSetRequest["OperationSetId"] = operationSetId;
    return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
}

/// <summary> 
/// Calls the action to update a Resource Assignment contour
/// </summary> 
/// <param name="resourceAssignmentId">Id of the resource assignment to be updated</param> 
/// <param name="serializedUpdates">JSON formatted contour updates</param>
/// <param name="operationSetId">operationSet id</param> 
/// <returns>OperationSetResponse</returns> 
private OperationSetResponse CallPssUpdateContourAction(string resourceAssignmentId, string serializedUpdates string operationSetId) 
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_PssUpdateResourceAssignmentContourV1"); 
    operationSetRequest["ResourceAssignmentId"] = resourceAssignmentId; 
    operationSetRequest["UpdatedContours"] = serializedUpdates; 
    operationSetRequest["OperationSetId"] = operationSetId; 
    return GetOperationSetResponseFromOrgResponse(OrganizationService.Execute(operationSetRequest)); 
} 

/// <summary>
/// Calls the action to execute requests in an operationSet
/// </summary>
/// <param name="operationSetId">operationSet id</param>
/// <returns>OperationSetResponse</returns>
private OperationSetResponse CallExecuteOperationSetAction(string operationSetId)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_ExecuteOperationSetV1");
    operationSetRequest["OperationSetId"] = operationSetId;
    return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
}

/// <summary>
/// This can be used to abandon an operationSet that is no longer needed
/// </summary>
/// <param name="operationSetId">operationSet id</param>
/// <returns>OperationSetResponse</returns>
protected OperationSetResponse CallAbandonOperationSetAction(Guid operationSetId)
{
    OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn_AbandonOperationSetV1");
    operationSetRequest["OperationSetId"] = operationSetId.ToString();
    return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
}


/// <summary>
/// Calls the action to create a new project
/// </summary>
/// <param name="project">Project</param>
/// <returns>project Id</returns>
private Guid CallCreateProjectAction(Entity project)
{
    OrganizationRequest createProjectRequest = new OrganizationRequest("msdyn_CreateProjectV1");
    createProjectRequest["Project"] = project;
    OrganizationResponse response = organizationService.Execute(createProjectRequest);
    var projectId = Guid.Parse((string)response["ProjectId"]);
    return projectId;
}

/// <summary>
/// Calls the action to create a new project team member
/// </summary>
/// <param name="teamMember">Project team member</param>
/// <returns>project team member Id</returns>
private string CallCreateTeamMemberAction(Entity teamMember)
{
    OrganizationRequest request = new OrganizationRequest("msdyn_CreateTeamMemberV1");
    request["TeamMember"] = teamMember;
    OrganizationResponse response = organizationService.Execute(request);
    return (string)response["TeamMemberId"];
}

private OperationSetResponse GetOperationSetResponseFromOrgResponse(OrganizationResponse orgResponse)
{
    return JsonConvert.DeserializeObject<OperationSetResponse>((string)orgResponse.Results["OperationSetResponse"]);
}

private EntityCollection GetDefaultBucket(EntityReference projectReference)
{
    var columnsToFetch = new ColumnSet("msdyn_project", "msdyn_name");
    var getDefaultBucket = new QueryExpression("msdyn_projectbucket")
    {
        ColumnSet = columnsToFetch,
        Criteria =
        {
            Conditions =
            {
                new ConditionExpression("msdyn_project", ConditionOperator.Equal, projectReference.Id),
                new ConditionExpression("msdyn_name", ConditionOperator.Equal, "Bucket 1")
            }
        }
    };

    return organizationService.RetrieveMultiple(getDefaultBucket);
}

private Entity GetBucket(EntityReference projectReference)
{
    var bucketCollection = GetDefaultBucket(projectReference);
    if (bucketCollection.Entities.Count > 0)
    {
        return bucketCollection[0].ToEntity<Entity>();
    }

    throw new Exception($"Please open project with id {projectReference.Id} in the Dynamics UI and navigate to the Tasks tab");
}

private Entity CreateProject()
{
    var project = new Entity("msdyn_project", Guid.NewGuid());
    project["msdyn_subject"] = $"Proj {DateTime.Now.ToShortTimeString()}";

    return project;
}



private Entity GetTask(string name, EntityReference projectReference, EntityReference parentReference = null)
{
    var task = new Entity("msdyn_projecttask", Guid.NewGuid());
    task["msdyn_project"] = projectReference;
    task["msdyn_subject"] = name;
    task["msdyn_effort"] = 4d;
    task["msdyn_scheduledstart"] = DateTime.Today;
    task["msdyn_scheduledend"] = DateTime.Today.AddDays(5);
    task["msdyn_start"] = DateTime.Now.AddDays(1);
    task["msdyn_projectbucket"] = GetBucket(projectReference).ToEntityReference();
    task["msdyn_LinkStatus"] = new OptionSetValue(192350000);

    //Custom field handling
    /*
    task["new_custom1"] = "Just my test";
    task["new_age"] = 98;
    task["new_amount"] = 591.34m;
    task["new_isready"] = new OptionSetValue(100000000);
    */

    if (parentReference == null)
    {
        task["msdyn_outlinelevel"] = 1;
    }
    else
    {
        task["msdyn_parenttask"] = parentReference;
    }

    return task;
}

private Entity GetResourceAssignment(string name, Entity teamMember, Entity task, Entity project)
{
    var assignment = new Entity("msdyn_resourceassignment", Guid.NewGuid());
    assignment["msdyn_projectteamid"] = teamMember.ToEntityReference();
    assignment["msdyn_taskid"] = task.ToEntityReference();
    assignment["msdyn_projectid"] = project.ToEntityReference();
    assignment["msdyn_name"] = name;
   
    return assignment;
}

protected Entity GetTaskDependency(Entity project, Entity predecessor, Entity successor)
{
    var taskDependency = new Entity("msdyn_projecttaskdependency", Guid.NewGuid());
    taskDependency["msdyn_project"] = project.ToEntityReference();
    taskDependency["msdyn_predecessortask"] = predecessor.ToEntityReference();
    taskDependency["msdyn_successortask"] = successor.ToEntityReference();
    taskDependency["msdyn_linktype"] = new OptionSetValue(192350000);

    return taskDependency;
}

#endregion


#region OperationSetResponse DataContract --- Sample code ----

[DataContract]
public class OperationSetResponse
{
[DataMember(Name = "operationSetId")]
public Guid OperationSetId { get; set; }

[DataMember(Name = "operationSetDetailId")]
public Guid OperationSetDetailId { get; set; }

[DataMember(Name = "operationType")]
public string OperationType { get; set; }

[DataMember(Name = "recordId")]
public string RecordId { get; set; }

[DataMember(Name = "correlationId")]
public string CorrelationId { get; set; }
}

#endregion

#region UpdatedContour DataContract --- Sample code ---- 

[DataContract] 
public class UpdatedContour 
{ 
[DataMember(Name = "start")] 
public DateTime Start { get; set; } 

[DataMember(Name = "end")] 
public DateTime End { get; set; } 

[DataMember(Name = "minutes")] 
public decimal Minutes { get; set; } 
} 

#endregion 
```
