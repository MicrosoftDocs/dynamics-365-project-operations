---
title: Use Schedule APIs to perfom operations with Scheduling entities
description: This topic provides information and samples for using Schedule APIs.
author: sigitac
manager: Annbe
ms.date: 04/05/2021
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Use Schedule APIs to operations with Scheduling entities 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

## Scheduling entities

Schedule APIs provide the ability to perform create, update, and delete operations with **Scheduling entities**. These entities are managed through the Scheduling engine in Microsoft Project for the Web. Create, update, and delete operations with **Scheduling entities** were restricted in earlier Dynamics 365 Project Operations releases.

The following table provides a full list of the **Scheduling entities**:

| Entity name  | Entity logical name |
| --- | --- |
| Project | msdyn\_project |
| Project Task  | msdyn\_projecttask  |
| Project Task Dependency  | msdyn\_projecttaskdependency  |
| Resource Assignment | msdyn\_resourceassignment |
| Project Bucket  | msdyn\_projectbucket |
| Project Team Member | msdyn\_projectteam |

## OperationSet

OperationSet is a unit-of-work pattern that can be used when several schedule impacting requests must be processed within a transaction.

## Schedule APIs
The following is a list of current Schedule APIs.

  - **msdyn_CreateProjectV1**: This API can be used to create a project. The project and default project bucket is created immediately.
  - **msdyn_CreateTeamMemberV1**: This API can be used to create a project team member. The team member record is created immediately.
  - **msdyn_CreateOperationSetV1**: This API can be used to to schedule several requests that must be performed withinin a transaction.
  - **msdyn_PSSCreateV1**: This API can be used to create an entity. The entity can be any of the Scheduling entities that support the create operation.
  - **msdyn_PSSUpdateV1**: This API can be used to update an entity. The entity can be any of the Scheduling entities that support the update operation.
  - **msdyn_PSSDeleteV1**: This API can be used to delete an entity. The entity can be any of the Scheduling entities that support the delete operation.
  - **msdyn_ExecuteOperationSetV1**: This API is used to execute all of the operations within the given operation set. 

## Using Schedule APIs with OperationSet

Because records with both **CreateProjectV1** and **CreateTeamMemberV1** are created immediately, these APIs can't be used in the **OperationSet** directly. However, you can use the API to create needed records, create an **OperationSet**, and then use these pre-created records in the **OperationSet**.

## Supported operations

| Scheduling entity | Create | Update | Delete | Important considerations |
| --- | --- | --- | --- | --- |
Project task | Yes | Yes | Yes | None |
| Project task dependency | Yes | Yes | | Project task dependency records aren't updated. Instead, an old record can be deleted and a new record can be created. |
| Resource assignment | Yes | Yes | | Operations with the following fields aren't supported: **BookableResourceID**, **Effort**, **EffortCompleted**, **EffortRemaining**, abd **PlannedWork**. Resource assignment records aren't updated. Instead, the old record can be deleted and a new record can be created. |
| Project bucket | N/A | N/A | N/A | The default bucket is created using the **CreateProjectV1** API. |
| Project team member | Yes | Yes | Yes | For the create operation, use the API **CreateTeamMemberV1**. |
| Project | Yes | Yes | N/A | Operations with the following fields aren't supported: **StateCode**, **BulkGenerationStatus**, **GlobalRevisionToken**, **CalendarID**, **Effort**, **EffortCompleted**, **EffortRemaining**, **Progress**, **Finish**, **TaskEarliestStart**, and **Duration**. |

These APIs can be called with entity objects that include custom fields.

The ID property is optional. If it's provided, the system attempts to use it and throws an exception if it can't be used. If it isn't provided, the system will generate it.

## Limitations and known issues

- Schedule APIs can only be used by **Users with Microsoft Project License.** They can't be used by application users, system users, integration users, or other users that don't have the required license.
- Each **OperationSet** can only have a maximum of 100 operations.
- Each user can only have a maximum of 10 open **OperationSets**.
- Project Operations currently supports a maximum of 500 total tasks on a project.
- **OperationSet** failure status and failure logs aren't currently available.
- Schedule APIs are in Public preview. Using these APIs in a Production environment isn't supported by Microsoft.

## Sample scenario

