---
title: Set up a Budget period
description: This article explains how to set up the budget period at an organization level and also at a project level. A budget period is a prerequisite for time phasing.
author: niranjanmaski
ms.date: 08/25/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Set up a Budget period

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to set up a budget period, both at an organizational level and at a project level. 

> [!NOTE]
> A budget period mandatory at the project level to enable the time phasing of budgeted values and quantities over the budget line's time period.

## What is Budget period

Budget period defines a week, month, quarter, and fiscal periods in your organization. 

For example, in some countries, fiscal and quarter one starts on the first day in April.  In other countries, the fiscal and quarter one starts the first day in January. Work week may start on Monday, or for some may start on Sunday. A budget period defines fiscal, quarter, month, and week starts at an organization level or at project level.

A budget period that is set up at an organization level is available for consumption at a project level. However, based on a specific project's needs, a project manager can override the organization budget period setup at a project level to cater to a specific project's needs. 

## Set up a budget period at an Organization level

To set up or edit a budget period at an organization level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Settings** section in the bottom left navigation.
1. From the **General** category, select **Organizational Units**.
1. Find and select the desired organizational unit to open the main page.
1. Select the **Budget Period** tab. If there's no existing budget period in the grid, select **+ New Budget Period** to create one.
1. Select **Save & Close**. A budget period line is created in the grid.
1. To view or modify the budget period details, double-click on the budget period line.
1. Make any necessary updates, and select **Save** or **Save & Close** in the top ribbon bar. Depending on your configuration updates, the budget period detail line is extended or deleted and created again.

Refer to the following table for details of the fields.

| Field | Requirement | Description | Comments |
|---|---|---|--|
| Name | Optional | The name of the budget period. | Give a name of your choice to identify the budget period. |
| Fiscal start | Mandatory | Specifies the month when the fiscal year begins. <p>This month is also considered the quarter one start for the budget period. </p>  <p> For example, if the fiscal start is January, then quarter one is January through March. </p>| Updates to this field delete and create budget period details. |
| Week starts on | Mandatory | Specifies the day of the week that the workweek starts. <p> The first occurrence of that weekday in the month is considered the start of the month.</p> <p> For example, if **Week starts on** is set to Monday, the first Monday of a month is considered the start of the month for period calculation. </p>  | Updates to this field delete and create budget period details. |
| Start year | Mandatory | Specifies the calendar year from which the budget period creation commences. <p> For example, if the **Start year** is 2023, the budget period starts on the Year and month of Start year and Start month.  | Updates to this field extend the budget period details. |
| Start month | Mandatory | Defines the month of the calendar year from when the budget period creation starts. <p> For example, if the **Start year** is 2023 and the **Start month** is July, the budget period starts July of 2023. | Updates to this field extend the budget period details. |
| End year | Mandatory | Specifies the calendar year up to which the budget period is created. <p> For example, if the **Start year** is 2023, the budget period starts on the Year and month of Start year and Start month.  | Updates to this field extend the budget period details. |
| End month | Mandatory | Specifies the month up to which the budget period is created. <p> For example, if the **End year** is 2033 and **End month** is June, the budget period ends at last week of June 2033. </p>  | Updates to this field extend the budget period details. |

> [!NOTE]
> A budget period that is set up at the organization level serves as a template that can be easily copied and applied at the project level for your specific needs. This approach streamlines the process of setting up budget periods for individual projects, and ensures consistency and efficiency across different projects within the organization. 

## Set up a budget period at a project level

To set up a budget period at a project level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project's main page.
1. Select **Budget**, and then from the drop-down menu select **Create budget period**.

The budget period configuration dialog for the selected project opens. If an organization budget period configuration is set up, the **Fiscal start** and **Week starts on** is taken from the organization budget period. Otherwise, they default to July and Monday. The **Start year** and **Start month** is defaulted to the project's start year and month. The **End year** and **End month** is defaulted to the project's end year and month.

You can edit the budget period configuration at the project level to meet your specific needs. You can edit the budget period config at the project level as per your needs.

Refer to the following table for details of the fields.

> [!NOTE]
> After copying the budget period to the project level, any subsequent changes to the organization-level configuration won't affect the project level. The project's budget period becomes independent and isolated from the organization-level template.


| Field | Requirement | Description | Comments |
|---|---|---|--|
| Name | Optional | The name of the budget period. | Give a name of your choice to identify the budget period. |
| Fiscal start | Mandatory | Specifies the month when the fiscal year begins. <p>This month is also considered the quarter one start for budget period. </p>  <p> For example, if the fiscal start is January, the quarter one is January through March. </p>| Updates to this field delete and create budget period details. |
| Week starts on | Mandatory | Specifies the day of the week when the workweek starts. <p> The first occurrence of that weekday in the month is considered the start of the month.</p> <p> For example, if **Week starts on** is set to Monday, the first Monday of a month is considered the start of the month for period calculation. </p>  | Updates to this field delete and create budget period details. |
| Start year | Mandatory | Specifies the calendar year from which the budget period creation commences. <p> For example, if the **Start year** is 2023, the budget period starts on the year and month of the **Start year** and **Start month**. | Updates to this field extend the budget period details. |
| Start month | Mandatory | Defines the month of the calendar year from when the budget period creation starts. <p> For example, if the **Start year** is 2023 and the **Start month** is July, the budget period starts July of 2023. </p>  | Updates to this field extend the budget period details. |
| End year | Mandatory | Specifies the calendar year up to which the budget period is created. <p> For example, if the **Start year** is 2023, the budget period starts on the year and month of the **Start year** and **Start month**.  | Updates to this field extend the budget period details. |
| End month | Mandatory | Specifies the month up to which the budget period is created. <p> For example, if **End year** is 2033 and **End month** is June, the budget period ends the last week of June 2033. </p>  | Updates to this field extend the budget period details. |


## Edit a budget period at a project level

To edit a budget period at a project level after it's created, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project's main page.
1. In the top ribbon bar, select **Budget**, and then choose **Budget Periods** from the drop-down menu.
1. Select **Edit**. 
1. Select **Save** or **Save & Close**.

Depending on your updates, the budget period detail line is extended or deleted and created again.

> [!NOTE]
> If a project has an approved budget and budget line is already time-phased, you can only extend the budget period end date. You cannot change any other field for this project to protect the budget period detail lines created. If its a must to update the budget period configuration the only way is to create a copy of the project and create a new budget and budget period.
   


## Delete budget period at a project level

To delete a budget period at a project level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left navigation.
1. Select **Projects** to view the list of active projects.
1. Find and select the desired project to open the project's main page.
1. In the top ribbon bar, select **Budget**, and then choose **Budget Periods** from the drop-down menu.
1. Select **Delete**.
2. Select **Confirm** to delete the budget period configuration.
   
> [!NOTE]
> Deleting the budget period halts the time phasing of budget lines to budget line details. If the budget is already in an approved state, time phasing of budget lines will not occur during budget revision.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

