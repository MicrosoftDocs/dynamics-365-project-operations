---
title: Use Project schedule APIs to perform operations with Scheduling entities
description: This topic provides information and samples for using Project schedule APIs.
author: sigitac
ms.date: 06/22/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: sigitac
---

# Use Project schedule APIs to perform operations with Scheduling entities

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

> [!IMPORTANT] 
> Some or all of the functionality noted in this topic is available as part of a preview release. The content and the functionality are subject to change. 

## Scheduling entities

Project schedule APIs provide the ability to perform create, update, and delete operations with **Scheduling entities**. These entities are managed through the Scheduling engine in Project for the web. Create, update, and delete operations with **Scheduling entities** were restricted in earlier Dynamics 365 Project Operations releases.

The following table provides a full list of the Project schedule entities.

| Entity name  | Entity logical name |
| --- | --- |
| Project | msdyn_project |
| Project Task  | msdyn_projecttask  |
| Project Task Dependency  | msdyn_projecttaskdependency  |
| Resource Assignment | msdyn_resourceassignment |
| Project Bucket  | msdyn_projectbucket |
| Project Team Member | msdyn_projectteam |

## OperationSet

OperationSet is a unit-of-work pattern that can be used when several schedule impacting requests must be processed within a transaction.

## Project schedule APIs

The following is a list of current Project schedule APIs.

- **msdyn_CreateProjectV1**: This API can be used to create a project. The project and default project bucket is created immediately.
- **msdyn_CreateTeamMemberV1**: This API can be used to create a project team member. The team member record is created immediately.
- **msdyn_CreateOperationSetV1**: This API can be used to schedule several requests that must be performed within a transaction.
- **msdyn_PSSCreateV1**: This API can be used to create an entity. The entity can be any of the Project scheduling entities that support the create operation.
- **msdyn_PSSUpdateV1**: This API can be used to update an entity. The entity can be any of the Project scheduling entities that support the update operation.
- **msdyn_PSSDeleteV1**: This API can be used to delete an entity. The entity can be any of the Project scheduling entities that support the delete operation.
- **msdyn_ExecuteOperationSetV1**: This API is used to execute all of the operations within the given operation set.

## Using Project schedule APIs with OperationSet

Because records with both **CreateProjectV1** and **CreateTeamMemberV1** are created immediately, these APIs can't be used in the **OperationSet** directly. However, you can use the API to create needed records, create an **OperationSet**, and then use these pre-created records in the **OperationSet**.

## Supported operations

| Scheduling entity | Create | Update | Delete | Important considerations |
| --- | --- | --- | --- | --- |
Project task | Yes | Yes | Yes | None |
| Project task dependency | Yes | Yes | | Project task dependency records aren't updated. Instead, an old record can be deleted and a new record can be created. |
| Resource assignment | Yes | Yes | | Operations with the following fields aren't supported: **BookableResourceID**, **Effort**, **EffortCompleted**, **EffortRemaining**, and **PlannedWork**. Resource assignment records aren't updated. Instead, the old record can be deleted and a new record can be created. |
| Project bucket | N/A | N/A | N/A | The default bucket is created using the **CreateProjectV1** API. |
| Project team member | Yes | Yes | Yes | For the create operation, use the **CreateTeamMemberV1** API. |
| Project | Yes | Yes | N/A | Operations with the following fields aren't supported: **StateCode**, **BulkGenerationStatus**, **GlobalRevisionToken**, **CalendarID**, **Effort**, **EffortCompleted**, **EffortRemaining**, **Progress**, **Finish**, **TaskEarliestStart**, and **Duration**. |

These APIs can be called with entity objects that include custom fields.

The ID property is optional. If it's provided, the system attempts to use it and throws an exception if it can't be used. If it isn't provided, the system will generate it.

## Restricted fields

The following tables define the fields that are restricted from **Create** and **Edit.**

### Project task

