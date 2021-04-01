---
title: What's new or changed in Project Service Automation Update Release 30, V3
description: This topic lists the features and fixes that are available in Project Service Automation Update Release 30, V3.
author: ruhercul
manager: kfend
ms.service: project-operations
ms.custom: dyn365-projectservice
ms.date: 04/01/2021
ms.topic: article
ms.author: ruhercul
audience: Admin
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365PS
  - ProjectOperations
---



# What's new or changed in Project Service Automation Update Release 30, V3

[!include [banner](../includes/psa-now-project-operations.md)]

We’re pleased to announce the latest update for the Project Service Automation application for Dynamics 365. This release includes some important improvements to quality, performance, and usability. This release is compatible with Dynamics 365 9.x. To update to this release, visit the Admin Center for Dynamics 365 online solutions page to install the update. For more information, see [Install, update, or remove a preferred solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project Service Automation V3, Update Release 30. This version has a build number of V3.10.51.61 and is generally available through a self-update in February 2021.

## Update Release 30

### Bug fixes

**Time and Expense**

The following issues have been fixed:

-   An error is thrown on save when the role field is removed from the time
    entry quick create.

-   The incorrect filter operator has been applied to the Time Entry Control.

-   Copied timesheets are note automatically displayed when using "Copy Week"
    button on the time entry control.

**Resource Management**

The following issues have been fixed:

-   When users extend bookings, the incorrect booking status is assigned to the
    hard booking.   Extend booking will respect the booking status defined as committed in the booking setup meta data.

-   When a valid booking status has not been specified, the error message is not
    correctly localized.

**Project Management**

The following issues have been fixed:

-   Users are able to create projects in one currency and related tasks in
    another currency.

**Sales**

The following issues have been fixed:

-   When a price list is copied, update prices does not update.

-   Closing a quote as won fails when the cost detail has a value for Origin.

-   On the Project Task Entity, "Estimated Cost" has been renamed to "Planned
    Cost (Base)"

-   Null Reference Exception generated when invoices are created or deleted.
