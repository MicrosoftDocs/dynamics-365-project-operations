---
title: Budget period setup
description: This article explains how to setup the budget period at an organization level and also at a project level. Budget period setup is a pre-requisite for time phasing.
author: niranjanmaski
ms.date: 25/08/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: nimaski
---

# Budget period setup

**_Applies to:_** _Lite deployment - deal to proforma invoicing._

This article explains how to setup a budget period setup, both at an organization level and also at a project level. 

> [!NOTE]
> Budget period setup is mandatory at the project level to enable the time phasing of budgeted values and quantities over the budget line's period.

## What is Budget period

Budget period would define how you would define the week, month, quarter and fiscal periods in your organization. 

For example, in some countries fiscal and quarter 1 would start on 01st of April and in some countries it would start on 1st of January. In some countries a work week would start on Monday and in some it would start on Sunday. Budget period config would define these at an organization level or at project level.

Budget period setup at organization level would be available for consumption at a project level. However based on a specific project needs a project manager can override the organization budget period config at a project level, to cater to a specific project needs. 

## Budget period setup at an Organization level

To setup or edit a budget period at an organization level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Settings** section in the bottom left-hand navigation.
1. Under the **General** category, select **Organizational Units**.
1. You will see a list of active organizational units.
1. Find and click on the desired organizational unit to open the main form.
1. Once the main form opens, go to the **Budget Period** tab.
1. If there is no existing budget period in the grid, click on **+ New Budget Period** to create one.
1. Save your changes by clicking Save & Close.
1. You will now have a budget period line created in the grid.
1. To view or modify the budget period details, double-click on the budget period line.
1. Make any necessary updates and save the changes by clicking **Save** or **Save & Close** in the top ribbon bar.
1. Depending on your configuration updates, the budget period detail line will be extended or deleted and created again.

| Field | Requirement | Description | Comments |
|---|---|---|--|
| Name | Optional | It is the name of the budget period config. | Give a name of your choice to identify the budget period config |
| Fiscal start | Mandatory | Specifies the month when the fiscal year will begin. <p>This month is also considered as a Quarter 1 start for budget period configuration. </p>  <p> For example, if Fiscal start is January, the quarter 1 would be January to March. </p>| An update of this field would delete and create budget period details |
| Week starts on | Mandatory | Specifies the day of the week when the workweek will start. <p> The first occurrence of that weekday in the month will be considered as the start of the month.</p> <p> For example, if Week starts on setting is set to Monday, the first Monday of a month will be considered as the start of the month for period calculation. </p>  | An update of this field would delete and create budget period details |
| Start year | Mandatory | Specifies the calendar year from which the budget period creation will commence. <p> For example, if Start year is 2023, the budget period would start on the Year and month of Start year and Start month </p>  | An update of this field would extend the budget period details. |
| Start month | Mandatory | Defines the month of the calender year from when the budget period creation would start. <p> For example, if Start year is 2023 and Start month is July, the budget period would start from the July month of 2023. </p>  | An update of this field would extend the budget period details. |
| End year | Mandatory | Specifies the calendar year up to which the budget period will be created. <p> For example, if Start year is 2023, the budget period would start on the Year and month of Start year and Start month </p>  | An update of this field would extend the budget period details. |
| End month | Mandatory | Specifies the month up to which the budget period will be created. <p> For example, if End year is 2033 and End month is June, the budget period would end at last week of June 2033. </p>  | An update of this field would extend the budget period details. |

<p></p>
<p></p>

> [!NOTE]
> Budget period setup at the organization level serves as a template that can be easily copied and applied at the project level as per specific needs. This approach streamlines the process of setting up budget periods for individual projects, ensuring consistency and efficiency across different projects within the organization. 

<p></p>

## Budget period setup at a Project level

