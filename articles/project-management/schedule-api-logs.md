---
title: Project scheduling logs
description: This article provides information and samples that helps you use the Project Scheduling logs to track failures that are related to the Project Scheduling Service and Project Scheduling APIs.
author: abriccetti
ms.author: abriccetti
ms.date: 02/26/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project scheduling logs

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_, _Project for the Web_

Microsoft Dynamics 365 Project Operations uses [Project for the Web](https://support.microsoft.com/office/what-is-project-for-the-web-c19b2421-3c9d-4037-97c6-f66b6e1d2eb5) as its primary scheduling engine. Instead of using the standard Microsoft Dataverse Web application programming interfaces (APIs), Project Operations uses the new Project Scheduling APIs to create, update, and delete project tasks, resource assignments, task dependencies, project buckets, and project team members. However, errors might occur when you programmatically run create, update, or delete operations on work breakdown structure (WBS) entities. To track these errors and the history of operations, the system implements two new administrative logs: **Operation Set** and **Project Scheduling Service (PSS)**. To access these logs, go to **Settings** \> **Schedule Integration**.

The following illustration shows the data model for the Project Scheduling logs.

:::image type="content" source="media/LOGDATAMODEL.jpg" alt-text="Screenshot of the data model for the Project Scheduling logs.":::

## Operation Set log

The Operation Set log tracks the execution of an operation set that runs one or many create, update, or delete operations in a batch on projects, project tasks, resource assignments, task dependencies, project buckets, or project team members. The **Operation in Status** field shows the overall status of the operation set. Related Operation Set Detail records capture the details of the operation set payload.

### Operation Set

The following table shows the fields that are related to the **Operation Set** entity.

| SchemaName            | Description                                                                                                  | DisplayName            |
|-----------------------|--------------------------------------------------------------------------------------------------------------|------------------------|
| msdyn_completedon     | The date and time when the operation set completed or failed.                                                | CompletedOn            |
| msdyn_correlationId   | The **correlationId** value of the request.                                                                  | CorrelationId          |
| msdyn_description     | The description of the operation set.                                                                        | Description            |
| msdyn_executedon      | The date and time when the record ran.                                                                       | Executed On            |
| msdyn_operationsetId  | The unique identifier of entity instances.                                                                   | OperationSet           |
| msdyn_Project         | The project that is related to the operation set.                                                            | Project                |
| msdyn_projectId       | The **projectId** value of the request.                                                                      | ProjectId (Deprecated) |
| msdyn_projectName     | Not applicable.                                                                                              | Not applicable         |
| msdyn_PSSErrorLog     | The unique identifier of the Project Scheduling Service error log that is associated with the operation set. | PSS Error Log          |
| msdyn_PSSErrorLogName | Not applicable.                                                                                              | Not applicable         |
| msdyn_status          | The status of the operation set.                                                                             | Status                 |
| msdyn_statusName      | Not applicable.                                                                                              | Not applicable         |
| msdyn_useraadId       | The Microsoft Entra object ID of the user that the request belongs to.                     | UserAADID              |

### Operation Set Detail

The following table shows the fields that are related to the **Operation Set Detail** entity.

| SchemaName                 | Description                                                                                 | DisplayName           |
|----------------------------|---------------------------------------------------------------------------------------------|-----------------------|
| msdyn_cdspayload           | The serialized Dataverse fields for the request.                                            | CdsPayload            |
| msdyn_entityname           | The name of the entity for the request.                                                     | EntityName            |
| msdyn_httpverb             | The request method.                                                                         | HTTPVerb (Deprecated) |
| msdyn_httpverbName         | Not applicable.                                                                             | Not applicable        |
| msdyn_operationset         | The unique identifier of the operation set that the record belongs to.                      | OperationSet          |
| msdyn_operationsetdetailId | The unique identifier of entity instances.                                                  | OperationSet Detail   |
| msdyn_operationsetName     | Not applicable.                                                                             | Not applicable        |
| msdyn_operationtype        | The operation type of the operation set detail.                                             | OperationType         |
| msdyn_operationtypeName    | Not applicable.                                                                             | Not applicable        |
| msdyn_psspayload           | The serialized Project Scheduling Service fields for the request.                           | PssPayload            |
| msdyn_recordid             | The identifier of the request record.                                                       | Record ID             |
| msdyn_requestnumber        | An automatically generated number that identifies the order that requests were received in. | Request Number        |

## Project Scheduling Service error logs

The Project Scheduling Service error logs capture failures that occur when the Project Scheduling Service tries a **Save** or **Open** operation. These logs are generated in three supported scenarios:

- User-initiated actions critically fail. For example, an assignment can't be created because of missing privileges.
- The Project Scheduling Service can't programmatically create, update, delete, or perform any other cascading operation on an entity.
- The user experiences errors when a record fails to open. For example, when a project is opened or a team member's information is updated.

> [!NOTE]
> When the system creates a log entry, it sets the owner of the project record as the owner of that record. If the user doesn't have at least user-level read access to the **PSS Error Log** table, the system doesn't create a record.
>

### Project Scheduling Service log

The following table shows the fields that are included in the Project Scheduling Service log.

| SchemaName          | Description                                                                    | DisplayName    |
|---------------------|--------------------------------------------------------------------------------|----------------|
| msdyn_CallStack     | The call stack of the exception.                                               | Call Stack     |
| msdyn_correlationId | The correlation ID of the error.                                               | CorrelationId  |
| msdyn_errorcode     | A field that stores the Dataverse error code or the HTTP error code.           | Error Code     |
| msdyn_HelpLink      | A link to the public Help documentation.                                       | Help Link      |
| msdyn_log           | The log from the Project Scheduling Service.                                   | Log            |
| msdyn_project       | The project that is associated with the error log.                             | Project        |
| msdyn_projectName   | The name of the project if the payload of the operation set persists.          | Not applicable |
| msdyn_psserrorlogId | The unique identifier of entity instances.                                     | PSS Error Log  |
| msdyn_SessionId     | The project session ID.                                                        | Session ID     |

## Error log cleanup

By default, both Project Scheduling Service error logs and the Operation Set log are cleaned up every 90 days. The system deletes any records that are older than 90 days. However, administrators can change the value of the **msdyn_StateOperationSetAge** field on the **Project Parameters** page to adjust the cleanup range to any value between 1 and 120 days. You can change this value by using several methods:

- Customize the **Project Parameter** entity by creating a custom page and adding the **Stale Operations Set Age** field.
- Use client code that uses the [WebApi software development kit (SDK)](/powerapps/developer/model-driven-apps/clientapi/reference/xrm-webapi/updaterecord).
- Use Service SDK code that uses the Xrm SDK **updateRecord** method (Client API reference) in model-driven apps. Power Apps includes a description and supported parameters for the **updateRecord** method.

    ```C#
    Xrm.WebApi.retrieveMultipleRecords('msdyn_projectparameter').then(function (response) {
        parameter = response.entities[0];
        var staleOperationValue = prompt("All records older than (x) days are deleted, please enter X between 1 to 90 days", 1)
        var newData = {};
        newData.msdyn_projectparameterid = parameter.msdyn_projectparameterid;
        newData.msdyn_staleoperationsetage = parseInt(staleOperationValue);
        Xrm.WebApi.updateRecord("msdyn_projectparameter", parameter.msdyn_projectparameterid, newData).then(
            function success(result) {
                console.log("Project Parameter: Stale Operation Expiry is set to: " + newData.msdyn_staleoperationsetage);
                // perform operations on record update
                Xrm.WebApi.retrieveMultipleRecords('msdyn_projectparameter')
                .then(function (response2) { console.log("Confirmed Project Parameter: Stale Operation Expiry is set to: " + response2.entities[0].msdyn_staleoperationsetage) });
            },
            function (error) {
                console.log("Failed to Update Project Ednpoint with error: " + error.message);
            // handle error conditions
            }
        );
    });
    ```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