| **Logical name**                       | **Can create** | **Can edit**     |
|----------------------------------------|----------------|------------------|
| msdyn_actualcost                       | no             | no               |
| msdyn_actualcost_base                  | no             | no               |
| msdyn_actualend                        | no             | no               |
| msdyn_actualsales                      | no             | no               |
| msdyn_actualsales_base                 | no             | no               |
| msdyn_actualstart                      | no             | no               |
| msdyn_costatcompleteestimate           | no             | no               |
| msdyn_costatcompleteestimate_base      | no             | no               |
| msdyn_costconsumptionpercentage        | no             | no               |
| msdyn_effortcompleted                  | no             | no               |
| msdyn_effortestimateatcomplete         | no             | no               |
| msdyn_iscritical                       | no             | no               |
| msdyn_iscriticalname                   | no             | no               |
| msdyn_ismanual                         | no             | no               |
| msdyn_ismanualname                     | no             | no               |
| msdyn_ismilestone                      | no             | no               |
| msdyn_ismilestonename                  | no             | no               |
| msdyn_LinkStatus                       | no             | no               |
| msdyn_linkstatusname                   | no             | no               |
| msdyn_msprojectclientid                | no             | no               |
| msdyn_plannedcost                      | no             | no               |
| msdyn_plannedcost_base                 | no             | no               |
| msdyn_plannedsales                     | no             | no               |
| msdyn_plannedsales_base                | no             | no               |
| msdyn_pluginprocessingdata             | no             | no               |
| msdyn_progress                         | no             | no (yes for P4W) |
| msdyn_remainingcost                    | no             | no               |
| msdyn_remainingcost_base               | no             | no               |
| msdyn_remainingsales                   | no             | no               |
| msdyn_remainingsales_base              | no             | no               |
| msdyn_requestedhours                   | no             | no               |
| msdyn_resourcecategory                 | no             | no               |
| msdyn_resourcecategoryname             | no             | no               |
| msdyn_resourceorganizationalunitid     | no             | no               |
| msdyn_resourceorganizationalunitidname | no             | no               |
| msdyn_salesconsumptionpercentage       | no             | no               |
| msdyn_salesestimateatcomplete          | no             | no               |
| msdyn_salesestimateatcomplete_base     | no             | no               |
| msdyn_salesvariance                    | no             | no               |
| msdyn_salesvariance_base               | no             | no               |
| msdyn_scheduleddurationminutes         | no             | no               |
| msdyn_scheduledend                     | no             | no               |
| msdyn_scheduledstart                   | no             | no               |
| msdyn_schedulevariance                 | no             | no               |
| msdyn_skipupdateestimateline           | no             | no               |
| msdyn_skipupdateestimatelinename       | no             | no               |
| msdyn_summary                          | no             | no               |
| msdyn_varianceofcost                   | no             | no               |
| msdyn_varianceofcost_base              | no             | no               |

### Project task dependency

| **Logical name**              | **Can create** | **Can edit** |
|-------------------------------|----------------|--------------|
| msdyn_linktype                | no             | no           |
| msdyn_linktypename            | no             | no           |
| msdyn_predecessortask         | yes            | no           |
| msdyn_predecessortaskname     | yes            | no           |
| msdyn_project                 | yes            | no           |
| msdyn_projectname             | yes            | no           |
| msdyn_projecttaskdependencyid | yes            | no           |
| msdyn_successortask           | yes            | no           |
| msdyn_successortaskname       | yes            | no           |

### Resource assignment

| **Logical name**             | **Can create** | **Can edit** |
|------------------------------|----------------|--------------|
| msdyn_bookableresourceid     | yes            | no           |
| msdyn_bookableresourceidname | yes            | no           |
| msdyn_bookingstatusid        | no             | no           |
| msdyn_bookingstatusidname    | no             | no           |
| msdyn_committype             | no             | no           |
| msdyn_committypename         | no             | no           |
| msdyn_effort                 | no             | no           |
| msdyn_effortcompleted        | no             | no           |
| msdyn_effortremaining        | no             | no           |
| msdyn_finish                 | no             | no           |
| msdyn_plannedcost            | no             | no           |
| msdyn_plannedcost_base       | no             | no           |
| msdyn_plannedcostcontour     | no             | no           |
| msdyn_plannedsales           | no             | no           |
| msdyn_plannedsales_base      | no             | no           |
| msdyn_plannedsalescontour    | no             | no           |
| msdyn_plannedwork            | no             | no           |
| msdyn_projectid              | yes            | no           |
| msdyn_projectidname          | no             | no           |
| msdyn_projectteamid          | no             | no           |
| msdyn_projectteamidname      | no             | no           |
| msdyn_start                  | no             | no           |
| msdyn_taskid                 | no             | no           |
| msdyn_taskidname             | no             | no           |
| msdyn_userresourceid         | no             | no           |

### Project team member

| **Logical name**                                 | **Can create** | **Can edit** |
|--------------------------------------------------|----------------|--------------|
| msdyn_calendarid                                 | no             | no           |
| msdyn_creategenericteammemberwithrequirementname | no             | no           |
| msdyn_deletestatus                               | no             | no           |
| msdyn_deletestatusname                           | no             | no           |
| msdyn_effort                                     | no             | no           |
| msdyn_effortcompleted                            | no             | no           |
| msdyn_effortremaining                            | no             | no           |
| msdyn_finish                                     | no             | no           |
| msdyn_hardbookedhours                            | no             | no           |
| msdyn_hours                                      | no             | no           |
| msdyn_markedfordeletiontimer                     | no             | no           |
| msdyn_markedfordeletiontimestamp                 | no             | no           |
| msdyn_msprojectclientid                          | no             | no           |
| msdyn_percentage                                 | no             | no           |
| msdyn_requiredhours                              | no             | no           |
| msdyn_softbookedhours                            | no             | no           |
| msdyn_start                                      | no             | no           |

### Project

