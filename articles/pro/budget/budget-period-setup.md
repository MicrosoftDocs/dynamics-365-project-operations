---
title: Set up a budget period
description: This article explains how to set up a budget period at the organization level and at the project level. A budget period is a prerequisite for time phasing.
author: niranjanmaski
ms.date: 11/12/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Set up a budget period

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Core deployment - deal to proforma invoicing._

This article explains how to set up a budget period at the organizational level and at the project level.

> [!NOTE]
> A budget period at the project level is required to enable time phasing of budgeted values and quantities over the budget line's time period.

## What is a budget period?

A budget period defines a week, month, quarter, and fiscal periods in your organization.

For example, in some countries/regions, the fiscal year and quarter 1 begin on April 1. In other countries/regions, they begin on January 1. The work week might begin on Monday or Sunday.

A budget period set up at the organization level is available for consumption at the project level. However, a project manager can override the organization-level budget period configuration at the project level to meet the requirements of a specific project.

## Set up a budget period at the organization level

To set up or edit a budget period at the organization level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Go to the **Settings** section in the lower-left navigation.
1. In the **General** category, select **Organizational Units**.
1. Find and select the desired organizational unit.
1. On the **Budget Period** tab, if there's no existing budget period in the grid, select **New Budget Period** to create one.
1. Select **Save & Close**. A budget period line is created in the grid.
1. To view or modify the budget period details, double-tap (or double-click) the budget period line.
1. Make any required updates, and then, on the Action Pane, select **Save**, or **Save & Close**. Depending on your updates, the budget period detail line is extended, or deleted and then re-created.

> [!NOTE]
> A budget period can be created with a Week, Month, Quarter or Year granularity. 

The following table describes the fields that are available.

| Field | Requirement | Description | Comments |
|---|---|---|---|
| Name | Optional | Enter a name of your choice to identify the budget period. | |
| Fiscal start | Mandatory | <p>Specify the month when the fiscal year begins. This month is also considered the start of quarter 1 for the budget period.</p><p>For example, if the fiscal start is January, quarter 1 is January through March.</p> | Updates to this field cause the budget period details to be deleted and re-created. |
| Interval | Mandatory | Specify the interval of default budget period configuration for the organization unit. You can choose from **Weekly, Monthly, Quarterly**, or **Yearly**. | Updates to this field cause the budget period details to be deleted and re-created. |
| Interval Start | Mandatory | If the chosen Interval is **Monthly**, specify when do you want to consider the **Month start date**. Month start date can be either the first day of work week or the first calendar day of the month. | Updates to this field delete the budget period details then re-create them. |
| Week starts on | Mandatory | <p>Specify the day of the week when the work week begins. The first occurrence of the specified weekday during a month is considered the start of that month.</p><p>For example, if the **Week starts on** field is set to **Monday**, the first Monday of a month is considered the start of that month for period calculation.</p> | Updates to this field cause the budget period details to be deleted and re-created. |
| Start year | Mandatory | <p>Specify the calendar year that budget period creation begins from.</p><p>For example, if the **Start year** field is set to **2023**, the budget period begins in 2023, in the month specified in the **Start month** field.</p> | Updates to this field extend the budget period details. |
| Start month | Mandatory | <p>Specify the month of the calendar year that budget period creation begins from.</p><p>For example, if the **Start year** field is set to **2023**, and the **Start month** field is set to **July**, the budget period begins July 2023.</p> | Updates to this field extend the budget period details. |
| End year | Mandatory | <p>Specify the calendar year when budget period creation ends.</p><p>For example, if the **End year** field is set to **2033**, the budget period ends in 2033, in the month specified in the **End month** field.</p> | Updates to this field extend the budget period details. |
| End month | Mandatory | <p>Specify the month when budget period creation ends.</p><p>For example, if the **End year** field is set to **2033**, and the **End month** field is set to **June**, the budget period ends the last week of June 2033.</p> | Updates to this field extend the budget period details. |

> [!NOTE]
> A budget period set up at the organization level serves as a template that you can easily copy and apply at the project level to meet your specific requirements. This approach streamlines the process of setting up budget periods for individual projects. It also helps ensure consistency and efficiency across different projects in the organization.

## Set up a budget period at the project level

To set up a budget period at the project level, follow these steps.

1. Sign in to Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the Action Pane, select **Budget**, and then select **Create budget period** on the dropdown menu.

