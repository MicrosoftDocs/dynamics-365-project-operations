---
title: Create and update a project
description: This topic provides information about updating projects Project Operations.
author: ruhercul
ms.date: 10/01/2020
ms.topic: article
ms.reviewer: kfend 
ms.author: ruhercul
---

# Update a project

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Below is a summary of the fields that can be updated on a project after it has been created and any applicable implications of the updates.

## Project detail fields

- **Name**: The title of the project.
- **Description**: An overview of the project.
- **Customer**: The company the project will be delivered to.
- **Calendar template**: The working hours of the project. When the field is changed, the entire schedule is recalculated.
- **Currency**: The currency for the project. This field defaults based on the currency defined in the contracting unit. When the contracting unit is updated, the field is also updated.
- **Contracting Unit**: The organizational unit that represents the company group or division that is primarily responsible for winning the sale and managing the delivery of work and services to the customer.  When the Organzational unit of the Project Manager is undefined, this field defaults to the value defined in the Project Parameters.
- **Project Manager**: The project team member who has the authority to review and approve time entries and expenses.

## Estimate fields

- **Estimated Start Date**: The date that the project will begin. When this field is updated, any tasks on the project will move proportionately with the start new start date.
- **Finish Date**: The date that the project is scheduled to end.
- **Effort**: The estimated effort of the project. When tasks are added to the project, this field is no longer editable.
- **Estimated Labor Cost**: The estimated labor cost of the project. When labor costs are added to the project, this field is no longer editable.
- **Estimated Expenses**: The estimated expenses of the project. When expenses are added to the project, this field is no longer editable.

## Project actual fields
- **Actual Start**: The date that the project started.
- **Actual Finish**: To be updated when a project has been completed.

## Project status fields

- **Overall Project Status**: The overall project health provided by the Project manager.
- **Comments**: A narrative regarding the current health of the project provided by the Project manager.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
