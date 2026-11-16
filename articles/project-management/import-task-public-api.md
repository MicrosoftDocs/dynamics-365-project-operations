---
title: Use import tasks API
description: Learn how to import tasks between projects in Dynamics 365 Project Operations, include dependencies, and track asynchronous completion.
author: dishantpopli
ms.author: dishantpopli
ms.reviewer: johnmichalak
ms.date: 11/16/2026
ms.topic: how-to
ms.custom:
  - bap-template
---

# Import tasks between projects by using the public API

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Use the `msdyn_ImportProjectTasksV1` public API to copy selected tasks from a source project into a target project in Dynamics 365 Project Operations. You can include dependencies between selected tasks and track the import through operation sets. This article helps developers and integration makers submit an import and confirm its completion.

## How task import works

The API is an unbound Dataverse action that you call by using `POST`. You don't bind the request to a specific project record in the URL. Instead, you supply both project IDs in the request body.

1. Submit the source project ID, target project ID, and selected tasks.
1. The API validates the request and creates one or more operation sets.
1. Background processing executes the operation sets automatically.
1. Use the returned operation set IDs to check whether the import succeeds.

> [!IMPORTANT]
> An HTTP `200 OK` response doesn't mean that the import is complete. Check every returned operation set before you treat the import as successful.

## Prerequisites

Before you call the API, ensure that you:

- Have the `msdyn_ImportProjectTasksV1` action available in your environment.
- Authenticate to the Dataverse environment and have the privileges required to read the source project and its tasks, and create tasks in the target project.
- Can read the operation set records used to track completion.
- Have the source and target projects in the environment, and they have different IDs.
- Have the target project active.
- Don't have a project copy operation in progress for either project.
- Provide at least one source task. Every selected task exists, belongs to the source project, and appears only once in the request.

## Request reference

Send the request to the following endpoint. Replace `contoso.crm.dynamics.com` with your environment host.

```http
POST https://contoso.crm.dynamics.com/api/data/v9.2/msdyn_ImportProjectTasksV1
```

The following table describes the required request parameters.

| Parameter | Type | Description |
|-----------|------|-------------|
| **`SourceProjectId`** | `Edm.Guid` | ID of the source `msdyn_project` record. Supply a nonempty GUID. |
| **`TargetProjectId`** | `Edm.Guid` | ID of the target `msdyn_project` record. Supply a nonempty GUID different from `SourceProjectId`. |
| **`Tasks`** | `Collection(Edm.String)` | Nonempty array of JSON-encoded strings. Each string describes one source task to import. |

### Task entry format

Each element of `Tasks` is a string containing a serialized JSON object, not a nested JSON object. Use the following camelCase field names inside that string.

| Field | Type | Description |
|-------|------|-------------|
| **`taskId`** | GUID string | ID of the source `msdyn_projecttask` record to copy. |
| **`copyDependency`** | Boolean | Included in the task entry format. The current implementation uses `dependsOn` to determine dependency links; don't rely on this field to suppress them. |
| **`dependsOn`** | Array of GUID strings | IDs of source tasks that are predecessors of this task. A dependency is created only when both tasks are included in `Tasks`. Use an empty array when you don't want dependencies for this task. |

For example, the following object describes a task with one predecessor, before you serialize it:

```json
{
  "taskId": "bbbbbbbb-1111-2222-3333-444444444444",
  "copyDependency": true,
  "dependsOn": [
    "aaaaaaaa-1111-2222-3333-444444444444"
  ]
}
```

Include both task IDs in the import selection to recreate this dependency. The API doesn't automatically add predecessor tasks that aren't selected.

## Import selected tasks

The following example imports two tasks. The second task depends on the first task.

1. Identify the source project, target project, and source task IDs.
1. Prepare each task entry and serialize it to a JSON string.
1. Send an authenticated request with the following headers and body. The example omits the authorization header; use your application's Dataverse authentication mechanism.

   ```http
   POST https://contoso.crm.dynamics.com/api/data/v9.2/msdyn_ImportProjectTasksV1 HTTP/1.1
   Accept: application/json
   Content-Type: application/json
   OData-MaxVersion: 4.0
   OData-Version: 4.0

   {
     "SourceProjectId": "6b6d1f2a-9a1e-4a0b-8f7d-111111111111",
     "TargetProjectId": "2c3d4e5f-7b8c-4d1e-9a2b-222222222222",
     "Tasks": [
       "{\"taskId\":\"aaaaaaaa-1111-2222-3333-444444444444\",\"copyDependency\":false,\"dependsOn\":[]}",
       "{\"taskId\":\"bbbbbbbb-1111-2222-3333-444444444444\",\"copyDependency\":true,\"dependsOn\":[\"aaaaaaaa-1111-2222-3333-444444444444\"]}"
     ]
   }
   ```

