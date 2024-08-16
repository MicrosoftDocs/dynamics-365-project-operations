---
title: Reconcile Projects with Bulk Reconciliation
description: This article provides information about how you can reconcile differences between assignments and bookings using our bulk reconciliation API.
author: abriccetti
ms.author: abriccetti
ms.date: 08/15/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Reconcile Projects with Bulk Reconciliation

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Dynamics 365 Project Operations supports the ability for the reconciliation of bookings to assignments for bookable resources on a project. Customers can use this functionality to fix alignment between bookings and assignments. 
**Resource reconciliation** is the process of aligning bookings with assignments when there's a difference between the resource’s total booking hours and a rollup of their task assignments, for a specific project in each period.  
There are many potential reasons why bookings and assignments may become out of alignment such as:

- A project is delayed, moving the assignments and thus the contours.
- A project is paused/moved, moving the assignments, resulting in excess bookings and bookings shortages for more delay.
- A resource's calendar was modified, modifying the contours. 
- A project's calendar was modified.
- A resource was assigned one or multiple tasks, but hasn't been booked.
- A resource was assigned, and booked, but a new resource is assigned.

Currently, the [Resource reconciliation](./resource-reconciliation-overview.md) functionality in Microsoft Dynamics 365 Project Operations allows limited reconciliation.  Customers should use the Bulk Reconciliation Custom Action to efficiently reconcile bookings for entire projects at a time. 

## Key Concepts

- **Assignments**: Assignments are part of project planning and tracking process and allow Project Managers to commit or assign resources to project tasks in the project schedule. 
- **Bookings**: Bookings are the hard or soft allocation of the resources to a project. Depending on the booking method used, bookings typically consume a bookable resource’s capacity. 
- **Contours**: Contours represent the distribution of the assignment hours per day. 

## Bulk Reconciliation Custom Action

### Name
msdyn_ResourceReconciliation

### Input Parameters
There are four input parameters. All parameters must be defined and non-null.
- Target – The entity reference of the project to reconcile.
- msdyn_Start – The start date to start reconciling from. 
- msdyn_End – The end date to stop reconciling at. 
- msdyn_BookableResources – A collection of bookable resources with which to reconcile.

The following table provides a summary of the four parameters:

| Parameter                | Type             | Value                                            |
|--------------------------|------------------|--------------------------------------------------|
| Target                   | Entity Reference | The project with which to reconcile resources on |
| msdyn_Start              | Datetime         | Date to start reconciliation                     |
| msdyn_End                | Datetime         | Date to stop reconciliation                      |
| msdyn_BookableResources  | Entity Collection| Collection of bookable resources to reconcile    |

### Validations

There are validations that can fail the entire bulk reconciliation process, and those that can fail the individual operation for each resource. 
The following validations will fail the entire bulk reconciliation process:
- Null checks and retrieves the project to confirm the existence of the project in the organization.
- The start date is after the end date. 
- The number of bookable resources is greater than zero. 

The following validations will fail an individual operation for resource reconciliation:
- There are no existing Bulk Reconciliation Operations running for the bookable resource overlapping with the specified start and end times. 
- Null checks and retrieves the bookable resource to confirm the existence of the bookable resource in the organization.
- Null checks and confirms the bookable resource is associated with a team member on the target project.

### Definition of Reconciled

Currently the definition of reconciled differs between the Reconciliation Grid on the User Interface (UI) and Resource Reconciliation Asynchronous Plugin (API), with the plugin using a narrower or stricter definition. Therefore, everything that is deemed reconciled by the plugin should also be reconciled according to the reconciliation grid. However, the opposite isn't always true. There are known scenarios unrelated to this work that break the reconciliation grid (usually involving contours with effort > duration, with existing bookings, then Extend Booking is attempted). Though these can be reconciled by the Bulk Reconciliation feature correctly, they may still appear unreconciled on the reconciliation grid.

### Reconciliation Operation Logs
The Bulk Reconciliation custom action creates a Reconciliation Operation Log (msdyn_reconciliationoperationlog) for each resource that is reconciled. These reconciliation operation logs contain error information on failures, details on the number of bookings created, canceled, the runtime in seconds, and the reconciliation request ID. Each Bulk Reconciliation custom action run has a unique request ID, which can be used to find the operations associated with a specific Bulk Reconciliation request.

| **Logical Name**                  | **Type**         | **Description**                                                                        |
| --------------------------------- | ---------------- | -------------------------------------------------------------------------------------- |
| msdyn_name                        | String           | Resource Request ID followed by a number counting the operations in the Bulk Operation.|
| msdyn_project                     | Lookup           | The project with which to reconcile resources on                                       |
| msdyn_bookableresource            | Lookup           | Bookable Resource reconciled.                                                          |
| msdyn_reconciliationrequestid     | String           | Unique identifier for all requests in the same Bulk Operation.                         |
| msdyn_startofreconciliationperiod | Datetime         | Date to start reconciliation.                                                          |
| msdyn_endofreconciliationperiod   | Datetime         | Date to stop reconciliation.                                                           |
| statuscode                        | Choice Picklist  | <ul><li>**Value:** 192350001<br>**Label:** Completed<br>**Meaning:** Reconciliation was successfully completed.</li><li>**Value:** 192350002<br>**Label:** Reconciling<br>**Meaning:** Reconciliation is currently in progress.</li><li>**Value:** 192350003<br>**Label:** Reconciliation Failed<br>**Meaning:** There was an error during reconciliation. Check the error details for more details.</li></ul> |
| msdyn_reconcilaitiondetails       | String           | JSON object containing details about the operation.<br><ul><li>BookingsCreated</li><li>BookingsCanceled</li><li>RuntimeInSeconds</li></ul>                                                                                        |
| msdyn_errorcode                   | String           | Exception code.                                                                        |
| msdyn_errormessage                | String           | Exception message with details on the exception.                                       |

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
