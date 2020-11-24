---
title: "What's new or changed in Project Service Automation Update Release 26, V3"
---

Project Service Automation Update Release 26, V3
================================================

We’re pleased to announce the latest update for the Project Service Automation
application for Dynamics 365. This release includes some important improvements
to quality, performance, and usability. This release is compatible with Dynamics
365 9.x. To update to this release, visit the Admin Center for Dynamics 365
online solutions page to install the update. For more information, see [Install,
update, or remove a preferred
solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project
Service Automation V3, Update Release 26 This version has a build number of
V3.10.44.56 and is generally available through a self-update in December 2020.

Update Release 26
-----------------

### Bug fixes

**Time and Expense**

The following issues have been fixed:

-   Users are able to change the task on a time entry that has been
    approved/Submitted.

-   "Object Reference Not Set" Error when saving Time Entry.

-   Time Entry Import from resource assignments creates time entries with the
    incorrect DateTime values.

-   When Project Service Automation are both installed, the "New" button is
    displaying twice on command bar for Time Entries in the Field Service app.

-   Allow Unit and Unit group cells updates on Expense Estimates grid.

-   Update Time entry edit form to include Timeline.

-   Time Approval for non project time entries block as the system is looking
    for a project approver role.

**Resource Management**

The following issues have been fixed:

-   Added validation in the **PostProjectCreate** plugin to check for a Primary
    Requirement before Creating one.

-   Project Team Member quick create form throws a null reference exception if
    fields are removed from the form.

-   Generate Requirements for 12 hours over 1 year will fail.

-   Improved error message null reference exception during Resource Requirement
    Creation.

**Project Management**

The following issues have been fixed:

-   Improved validation to address null reference exception generated on the
    **PreProjectUpdate** plugin.

-   Projects published by the Microsoft Project desktop add-in delete unassigned
    assignments.

-   Added new validation when a task’s project reference is invalid due to null
    reference exception in **PreValidateProjectTaskUpdate** plugin.

-   Team Member grid does not show distinct assignments on the team member
    record.

-   Add new validation and error messages due to null reference exception in
    **PreProjectTaskDelete** plugin.

**Sales**

The following issues have been fixed:

-   When selecting a project based line in quote or contract, the suggestion
    button is should only be visible on selecting product based line associated
    with an existing product.

-   Split **Create_Product** privilege from **Create_ProjectContract** privilege.

-   Deleting an invoice line causes null ref failure
    **MarkReadyToInvoiceForProductContractLineAfterDeletingInvoice**.
