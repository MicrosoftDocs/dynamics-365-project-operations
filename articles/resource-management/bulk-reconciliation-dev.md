---
title: Reconcile projects with Bulk Reconciliation
description: This article explains how you can reconcile differences between assignments and bookings by using the bulk reconciliation API.
author: abriccetti
ms.author: abriccetti
ms.date: 08/15/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Reconcile projects with Bulk Reconciliation

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing_

Microsoft Dynamics 365 Project Operations supports the reconciliation of bookings to assignments for the bookable resources on a project. Use this functionality to fix the alignment between bookings and assignments.

*Resource reconciliation* is the process of aligning bookings with assignments when there is a difference between the resource's total booking hours and a rollup of the resource's task assignments for a specific project in each period.

The following list describes some of the reasons why bookings and assignments might become out of alignment:

- A project is delayed. As a result, the assignments and therefore the contours are moved.
- A project is paused or moved. As a result, the assignments are moved. Therefore, excess bookings and booking shortages occur and cause more delays.
- A resource's calendar is modified. As a result, the contours are modified.
- A project's calendar is modified.
- One or more tasks are assigned to a resource, but the resource isn't booked.
- A resource is assigned and booked, but then a new resource is assigned.

Currently, the [resource reconciliation](resource-reconciliation-overview.md) functionality in Project Operations allows for limited reconciliation. Customers should use the **Bulk Reconciliation** custom action to efficiently reconcile bookings for entire projects at one time.

## Key concepts

- **Assignments** – Assignments are part of the project planning and tracking process. Project managers use them to commit resources or assign them to project tasks in the project schedule.
- **Bookings** – Bookings are the hard or soft allocation of resources to a project. Depending on the booking method that is used, bookings typically consume a bookable resource's capacity.
- **Contours** – Contours represent the distribution of the assignment hours per day.

## Bulk Reconciliation custom action

### Name

msdyn\_ResourceReconciliation

### Input parameters

There are four input parameters. All of them must be defined and non-null.

The following table provides a summary of the four parameters.

| Parameter               | Type              | Value |
|-------------------------|-------------------|-------|
| Target                  | Entity Reference  | The entity reference of the project to reconcile resources with. |
| msdyn_Start             | Datetime          | The date to start to reconcile from. |
| msdyn_End               | Datetime          | The date to reconcile until. |
| msdyn_BookableResources | Entity Collection | The collection of bookable resources to reconcile with. |

### Validations

Some validations can fail the whole bulk reconciliation process. Other validations can fail individual operations for each resource.

The following validations fail the whole bulk reconciliation process:

- Null checks and retrieves the project to confirm the existence of the project in the organization.
- The start date is after the end date.
- The number of bookable resources is more than zero.

The following validations fail an individual operation for resource reconciliation:

- No existing bulk reconciliation operations that are running for the bookable resource overlap the specified start and end times.
- Null checks and retrieves the bookable resource to confirm the existence of the bookable resource in the organization.
- Null checks and confirms that the bookable resource is associated with a team member on the target project.

### Definition of reconciled

Currently, the reconciliation grid in the user interface (UI) and the Resource Reconciliation Asynchronous Plugin (API) define the term *reconciled* differently. The plugin uses a narrower or stricter definition. Therefore, everything that the plugin considers reconciled should also be reconciled according to the reconciliation grid. However, the opposite isn't always true. Some known scenarios that are unrelated to this work break the reconciliation grid. These scenarios usually involve cases where the effort for contours exceeds the duration, where there are existing bookings, and where the **Extend Booking** action is then attempted. Although the Bulk Reconciliation feature can correctly reconcile the resources in these scenarios, the resources might continue to appear unreconciled in the reconciliation grid.

### Reconciliation operation logs

The **Bulk Reconciliation** custom action creates a reconciliation operation log (msdyn\_reconciliationoperationlog) for each resource that is reconciled. The reconciliation operation logs contain error information about failures, details about the number of bookings that were created, information about cancellations, the runtime in seconds, and the reconciliation request ID. Each run of the **Bulk Reconciliation** custom action has a unique request ID. This request ID can be used to find the operations that are associated with a specific bulk reconciliation request.

| Logical name                      | Type            | Description |
|-----------------------------------|-----------------|-------------|
| msdyn_name                        | String          | The resource request ID followed by a number that counts the operations in the bulk operation. |
| msdyn_project                     | Lookup          | The project to reconcile resources with. |
| msdyn_bookableresource            | Lookup          | The bookable resource that is reconciled. |
| msdyn_reconciliationrequestid     | String          | The unique identifier of all requests in the same bulk operation. |
| msdyn_startofreconciliationperiod | Datetime        | The date to start reconciliation. |
| msdyn_endofreconciliationperiod   | Datetime        | The date to stop reconciliation. |
| statuscode                        | Choice Picklist | <p>The status of the reconciliation.</p><ul><li>**Value:** 192350001<br>**Label:** Completed<br>**Meaning:** Reconciliation was successfully completed.</li><li>**Value:** 192350002<br>**Label:** Reconciling<br>**Meaning:** Reconciliation is currently in progress.</li><li>**Value:** 192350003<br>**Label:** Reconciliation Failed<br>**Meaning:** An error occurred during reconciliation. Review the error details for more information.</li></ul> |
| msdyn_reconcilaitiondetails       | String          | <p>A JavaScript Object Notation (JSON) object that contains the following details about the operation:</p><ul><li>BookingsCreated</li><li>BookingsCanceled</li><li>RuntimeInSeconds</li></ul> |
| msdyn_errorcode                   | String          | The exception code. |
| msdyn_errormessage                | String          | The exception message, which includes details about the exception. |

## Example

```c#
using System;
using System.Runtime.Serialization;
using Microsoft.Xrm.Sdk;

public class BulkReconciliationSample
{
    private IOrganizationService organizationService;

    public BulkReconciliationSample(IOrganizationService organizationService)
    {
        this.organizationService = organizationService;
    }

    public void SampleRun()
    {
        // Example project GUID
        Guid projectId = new Guid("11111111-1111-1111-1111-111111111111");
        var project = new Entity("msdyn_project", projectId);

        // Example start and end dates
        DateTime start = DateTime.Now;
        DateTime end = DateTime.Now.AddDays(30);

        // Example bookable resources
        EntityCollection bookableResources = new EntityCollection();
        bookableResources.Entities.Add(new Entity("bookableresource", new Guid("11111111-1111-1111-1111-111111111111")));

        CallBulkReconciliationAPI(project.ToEntityReference(), start, end, bookableResources);
        Console.WriteLine("Done ...");
    }

    private void CallBulkReconciliationAPI(EntityReference project, DateTime start, DateTime end, EntityCollection bookableResources)
    {
        OrganizationRequest req = new OrganizationRequest("msdyn_ResourceReconciliation");
        req["Target"] = project;
        req["msdyn_Start"] = start;
        req["msdyn_End"] = end;
        req["msdyn_BookableResources"] = bookableResources;

        OrganizationResponse response = OrganizationService.Execute(req);
    }
}
```
