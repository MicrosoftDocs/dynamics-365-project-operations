---
title: Project timesheet mobile application 
description: This article provides information about the Microsoft Dynamics 365 Project Timesheet mobile application. The Project Timesheet mobile app enables users to submit and approve timesheets for projects on their mobile device.
author: mohitmenon
ms.author: mohitmenon
ms.date: 03/19/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.dyn365.ops.version: 10.0
ms.search.validFrom: 2019-01-15

---

# Project timesheet mobile application

[!include [banner](../includes/banner.md)]

## Overview

The Microsoft Dynamics 365 Project Timesheet mobile app lets users submit and approve timesheets for projects on their mobile device (iPhone or Android). This mobile app surfaces the timesheet functionality that resides in the Project management and accounting area of Dynamics 365 Finance. It helps improve user productivity and efficiency, and also enables timely entry and approval of project timesheets.

## Deprecation of mobile app (Dec 2025)

Microsoft ended support for Xamarin on **May 1, 2024**. As a result, the Dynamics 365 Project Timesheet mobile app (which is based on Xamarin) will be **deprecated by Dec 31, 2025**. 

You can use [Timesheets optimized for mobile](Mobile-timesheets.md) as an alternative mobile experience that supports creation, submission, and reviewing of timesheets. 

> [!IMPORTANT]
>  Learn about the end of Microsoft Xamarin support in the [Xamarin Support Policy](https://dotnet.microsoft.com/en-us/platform/support/policy/xamarin). Microsoft recommends that customers switch to [Timesheets optimized for mobile](Mobile-timesheets.md) to avoid potential disruptions caused by security issues that result from ending Xamarin support.

## Download and install the mobile app

Download and install the Microsoft Dynamics 365 Project Timesheet mobile app for
Android or iPhone from the mobile store for your device.

## Enable the app 

In Finance, the Project Timesheet
mobile app must be enabled. To enable the functionality, go to **Project
management and accounting parameters \> Timesheet** and select the **Enable Microsoft
Dynamics 365 Project Timesheet** parameter.

### Resolve sign-in issues

**Issue:** During sign-in to the Project Timesheet Mobile app, users receive an error message that states that they "can't access the application '2bc50526-cdc3-4e36-a970-c284c34cbd6e' in that tenant."

**Issue:** During sign-in to the Project Timesheet Mobile app, users receive an error that resembles one of the following examples:

- "AADSTS50020: User account '[user name]' from identity provider 'https://sts.windows.net/[app ID]' doesn't exist in tenant '[tenant ID]' and can't access the application '[app ID]' in that tenant."
- "Selected user account doesn't exist in tenant '[tenant ID]' and can't access the application '[app ID]' in that tenant."

**Explanation:** These issues are caused by a change that was made to Microsoft Entra ID in May 2022 and that is related to external users. Because this change wasn't made to finance and operations apps, it can affect customers on any version of the platform or application.

**Fix:** All external users must be invited to the tenant through Microsoft Entra ID. For more information, see [Invite users with Microsoft Entra B2B collaboration](/power-platform/admin/invite-users-azure-active-directory-b2b-collaboration).

## Sign in to the app

1.  Start the app on your mobile device.

2.  Enter your Finance URL.

3.  The first time that you sign in, you're prompted for your user name and
    password. Enter your credentials.

4. You'll be signed into your default company.

## Submit a project timesheet

You can create and submit a project timesheet in the app. You can base a new timesheet on
information from a previous timesheet, saved lines, or project assignments. If
you're designated as a delegate, you can also enter a timesheet for another
worker. To create a timesheet as a delegate, select the **Menu** button and then select a resource name.

The timesheet page creates a new timesheet for the timesheet period, based
on the current date. The work week is displayed. If the timesheet period
covers multiple weeks, you can select another work week from the work week tabs.
If a timesheet exists for the current date, it's displayed. If you need to
create a new timesheet in a different timesheet period, select the **Menu** button and then select
**New timesheet**.

You can enter project information by clicking the **Add time** action
or the **Copy time from** action. The **Copy time from** action copies project
line information, but not the hours. The **Copy time from** menu includes the
following options:

- **Copy from existing timesheet** - Copy timesheet lines from an existing timesheet.

- **Copy from favorite** - Create new timesheet lines by using the timesheet settings that you selected as favorites.

- **Copy from assignment** - Create new timesheet lines from assigned projects.

The project information that is displayed is dependent on the mobile parameters
that you defined on the **Project management and accounting parameters** page.

In the **Legal entity** field, select the legal entity for which you performed
project work. The **Legal entity** field is available only if intercompany timesheet
support has been enabled for your legal entity.

Select the customer who is associated with the project for the timesheet. For the initial release on the Android, entry by customer isn't supported, as you must select the project first. If you selected the project first, the **Customer** field is filled in automatically.

In the **Project** field, select the project that you're entering time for. The **Customer** field is filled in automatically.

The customer and project lookups enable searching across both customers and projects.

Select information in the **Category**, **Activity**, **Line property**, **Sales tax group**, and **Item sales tax group** fields as required. These fields can be overridden.

The **Line property** field is set to a default value, based on project
management and accounting parameters. When the project/category and
category/resource parameters are enabled, the **Line property** value is set to
the default value you have defined for this validation. When the
project/category and category/resource parameters aren't enabled, the **Line
property** value defaults according to the **Enable default line property**
field on the **Project management and accounting parameters** page. The **Line
property** value can be overridden.

Select a day to add time. Enter the number of hours that you worked each day.

To add comments about the hours you're entering, click **Add comments**, and
then enter comments for an internal audience, customer audience, or both.
Internal comments can be viewed by project managers. Customer comments are
included on invoices.

To save the line as a favorite, select the check box, and then click **Save as
favorite**.

Financial dimension and attachment support aren't provided in the mobile
application.

Continue adding project lines as needed to complete your timesheet.

Click **Submit** to send the timesheet to the approval workflow.

## Review timesheets

A list of the timesheets that need to be reviewed is available on the menu. This option is only available if you've been designated as a workflow approver. Both header and line approval are supported. Line level
approval offers the ability to mark one or more lines for approval. After
reviewing the timesheet information, click **Approve**, **Delegate**, or
**Return** to continue the workflow.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
