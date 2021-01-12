---
title: "What's new or changed in Project Service Automation Update Release 27, V3"
---

Project Service Automation Update Release 27, V3
================================================

We’re pleased to announce the latest update for the Project Service Automation
application for Dynamics 365. This release includes some important improvements
to quality, performance, and usability. This release is compatible with Dynamics
365 9.x. To update to this release, visit the Admin Center for Dynamics 365
online solutions page to install the update. For more information, see [Install,
update, or remove a preferred
solution](https://docs.microsoft.com/power-platform/admin/install-remove-preferred-solution).

This topic lists the features and fixes that are new or changed for Project
Service Automation V3, Update Release 27 This version has a build number of
V3.10.45.98 and is generally available through a self-update in January 2021.

Update Release 27
-----------------

### Bug fixes

**General**

The following issues have been fixed:

-   Solution plug-ins have not been set logs to auto-delete.

-   Auto-upgrade fails because the PSA solution contains legacy null NavBarArea
    and title element.

**Time and Expense**

The following issues have been fixed:

-   Time Entry Grid displays incorrect data for TimeZone Independent date
    behavior.

-   Time Entry Grid creates incorrect time for TimeZone Independent date
    behavior.

-   Task Lookup not limited to selected Project in Edit Time Entry form.

-   Time Approval for non-project time entries is blocked as the system is
    looking for a project approver role.

-   Correct Entries on Actuals throws the incorrect error message.

-   Refresh Project Totals does not handle null values for Actual Cost on Tasks
    correctly.

-   In specific instances, **Group By** filters in the project estimate tab does
    not display expense estimates.

-   Daylight Saving Time interval is not correct for Time Entries.

**Project Management**

The following issues have been fixed:

-   Improvements to caching to enhance performance related to loading the
    project form.

-   Obsolete Business Rule preventing project tasks from being completed.

-   Microsoft Project Add-in contours are not respecting the add-in’s calendar
    resulting in incorrect resource requirements.

-   Creating projects from templates incorrect sets the dates for assignments
    and prevents the ability to generate resource requirements.

-   User are unable to access 'Category', 'Description', 'Status' controls using
    keyboard.

-   Actual Sales values of the Project are not including Fee and Material sales
    values.

-   Aggregation of Actual Sales and Actual Cost happens incorrectly with
    different Exchange Rates.

-   Default Work Hour Template description is misleading.

-   Indenting a task does not remove **Category** in the user interface until it
    is refreshed.

-   Missing validation to ensure moving a project beyond its end date is not
    permitted.

**Sales**

The following issues have been fixed:

-   Null reference exception generated on a project quote line, due to "import
    from project estimation" being visible when a project has not been selected.

-   Error "Object reference not set to an instance of an object" while closing
    **quote as won.**

-   Adjustment status not set during actual reversal while unlinking a Project
    from **contractline.**

-   When Field Service and Project Service Automation are both installed, the
    **'Lock pricing'** and **'Use Current Pricing'** Options are not displayed
    at a same time in invoice form.

-   For Japanese language, inconsistent translation with other calendar-based
    forms in quotes.

-   Activate and Deactivate have been removed from Price List association
    entities in Project Service.
