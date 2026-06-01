---
title: Project schedule API performance
description: This article provides information about the performance benchmarks of the Project schedule APIs and identifies best practices for optimum use.
author: dishantpopli
ms.author: dishantpopli
ms.date: 12/16/2025
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project schedule API performance

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core, Project for the web_

This article provides information about the performance benchmarks of the Project schedule application programming interfaces (APIs) and identifies the best practices for optimizing usage.

## Project Scheduling Service

The Project Scheduling Service is a multitenant service that runs in Microsoft Azure. It's designed to improve interaction by providing a fast and fluid experience when users work on projects. This improvement is achieved by accepting change requests, processing them, and then immediately returning the result. The service asynchronously persists to Dataverse and doesn't block users from performing other operations.

The Project schedule APIs rely on the Project Scheduling Service to run requests. Later sections of this article describe these requests in more detail.

The Project schedule APIs are designed to work with the following work breakdown structure (WBS) entities:

- Project
- Project Task
- Project Task Dependency
- Project Team Member
- Resource Assignment
  
Both out-of-box fields and custom fields are supported. Unless otherwise noted, all common operations are supported, such as create, update, and delete. For more information, see [Use Project schedule APIs to perform operations and scheduling entities](schedule-api-preview.md).

As part of the Project schedule APIs, a unit-of-work pattern is added. This pattern is known as an OperationSet, and you can use it when you need to process several requests in a single transaction.

The following illustration shows the flow that a partner experiences when this feature is used.

:::image type="content" source="./media/dataverse-project-scheduling-service-flow.png" alt-text="Screenshot of Dataverse and project scheduling service flow.":::

**Step 1**: A client makes an API call to an Open Data Protocol (OData) endpoint `ExecuteOperationSetV3`. This call does the following actions:

1. Creates an OperationSet.
1. Loads the OperationSet with Project schedule API requests.
1. Sends all the changes to Project Scheduling Service in one batch.

The Project Scheduling Service runs its own validations on requests in the batch. Any validation failures undo the batch and return an exception to the caller. If the Project Scheduling Service successfully accepts the batch, it updates the OperationSet status to reflect that it's processing the OperationSet.

**Step 2**: This step represents the PERSIST phase. The Project Scheduling Service asynchronously writes the batch to Dataverse in a transaction. If the write operation is successful, the OperationSet is marked as **Completed**. Any errors roll back the transaction and the batch, and the OperationSet is marked as **Failed**.

## Performance methodology

You run all operations a combined 2,280 times and report the P90 execution time measurements. Measure single-record and bulk operations.

For a single-record operation, the OperationSet contains one request. For bulk operations, it contains 20, 50, or 100 requests. Report each bulk size separately.

Run these operations on a UR58 Project Operations Core distributed across North America, EMEA, and APAC.

## Results

### Single-record operations

The following table shows the execution times for the creation, update, and deletion of a single record. The times are in seconds.

**Schedule API Duration**: Time taken by ExecuteOperationSetV3

**Total Duration**: Schedule API duration + Project Save Service time + time taken to sync to Dataverse

| Operation | Record type | Schedule API Duration - Required fields | Schedule API Duration - All supported fields | Total Duration - Required fields | Total Duration - All supported fields |
|-----------|-------------|----------------------------------------|---------------------------------------------|----------------------------------|--------------------------------------|
| Create | Project | 2.18 | 2.41 | 2.18 | 2.41 |
| Create | Task | 1.67 | 1.73 | 7.86 | 12.63 |
| Create | Assignment | 1.46 | 2.03 | 10.86 | 12.81 |
| Create | Dependency | 1.43 | 1.55 | 9.07 | 10.35 |
| Update | Project | 1.56 | 1.59 | 7.91 | 11.00 |
| Update | Task | 1.51 | 1.72 | 7.79 | 18.72 |
| Update | Team Member | 1.94 | 1.92 | 10.71 | 9.37 |
| Delete | Task | 1.53 | 1.55 | 7.92 | 9.68 |
| Delete | Assignment | 1.44 | 1.44 | 7.89 | 9.36 |
| Delete | Dependency | 1.23 | 1.44 | 8.88 | 8.40 |
| Delete | Team Member | 1.41 | 1.49 | 9.91 | 10.97 |