| **Logical name**                       | **Can create** | **Can edit** |
|----------------------------------------|----------------|--------------|
| msdyn_actualexpensecost                | no             | no           |
| msdyn_actualexpensecost_base           | no             | no           |
| msdyn_actuallaborcost                  | no             | no           |
| msdyn_actuallaborcost_base             | no             | no           |
| msdyn_actualsales                      | no             | no           |
| msdyn_actualsales_base                 | no             | no           |
| msdyn_contractlineproject              | yes            | no           |
| msdyn_contractorganizationalunitid     | yes            | no           |
| msdyn_contractorganizationalunitidname | yes            | no           |
| msdyn_costconsumption                  | no             | no           |
| msdyn_costestimateatcomplete           | no             | no           |
| msdyn_costestimateatcomplete_base      | no             | no           |
| msdyn_costvariance                     | no             | no           |
| msdyn_costvariance_base                | no             | no           |
| msdyn_duration                         | no             | no           |
| msdyn_effort                           | no             | no           |
| msdyn_effortcompleted                  | no             | no           |
| msdyn_effortestimateatcompleteeac      | no             | no           |
| msdyn_effortremaining                  | no             | no           |
| msdyn_finish                           | yes            | yes          |
| msdyn_globalrevisiontoken              | no             | no           |
| msdyn_islinkedtomsprojectclient        | no             | no           |
| msdyn_islinkedtomsprojectclientname    | no             | no           |
| msdyn_linkeddocumenturl                | no             | no           |
| msdyn_msprojectdocument                | no             | no           |
| msdyn_msprojectdocumentname            | no             | no           |
| msdyn_plannedexpensecost               | no             | no           |
| msdyn_plannedexpensecost_base          | no             | no           |
| msdyn_plannedlaborcost                 | no             | no           |
| msdyn_plannedlaborcost_base            | no             | no           |
| msdyn_plannedsales                     | no             | no           |
| msdyn_plannedsales_base                | no             | no           |
| msdyn_progress                         | no             | no           |
| msdyn_remainingcost                    | no             | no           |
| msdyn_remainingcost_base               | no             | no           |
| msdyn_remainingsales                   | no             | no           |
| msdyn_remainingsales_base              | no             | no           |
| msdyn_replaylogheader                  | no             | no           |
| msdyn_salesconsumption                 | no             | no           |
| msdyn_salesestimateatcompleteeac       | no             | no           |
| msdyn_salesestimateatcompleteeac_base  | no             | no           |
| msdyn_salesvariance                    | no             | no           |
| msdyn_salesvariance_base               | no             | no           |
| msdyn_scheduleperformance              | no             | no           |
| msdyn_scheduleperformancename          | no             | no           |
| msdyn_schedulevariance                 | no             | no           |
| msdyn_taskearlieststart                | no             | no           |
| msdyn_teamsize                         | no             | no           |
| msdyn_teamsize_date                    | no             | no           |
| msdyn_teamsize_state                   | no             | no           |
| msdyn_totalactualcost                  | no             | no           |
| msdyn_totalactualcost_base             | no             | no           |
| msdyn_totalplannedcost                 | no             | no           |
| msdyn_totalplannedcost_base            | no             | no           |


## Limitations and known issues
The following is a list of limitations and known issues:

- Project Schedule APIs can only be used by **Users with Microsoft Project License.** They can't be used by:
    - Application users
    - System users
    - Integration users
    - Other users that don't have the required license
- Each **OperationSet** can only have a maximum of 100 operations.
- Each user can only have a maximum of 10 open **OperationSets**.
- Project Operations currently supports a maximum of 500 total tasks on a project.
- **OperationSet** failure status and failure logs aren't currently available.
- [Limits and boundaries on projects and tasks](/project-for-the-web/project-for-the-web-limits-and-boundaries)

## Error handling

   - To review errors generated from the Operation Sets, go to **Settings** \> **Schedule Integration** \> **Operations Sets**.
   - To review errors generated from the Project schedule Service, go to **Settings** \> **Schedule Integration** \> **PSS Error Logs**.

## Sample scenario

In this scenario, you will create a project, a team member, four tasks, and two resource assignments. Next, you will update one task, update the project, delete one task, delete one resource assignment, and create a task dependency.

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

var task4DeleteResponse = CallPssDeleteAction(task4.Id.ToString(), task4.LogicalName, operationSetId);

var assignment2DeleteResponse = CallPssDeleteAction(assignment2.Id.ToString(), assignment2.LogicalName, operationSetId);

var dependency1 = GetTaskDependency(project, task2, task3);
var dependency1Response = CallPssCreateAction(dependency1, operationSetId);

CallExecuteOperationSetAction(operationSetId);
Console.WriteLine("Done....");
```

## Additional samples

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
/// Calls the action to create an entity, only Task and Resource Assignment for now
/// </summary>
/// <param name="entity">Task or Resource Assignment</param>
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
/// Calls the action to update an entity, only Task for now
/// </summary>
/// <param name="entity">Task or Resource Assignment</param>
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
/// Calls the action to update an entity, only Task and Resource Assignment for now
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
    task["msdyn_progress"] = 0.34m;
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
    assignment["msdyn_start"] = DateTime.Now;
    assignment["msdyn_finish"] = DateTime.Now;

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
```