In this scenario, you will create a project, a team member, four tasks, and two resource assignments. Next, you will update one task, update the project, delete one task, delete one resource assignment, and create a task dependency.

  ```C#
  Entity project = CreateProject();
  project.Id = CallCreateProjectAction(project);
  var projectReference = project.ToEntityReference();
  
  var teamMember = new Entity("msdyn\_projectteam", Guid.NewGuid());
  teamMember["msdyn\_name"] = $"TM {DateTime.Now.ToShortTimeString()}";
  teamMember["msdyn\_project"] = projectReference;
  var createTeamMemberResponse = CallCreateTeamMemberAction(teamMember);
  
  var description = $"My demo {DateTime.Now.ToShortTimeString()}";
  var operationSetId = CallCreateOperationSetAction(project.Id, description);
  
  var task1 = GetTask("1WW", projectReference);
  var task2 = GetTask("2XX", projectReference, task1.ToEntityReference());
  var task3 = GetTask("3YY", projectReference);
  var task4 = GetTask("4ZZ";, projectReference);

  var assignment1 = GetResourceAssignment("R1", teamMember, task2, project);
  var assignment2 = GetResourceAssignment"R2", teamMember, task3, project);

  var task1Response = CallPssCreateAction(task1, operationSetId);
  var task2Response = CallPssCreateAction(task2, operationSetId);
  var task3Response = CallPssCreateAction(task3, operationSetId);
  var task4Response = CallPssCreateAction(task4, operationSetId);

  varassignment1Response = CallPssCreateAction(assignment1, operationSetId);
  varassignment2Response = CallPssCreateAction(assignment2, operationSetId);

  task2["msdyn\_subject"] = "Updated Task";
  var task2UpdateResponse = CallPssUpdateAction(task2, operationSetId);

  project["msdyn\_subject"] = $"Proj update {DateTime.Now.ToShortTimeString()}";
  var projectUpdateResponse = CallPssUpdateAction(project, operationSetId);

  var task4DeleteResponse = CallPssDeleteAction(task4.Id.ToString(), task4.LogicalName, operationSetId);

  varassignment2DeleteResponse = CallPssDeleteAction(assignment2.Id.ToString(), assignment2.LogicalName, operationSetId);

  var dependency1 = GetTaskDependency(project, task2, task3);
  var dependency1Response = CallPssCreateAction(dependency1, operationSetId);

  CallExecuteOperationSetAction(operationSetId);
  Console.WriteLine("Done....");
  ```
  
## Additional samples