The budget period configuration dialog box for the selected project appears. If an organization-level budget period is set up, the **Fiscal start** and **Week starts on** values are taken from it. Otherwise, by default, the **Fiscal start** field is set to **July**, and the **Week starts on** field is set to **Monday**. By default, the **Start year** and **Start month** fields are set to the project's start year and month, and the **End year** and **End month** fields are set to the project's end year and month.

You can edit the budget period configuration at the project level to meet your specific requirements. The following table describes the fields that are available.

> [!NOTE]
> After you copy a budget period to the project level, subsequent changes to the organization-level configuration have no effect on the project-level configuration. The project-level budget period becomes independent of and isolated from the organization-level template.

| Field | Requirement | Description | Comments |
|---|---|---|---|
| Name | Optional | Enter a name of your choice to identify the budget period. | |
| Fiscal start | Mandatory | <p>Specify the month when the fiscal year begins. This month is also considered the start of quarter 1 for the budget period.</p><p>For example, if the fiscal start is January, quarter 1 is January through March.</p> | Updates to this field cause the budget period details to be deleted and re-created. |
| Interval | Mandatory | Specify the interval of default budget period configuration for the organization unit. You can choose from **Weekly, Monthly, Quarterly**, or **Yearly**. | Updates to this field cause the budget period details to be deleted and re-created. |
| Interval Start | Mandatory | If the chosen Interval is **Monthly**, specify when do you want to consider the **Month start date**. Month start date can be either the first day of work week or the first calendar day of the month. | Updates to this field delete the budget period details then re-create them. |
| Week starts on | Mandatory | <p>Specify the day of the week when the work week begins. The first occurrence of the specified weekday during a month is considered the start of that month.</p><p>For example, if the **Week starts on** field is set to **Monday**, the first Monday of a month is considered the start of that month for period calculation.</p> | Updates to this field cause the budget period details to be deleted and re-created. |
| Start year | Mandatory | <p>Specify the calendar year that budget period creation begins from.</p><p>For example, if the **Start year** field is set to **2023**, the budget period begins in 2023, in the month specified in the **Start month** field.</p> | Updates to this field extend the budget period details. |
| Start month | Mandatory | <p>Specify the month of the calendar year that budget period creation begins from.</p><p>For example, if the **Start year** field is set to **2023**, and the **Start month** field is set to **July**, the budget period begins July 2023.</p> | Updates to this field extend the budget period details. |
| End year | Mandatory | <p>Specify the calendar year when budget period creation ends.</p><p>For example, if the **End year** field is set to **2033**, the budget period ends in 2033, in the month specified in the **End month** field.</p> | Updates to this field extend the budget period details. |
| End month | Mandatory | <p>Specify the month when budget period creation ends.</p><p>For example, if the **End year** field is set to **2033**, and the **End month** field is set to **June**, the budget period ends the last week of June 2033.</p> | Updates to this field extend the budget period details. |

## Edit a budget period at the project level

To edit a budget period that was created at the project level, follow these steps.

1. Sign in to Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the Action Pane, select **Budget**, and then select **Budget Periods** on the dropdown menu.
1. Select **Edit**.
1. Select **Save**, or **Save & Close**.

Depending on your updates, the budget period detail line is extended, or deleted and then re-created.

> [!NOTE]
> If a project has an approved budget, and a budget line is already time-phased, you can only extend the budget period's end date. You can't change any other fields for the project. This limitation helps protect the budget period detail lines that have been created. The only way to update the budget period configuration is to create a copy of the project, and then create a new budget and budget period.
>
> The **Budget period interval** can be changed only when the budget is in either the **Draft** state or the **Editable** state. Revise the budget if you want to change the **Budget period interval** to either **Weekly, Monthly, Quarterly**, or **Yearly**.

## Delete a budget period at the project level

To delete a budget period at the project level, follow these steps.

1. Sign in to Project Operations.
1. Go to the **Projects** section in the lower-left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project main page.
1. On the Action Pane, select **Budget**, and then select **Budget Periods** on the dropdown menu.
1. Select **Delete**.
1. Select **Confirm** to delete the budget period configuration.

> [!NOTE]
> Deletion of a budget period stops the time phasing of budget lines to budget line details. If the budget is already in an approved state, time phasing of budget lines won't occur during budget revision.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
