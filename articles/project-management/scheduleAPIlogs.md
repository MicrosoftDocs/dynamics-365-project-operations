---
title: Project Scheduling Logs
description: This topic provides information and samples for using the Project Scheduling Logs
author: ruhercul
ms.date: 11/16/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Use Project Scheduling Logs to track Failures related to Project Scheduling Service and Project Scheduling APIs

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_, _Project for the Web_



Overview
========

Project Operations leverages [Project for the
Web](https://support.microsoft.com/en-us/office/what-is-project-for-the-web-c19b2421-3c9d-4037-97c6-f66b6e1d2eb5)
as its primary scheduling engine. In lieu of the standard Dataverse Web APIs,
Project Operations utilizes new Project Scheduling APIs to create, update and
delete Project Tasks, Resource Assignments, Task Dependencies Project Buckets or Project Teams
Members. However, when executing create, update or delete operations on work
breakdown structure entities programmatically, errors may occur. To track errors
and history of operations, two new administrative logs: **Operation Sets** and
**Project Scheduling Service (PSS),** have been implemented. These logs can be
accessed by navigating to **Settings** \> **Schedule Integration**.

![Scheduling Log Data Model](media/LOGDATAMODEL.jpg)

Operation Set Log
=================

The Operation Set log will track the execution of an operation set which is
issued to batch one or many create, update or delete operations on the
**Projects, Project Tasks, Resource Assignments, Task Dependencies, Project
Buckets or Project Team Members**. The overall status of the Operation Set is
tracked in the Operation in Status field. The Details of the Operation Set
Payload are captured in the related Operation Set Detail records.

Operation Set
-------------

| **SchemaName**        | **Description**                                                          | **DisplayName**        |
|-----------------------|--------------------------------------------------------------------------|------------------------|
| msdyn_completedon     | Datetime the operationSet completed or failed                            | CompletedOn            |
| msdyn_correlationid   | Request correlationId                                                    | CorrelationId          |
| msdyn_description     | The description of the operationSet.                                     | Description            |
| msdyn_executedon      | The datetime this record was executed on                                 | Executed On            |
| msdyn_operationsetId  | Unique identifier for entity instances                                   | OperationSet           |
| msdyn_Project         | Project related to the operation set.                                    | Project                |
| msdyn_projectid       | Request projectId                                                        | ProjectId (Deprecated) |
| msdyn_projectName     | N/A                                                                      | N/A                    |
| msdyn_PSSErrorLog     | Unique identifier for PSS Error Log associated with OperationSet.        | PSS Error Log          |
| msdyn_PSSErrorLogName | N/A                                                                      | N/A                    |
| msdyn_status          | OperationSet status                                                      | Status                 |
| msdyn_statusName      | N/A                                                                      | N/A                    |
| msdyn_useraadid       | The Azure Active Directory Object ID of the User this request belongs to | UserAADID              |

Operation Set Detail
--------------------

| **SchemaName**             | **Description**                                                                      | **DisplayName**       |
|----------------------------|--------------------------------------------------------------------------------------|-----------------------|
| msdyn_cdspayload           | Serialized CDS fields for request                                                    | CdsPayload            |
| msdyn_entityname           | The name of the entity for this request.                                             | EntityName            |
| msdyn_httpverb             | The request method                                                                   | HTTPVerb (Deprecated) |
| msdyn_httpverbName         | N/A                                                                                  | N/A                   |
| msdyn_operationset         | Unique identifier for the operationSet this record belongs to                        | OperationSet          |
| msdyn_operationsetdetailId | Unique identifier for entity instances                                               | OperationSet Detail   |
| msdyn_operationsetName     | N/A                                                                                  | N/A                   |
| msdyn_operationtype        | Operation type of the operation set detail.                                          | OperationType         |
| msdyn_operationtypeName    | N/A                                                                                  | N/A                   |
| msdyn_psspayload           | Serialized PSS fields for request                                                    | PssPayload            |
| msdyn_recordid             | The identified for request record                                                    | Record ID             |
| msdyn_requestnumber        | An auto generated number used to identify the order in which requests where received | Request Number        |

Project Scheduling Service (PSS) Error Logs
===========================================

The PSS Error logs are uses to capture failures when either a save or open
operation is attempted by the Project Scheduling Service. There are three
currently supported scenarios where PSS Error logs are generated:

1.  User initiated actions in the UI that critically fail (e.g. unable to create
    an assignment because of missing privileges)

2.  Programmatically PSS is unable to create, update or delete an entity (or any
    cascading operation)

3.  Errors experienced by the user when failing to open a record (e.g. open
    project, refreshing a team member)

PSS Log
-------

| **SchemaName**      | **Description**                                                                 | **DisplayName** |
|---------------------|---------------------------------------------------------------------------------|-----------------|
| msdyn_CallStack     | The call stack of the exception.                                                | Call Stack      |
| msdyn_correlationid | The correlation id of the error.                                                | CorrelationId   |
| msdyn_errorcode     | Used to store Cds error code or http error code                                 | Error Code      |
| msdyn_HelpLink      | Link of the public help documentation.                                          | Help Link       |
| msdyn_log           | The log from PSS                                                                | Log             |
| msdyn_project       | Project associated with the error log.                                          | Project         |
| msdyn_projectName   | The Name of the Project when the payload of the operation set will be persisted | N/A             |
| msdyn_psserrorlogId | Unique identifier for entity instances                                          | PSS Error Log   |
| msdyn_SessionId     | Project session id.                                                             | Session Id      |

Error Log Cleanup
=================

Both PSS Error Logs and Operation Set Logs can be cleaned up every 90 days by
default, therefore any records older than 90 days will be deleted. However, by
modifying the value of the msdyn_StateOperationSetAge field on the Project
Parameter, administrators can adjust the cleanup range between 1 and 120 days.
This is achieved by using one of the three methods outlined below:

1.  By customizing 'Project Parameter' entity: Creation of a custom Form and
    including the 'Stale Operations Set Age' field .

2.  Via Client code using WebApi
    SDK <https://docs.microsoft.com/en-us/powerapps/developer/model-driven-apps/clientapi/reference/xrm-webapi/updaterecord>

3.  Via Service SDK code using Xrm SDK updateRecord (Client API reference) in
    model-driven apps - Power Apps Includes description and supported parameters
    for the updateRecord method.

>   Xrm.WebApi.retrieveMultipleRecords('msdyn_projectparameter')  
>   .then(function (response) {  
>   parameter = response.entities[0];  
>   var staleOperationValue = prompt("All records older than (x) days will be
>   deleted, please enter X between 1 to 90 days", 1)  
>   var newData = {};  
>   newData.msdyn_projectparameterid = parameter.msdyn_projectparameterid;  
>   newData.msdyn_staleoperationsetage = parseInt(staleOperationValue);  
>   Xrm.WebApi.updateRecord("msdyn_projectparameter",
>   parameter.msdyn_projectparameterid, newData).then(  
>   function success(result) {  
>   console.log("Project Parameter: Stale Operation Expiry is set to: " +
>   newData.msdyn_staleoperationsetage);  
>   // perform operations on record update  
>   Xrm.WebApi.retrieveMultipleRecords('msdyn_projectparameter')  
>   .then(function (response2) { console.log("Confirmed Project Parameter: Stale
>   Operation Expiry is set to: " +
>   response2.entities[0].msdyn_staleoperationsetage) });  
>   },  
>   function (error) {  
>   console.log("Failed to Update Project Ednpoint with error: " +
>   error.message);  
>   // handle error conditions  
>   }  
>   );  
>   });