> [!NOTE]
>
> * The **Team Member** entity isn't included in the create operation, because you can create a Team Member directly in Dataverse.
> * Update operations on the **Resource Assignments** and **Project Task Dependency** entities aren't supported.
> * Delete operation on the **Project** entity isn't supported.

### Bulk operations

The following table shows the execution times for the creation, update, and deletion of many records. Specifically, Microsoft measured the execution times for the creation of 20, 50, and 100 records in a single OperationSet. The times are in seconds.

**Schedule API Duration**: Time taken by ExecuteOperationSetV3

**Total Duration**: Schedule API duration + Project Save Service time + time taken to sync to Dataverse

| Operation | Record type | No. of Records | Schedule API Duration - Required fields | Schedule API Duration - All supported fields | Total Duration - Required fields | Total Duration - All supported fields |
|-----------|-------------|----------------|----------------------------------------|---------------------------------------------|----------------------------------|--------------------------------------|
| Create | Task | 20 | 1.88 | 2.81 | 9.57 | 32.75 |
| Create | Task | 50 | 2.41 | 3.17 | 12.82 | 36.96 |
| Create | Task | 100 | 4.14 | 3.97 | 15.96 | 47.55 |
| Create | Assignment | 20 | 2.61 | 1.98 | 12.51 | 26.62 |
| Create | Assignment | 50 | 2.49 | 2.73 | 18.49 | 62.40 |
| Create | Assignment | 100 | 3.85 | 4.04 | 35.43 | 68.69 |
| Create | Dependency | 20 | 1.71 | 1.92 | 8.91 | 19.92 |
| Create | Dependency | 50 | 2.38 | 2.58 | 18.72 | 39.73 |
| Create | Dependency | 100 | 3.45 | 4.80 | 41.29 | 83.41 |
| Update | Task | 20 | 2.03 | 5.36 | 8.82 | 20.42 |
| Update | Task | 50 | 3.72 | 11.97 | 30.37 | 64.36 |
| Update | Task | 100 | 5.94 | 20.21 | 69.37 | 155.52 |
| Update | Team Member | 20 | 2.17 | 3.86 | 15.01 | 12.61 |
| Update | Team Member | 50 | 3.88 | 6.33 | 17.89 | 21.84 |
| Update | Team Member | 100 | 6.39 | 12.40 | 30.23 | 31.85 |
| Delete | Task | 20 | 1.62 | 1.66 | 13.40 | 24.33 |
| Delete | Task | 50 | 2.25 | 2.46 | 33.75 | 54.92 |
| Delete | Task | 100 | 3.20 | 3.28 | 73.90 | 110.70 |
| Delete | Assignment | 20 | 1.55 | 1.58 | 8.69 | 13.98 |
| Delete | Assignment | 50 | 2.06 | 2.38 | 15.87 | 23.17 |
| Delete | Assignment | 100 | 3.04 | 3.62 | 39.27 | 54.76 |
| Delete | Dependency | 20 | 1.57 | 1.80 | 11.49 | 13.73 |
| Delete | Dependency | 50 | 2.24 | 2.53 | 19.40 | 45.26 |
| Delete | Dependency | 100 | 3.31 | 3.73 | 31.56 | 48.14 |
| Delete | Team Member | 20 | 2.05 | 2.19 | 13.67 | 15.09 |
| Delete | Team Member | 50 | 3.35 | 3.16 | 20.62 | 22.58 |
| Delete | Team Member | 100 | 4.18 | 5.15 | 25.49 | 36.66 |

> [!NOTE]
>
> 1. The table doesn't include bulk create operations on the Project and Team Member entities, because the runtime for those operations resembles the runtime when the API for creating a single record is called multiple times. These APIs run immediately in Dataverse.
> 1. Update operations on the Resource Assignments and Project Task Dependency entities aren't supported.
> 1. Delete operations on the Project entity aren't supported.

## Best practices

Based on the preceding scenario results, the APIs perform better in the following conditions:

- Use the latest versions of the Schedule APIs as they're optimized for better performance.
- Group as many operations together as possible. The average runtime for bulk operations is better than the average runtime for single-record operations. The smaller the number of operation sets in use, the faster the average execution time is.
- Set only the minimum attributes that are required to accomplish your scenario. Be selective about the types of nonrequired fields included in an operation set request. Fields that contain foreign keys or rollup fields negatively affect performance.