1. Store the `OperationSetIds` and `RequestId` from the response.
1. [Track completion](#track-import-completion) before you start work that depends on the imported tasks.

To avoid manually escaping inner JSON, you can build the request body in JavaScript:

```javascript
const selectedTasks = [
  {
    taskId: "aaaaaaaa-1111-2222-3333-444444444444",
    copyDependency: false,
    dependsOn: []
  },
  {
    taskId: "bbbbbbbb-1111-2222-3333-444444444444",
    copyDependency: true,
    dependsOn: ["aaaaaaaa-1111-2222-3333-444444444444"]
  }
];

const requestBody = JSON.stringify({
  SourceProjectId: "6b6d1f2a-9a1e-4a0b-8f7d-111111111111",
  TargetProjectId: "2c3d4e5f-7b8c-4d1e-9a2b-222222222222",
  Tasks: selectedTasks.map(task => JSON.stringify(task))
});
```

### Response

An accepted request returns HTTP `200 OK`. The following example shows the response properties used to track the import:

```json
{
  "OperationSetIds": [
    "9f0e1d2c-3b4a-5c6d-7e8f-999999999999",
    "1a2b3c4d-5e6f-7a8b-9c0d-aaaaaaaaaaaa"
  ],
  "RequestId": "77777777-8888-9999-aaaa-bbbbbbbbbbbb"
}
```

| Property | Type | Description |
|----------|------|-------------|
| **`OperationSetIds`** | `Collection(Edm.String)` | IDs of the `msdyn_operationset` records created for the import. An import can produce multiple operation sets. |
| **`RequestId`** | `Edm.Guid` | Correlation identifier for the import. Save it with the operation set IDs for troubleshooting and support. |

## Track import completion

Read the `msdyn_status` column on each operation set returned by the import.

1. For each ID in `OperationSetIds`, send an authenticated request like the following example:

   ```http
   GET https://contoso.crm.dynamics.com/api/data/v9.2/msdyn_operationsets(9f0e1d2c-3b4a-5c6d-7e8f-999999999999)?$select=msdyn_status HTTP/1.1
   Accept: application/json
   ```

1. Read the status in the response:

   ```json
   {
     "msdyn_operationsetid": "9f0e1d2c-3b4a-5c6d-7e8f-999999999999",
     "msdyn_status": 192350003
   }
   ```

1. Continue checking operation sets that don't have a terminal status. Use a polling interval with backoff rather than continuous requests.
1. Stop when all operation sets reach a terminal status. Report success only when every operation set is `Completed`.

The following table lists the operation set status values.

| Status | Value | Terminal status | Meaning |
|--------|-------|-----------------|---------|
| **Open** | `192350000` | No | The operation set is open for staging. |
| **Pending** | `192350001` | No | Processing is pending or in progress. |
| **Abandoned** | `192350002` | Yes | The operation set is abandoned without successful completion. |
| **Completed** | `192350003` | Yes | Processing completes successfully for this operation set. |
| **Failed** | `192350004` | Yes | Processing fails for this operation set. |

Apply a timeout in your integration. If the timeout expires before all operation sets finish, retain the identifiers and report the outcome as unresolved, not successful. You can resume checking the same operation sets later.

### Expected outcome

When all operation sets are `Completed`, the selected tasks are copied into the target project with new task IDs. Dependencies supplied through `dependsOn` are recreated between selected tasks. If you select both a parent task and its child task, their hierarchy is preserved. If you select a child without its parent, the child is imported as a root task.

## Error handling and retry guidance

Validation errors return in the original API response. Errors during background execution occur after that response, so your integration must also check operation set status.

| Issue | Cause or interpretation | Recommended action |
|-------|-------------------------|--------------------|
| **The request fails validation** | A required value is missing or invalid, the task selection is empty or invalid, or the projects don't meet the prerequisites. | Check the error returned by Dataverse. Correct the request or project state before submitting again. |
| **A dependency isn't imported** | One of its tasks isn't selected, or the predecessor isn't listed in `dependsOn`. | Include both tasks and specify the predecessor in the successor's `dependsOn` array. |
| **An operation set is `Failed` or `Abandoned`** | The import doesn't fully succeed. | Inspect the target project and available system job error details. Retain all returned IDs before deciding which tasks to submit again. |
| **The request succeeds but tasks aren't available yet** | Background processing hasn't completed. | Check every returned operation set instead of resubmitting the import. |
| **The client loses the response or reaches a timeout** | The outcome is unknown; the import might still be running or might have completed. | Reconcile the target project and any identifiers already recorded before submitting another request. |
| **Repeated submissions create duplicate tasks** | Each import creates new target tasks. Repeating the same request doesn't update the previously imported tasks. | Prevent duplicate submissions in your integration. Don't blindly retry an import with an unknown outcome. |

For support investigations, provide the `RequestId`, all returned `OperationSetIds`, the target project ID, and the time of the request. `RequestId` is a correlation identifier, not the primary key of a system job or a filterable `asyncoperation` column.

[!INCLUDE [footer-include](../includes/footer-banner.md)]

## Related information

- [Import tasks to project](import-tasks-to-project.md)
- [Use Project schedule APIs to perform operations with scheduling entities](schedule-api-preview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]