#region Call actions 

  ```C#

    ///<summary>
    /// Calls the action to create an operationSet
    /// </summary>
    /// <paramname="projectId">project id for the operations to be included in this operationSet>/param>
    /// <paramname="description">description of this operationSet</param>
    /// <returns>operationSet id</returns>
    privatestring CallCreateOperationSetAction(Guid projectId, string description)
    {
      OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn\_CreateOperationSetV1");
      operationSetRequest["ProjectId"] = projectId.ToString();
      operationSetRequest["Description"] = description;
      OrganizationResponse response = organizationService.Execute(operationSetRequest);
      return response["OperationSetId"].ToString();
    }

    /// <summary>
    /// Calls the action to create an entity, only Task and Resource Assignment for now
    /// </summary>
    /// <paramname="entity">Task or Resource Assignment</param>
    /// <paramname="operationSetId">operationSet id</param>
    /// <returns>OperationSetResponse</returns>
    private OperationSetResponse CallPssCreateAction(Entity entity, string operationSetId)
    {
      OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn\_PssCreateV1");
      operationSetRequest["Entity"] = entity;
      operationSetRequest["OperationSetId"] = operationSetId;
      return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
    }

    /// <summary<
    /// Calls the action to update an entity, only Task for now
    /// </summary>
    /// <paramname="entity">Task or Resource Assignment</param>
    /// <paramname="operationSetId">operationSet Id</param>
    /// <returns>OperationSetResponse</returns>
    private OperationSetResponse CallPssUpdateAction(Entity entity, string operationSetId)
    {
      OrganizationRequest operationSetRequest = new OrganizationRequest("msdyn\_PssUpdateV1");
      operationSetRequest["Entity"] = entity;
      operationSetRequest["OperationSetId"] = operationSetId;
      return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));
    }

///\&lt;summary\&gt;

/// Calls the action to update an entity, only Task and Resource Assignment for now

///\&lt;/summary\&gt;

///\&lt;paramname=&quot;recordId&quot;\&gt;Id of the record to be deleted\&lt;/param\&gt;

///\&lt;paramname=&quot;entityLogicalName&quot;\&gt;Entity logical name of the record\&lt;/param\&gt;

///\&lt;paramname=&quot;operationSetId&quot;\&gt;OperationSet Id\&lt;/param\&gt;

///\&lt;returns\&gt;OperationSetResponse\&lt;/returns\&gt;

private OperationSetResponse CallPssDeleteAction(string recordId, string entityLogicalName, string operationSetId)

{

OrganizationRequest operationSetRequest = new OrganizationRequest(&quot;msdyn\_PssDeleteV1&quot;);

operationSetRequest[&quot;RecordId&quot;] = recordId;

operationSetRequest[&quot;EntityLogicalName&quot;] = entityLogicalName;

operationSetRequest[&quot;OperationSetId&quot;] = operationSetId;

return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));

}

///\&lt;summary\&gt;

/// Calls the action to execute requests in an operationSet

///\&lt;/summary\&gt;

///\&lt;paramname=&quot;operationSetId&quot;\&gt;operationSet id\&lt;/param\&gt;

///\&lt;returns\&gt;OperationSetResponse\&lt;/returns\&gt;

private OperationSetResponse CallExecuteOperationSetAction(string operationSetId)

{

OrganizationRequest operationSetRequest = new OrganizationRequest(&quot;msdyn\_ExecuteOperationSetV1&quot;);

operationSetRequest[&quot;OperationSetId&quot;] = operationSetId;

return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));

}

///\&lt;summary\&gt;

/// This can be used to abandon an operationSet that is no longer needed

///\&lt;/summary\&gt;

///\&lt;paramname=&quot;operationSetId&quot;\&gt;operationSet id\&lt;/param\&gt;

///\&lt;returns\&gt;OperationSetResponse\&lt;/returns\&gt;

protected OperationSetResponse CallAbandonOperationSetAction(Guid operationSetId)

{

OrganizationRequest operationSetRequest = new OrganizationRequest(&quot;msdyn\_AbandonOperationSetV1&quot;);

operationSetRequest[&quot;OperationSetId&quot;] = operationSetId.ToString();

return GetOperationSetResponseFromOrgResponse(organizationService.Execute(operationSetRequest));

}

///\&lt;summary\&gt;

/// Calls the action to create a new project

///\&lt;/summary\&gt;

///\&lt;paramname=&quot;project&quot;\&gt;Project\&lt;/param\&gt;

///\&lt;returns\&gt;project Id\&lt;/returns\&gt;

private Guid CallCreateProjectAction(Entity project)

{

OrganizationRequest createProjectRequest = new OrganizationRequest(&quot;msdyn\_CreateProjectV1&quot;);

createProjectRequest[&quot;Project&quot;] = project;

OrganizationResponse response = organizationService.Execute(createProjectRequest);

var projectId = Guid.Parse((string)response[&quot;ProjectId&quot;]);

return projectId;

}

///\&lt;summary\&gt;

/// Calls the action to create a new project team member

///\&lt;/summary\&gt;

///\&lt;paramname=&quot;teamMember&quot;\&gt;Project team member\&lt;/param\&gt;

///\&lt;returns\&gt;project team member Id\&lt;/returns\&gt;

privatestring CallCreateTeamMemberAction(Entity teamMember)

{

OrganizationRequest request = new OrganizationRequest(&quot;msdyn\_CreateTeamMemberV1&quot;);

request[&quot;TeamMember&quot;] = teamMember;

OrganizationResponse response = organizationService.Execute(request);

return (string)response[&quot;TeamMemberId&quot;];

}

private OperationSetResponse GetOperationSetResponseFromOrgResponse(OrganizationResponse orgResponse)

{

return JsonConvert.DeserializeObject\&lt;OperationSetResponse\&gt;((string)orgResponse.Results[&quot;OperationSetResponse&quot;]);

}

private EntityCollection GetDefaultBucket(EntityReference projectReference)

{

var columnsToFetch = new ColumnSet(&quot;msdyn\_project&quot;, &quot;msdyn\_name&quot;);

var getDefaultBucket = new QueryExpression(&quot;msdyn\_projectbucket&quot;)

{

ColumnSet = columnsToFetch,

Criteria =

{

Conditions =

{

new ConditionExpression(&quot;msdyn\_project&quot;, ConditionOperator.Equal, projectReference.Id),

new ConditionExpression(&quot;msdyn\_name&quot;, ConditionOperator.Equal, &quot;Bucket 1&quot;)

}

}

};

return organizationService.RetrieveMultiple(getDefaultBucket);

}

private Entity GetBucket(EntityReference projectReference)

{

var bucketCollection = GetDefaultBucket(projectReference);

if (bucketCollection.Entities.Count \&gt; 0)

{

return bucketCollection[0].ToEntity\&lt;Entity\&gt;();

}

thrownew Exception($&quot;Please open project with id {projectReference.Id} in the Dynamics UI and navigate to the Tasks tab&quot;);

}

private Entity CreateProject()

{

var project = new Entity(&quot;msdyn\_project&quot;, Guid.NewGuid());

project[&quot;msdyn\_subject&quot;] = $&quot;Proj {DateTime.Now.ToShortTimeString()}&quot;;

return project;

}

private Entity GetTask(string name, EntityReference projectReference, EntityReference parentReference = null)

{

var task = new Entity(&quot;msdyn\_projecttask&quot;, Guid.NewGuid());

task[&quot;msdyn\_project&quot;] = projectReference;

task[&quot;msdyn\_subject&quot;] = name;

task[&quot;msdyn\_effort&quot;] = 4d;

task[&quot;msdyn\_scheduledstart&quot;] = DateTime.Today;

task[&quot;msdyn\_scheduledend&quot;] = DateTime.Today.AddDays(5);

task[&quot;msdyn\_progress&quot;] = 0.34m;

task[&quot;msdyn\_start&quot;] = DateTime.Now.AddDays(1);

task[&quot;msdyn\_projectbucket&quot;] = GetBucket(projectReference).ToEntityReference();

task[&quot;msdyn\_LinkStatus&quot;] = new OptionSetValue(192350000);

//Custom field handling

/\*

task[&quot;new\_custom1&quot;] = &quot;Just my test&quot;;

task[&quot;new\_age&quot;] = 98;

task[&quot;new\_amount&quot;] = 591.34m;

task[&quot;new\_isready&quot;] = new OptionSetValue(100000000);

\*/

if (parentReference == null)

{

task[&quot;msdyn\_outlinelevel&quot;] = 1;

}

else

{

task[&quot;msdyn\_parenttask&quot;] = parentReference;

}

return task;

}

private Entity GetResourceAssignment(string name, Entity teamMember, Entity task, Entity project)

{

var assignment = new Entity(&quot;msdyn\_resourceassignment&quot;, Guid.NewGuid());

assignment[&quot;msdyn\_projectteamid&quot;] = teamMember.ToEntityReference();

assignment[&quot;msdyn\_taskid&quot;] = task.ToEntityReference();

assignment[&quot;msdyn\_projectid&quot;] = project.ToEntityReference();

assignment[&quot;msdyn\_name&quot;] = name;

assignment[&quot;msdyn\_start&quot;] = DateTime.Now;

assignment[&quot;msdyn\_finish&quot;] = DateTime.Now;

return assignment;

}

protected Entity GetTaskDependency(Entity project, Entity predecessor, Entity successor)

{

var taskDependency = new Entity(&quot;msdyn\_projecttaskdependency&quot;, Guid.NewGuid());

taskDependency[&quot;msdyn\_project&quot;] = project.ToEntityReference();

taskDependency[&quot;msdyn\_predecessortask&quot;] = predecessor.ToEntityReference();

taskDependency[&quot;msdyn\_successortask&quot;] = successor.ToEntityReference();

taskDependency[&quot;msdyn\_linktype&quot;] = new OptionSetValue(192350000);

return taskDependency;

}

#endregion

}

#region OperationSetResponse DataContract --- Sample code ----

[DataContract]

publicclassOperationSetResponse

{

[DataMember(Name = &quot;operationSetId&quot;)]

public Guid OperationSetId { get; set; }

[DataMember(Name = &quot;operationSetDetailId&quot;)]

public Guid OperationSetDetailId { get; set; }

[DataMember(Name = &quot;operationType&quot;)]

publicstring OperationType { get; set; }

[DataMember(Name = &quot;recordId&quot;)]

publicstring RecordId { get; set; }

[DataMember(Name = &quot;correlationId&quot;)]

publicstring CorrelationId { get; set; }

}

#endregion