To setup a budget period at a project level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Find and click on the desired project to open the project main form.
1. In the top ribbon bar click on the **Budget** and then select **Create budget period** from the drop-down menu.
1. The budget period configuration dialog for the selected project will open.
1. If an organization budget period configuration is set up, the **Fiscal start** and **Week starts on** will be taken from the organization budget period template. Otherwise, they will default to July and Monday.
1. The **Start year** and **Start month** will be defaulted to the project's start year and month.
1. The **End year** and **End month** will be defaulted to the project's end year and month.
1. You can edit the budget period configuration at the project level to meet your specific needs.
1. You can edit the budget period config at the project level as per your needs.
1. Refer to the table below for details of the fields.

> [!NOTE]
> After copying the budget period to the project level, any subsequent changes to the organization-level configuration won't affect the project level. The project's budget period becomes independent and isolated from the organization-level template.


| Field | Requirement | Description | Comments |
|---|---|---|--|
| Name | Optional | It is the name of the budget period config. | Give a name of your choice to identify the budget period config |
| Fiscal start | Mandatory | Specifies the month when the fiscal year will begin. <p>This month is also considered as a Quarter 1 start for budget period configuration. </p>  <p> For example, if Fiscal start is January, the quarter 1 would be January to March. </p>| An update of this field would delete and create budget period details |
| Week starts on | Mandatory | Specifies the day of the week when the workweek will start. <p> The first occurrence of that weekday in the month will be considered as the start of the month.</p> <p> For example, if Week starts on setting is set to Monday, the first Monday of a month will be considered as the start of the month for period calculation. </p>  | An update of this field would delete and create budget period details |
| Start year | Mandatory | Specifies the calendar year from which the budget period creation will commence. <p> For example, if Start year is 2023, the budget period would start on the Year and month of Start year and Start month </p>  | An update of this field would extend the budget period details. |
| Start month | Mandatory | Defines the month of the calender year from when the budget period creation would start. <p> For example, if Start year is 2023 and Start month is July, the budget period would start from the July month of 2023. </p>  | An update of this field would extend the budget period details. |
| End year | Mandatory | Specifies the calendar year up to which the budget period will be created. <p> For example, if Start year is 2023, the budget period would start on the Year and month of Start year and Start month </p>  | An update of this field would extend the budget period details. |
| End month | Mandatory | Specifies the month up to which the budget period will be created. <p> For example, if End year is 2033 and End month is June, the budget period would end at last week of June 2033. </p>  | An update of this field would extend the budget period details. |


## Edit Budget period at a Project level

To edit a budget period at a project level once it is created, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Find and click on the desired project to open the project main form.
1. In the top ribbon bar, click on **Budget**, and then choose **Budget Periods** from the drop-down menu.
1. Click on **Edit** to open the budget period configuration dialog.
1. Update the configuration as needed, referring to the details provided in the table above for field information.
1. After making the necessary changes, save the modifications by clicking **Save** or **Save & Close** in the top ribbon bar.
1. Depending on your configuration updates, the budget period detail line will be extended or deleted and created again.

> [!NOTE]
> If a project has an approved budget and budget line is already time-phased, you can only extend the budget period end date. You cannot change any other field for this project to protect the budget period detail lines created. If its a must to update the budget period configuration the only way is to create a copy of the project and create a new budget and budget period.
   


## Delete Budget period at a Project level

To delete a budget period at a project level, follow these steps.

1. Sign in to Microsoft Dynamics 365 Project Operations.
1. Navigate to the **Projects** section in the bottom left-hand navigation.
1. Click on the **Projects** in the left-hand navigation to view the list of active projects.
1. Find and click on the desired project to open the project main form.
1. In the top ribbon bar, click on **Budget**, and then choose **Budget Periods** from the drop-down menu.
1. Click on **Delete** which opens a confirmation dialog.
2. Click on **Confirm** to delete the budget period configuration.
   
> [!NOTE]
> Deleting the budget period configuration will halt the time phasing of budget lines to budget line details. If the budget is already in an approved state, time phasing of budget lines will not occur during budget revision.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

[Microsoft](https://www.microsoft.com)
