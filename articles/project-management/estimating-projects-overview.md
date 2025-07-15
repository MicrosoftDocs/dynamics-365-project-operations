---
title: Financial estimation concepts
description: This article provides information about financial estimates of projects in  Project Operations. 
author: abriccetti
ms.date: 01/09/2025
ms.topic: overview
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
---

# Financial estimation concepts

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

In Dynamics 365 Project Operations, you can financially estimate your projects in two stages: 

1. During the presales stage before the deal is won. 
1. During the execution stage after the project contract is created. 

You can create a financial estimate for project-based work using any of the following three pages:
- The **Quote line** page, using the quote line details.  
- The **Project contract line** page, using the contract line details. 
- The **Project** page, using the **Tasks**  or **Estimates** tab pages.

## Use a project quote to create an estimate
On a project-based quote, you can use the **Quote line detail** entity to estimate the work that is required to deliver a project. You can then share that estimate with the customer.

Project-based quote lines can have zero to many quote line details. Quote line details are used to estimate time, expenses, materials, or fees. These are called transaction classes. Estimated tax amounts can also be entered on a transaction class.

In addition to transaction classes, quote line details have a transaction type. Two transaction types are supported for quote line details: **Cost** and **Project Contract**.

## Use a project contract to create an estimate

If you used a quote when you created a project-based contract, the estimate that you did for each quote line on the quote is copied to the project contract. The structure of a project contract is like the structure of project quote that has lines, line details, and invoice schedules.

Estimates can be done directly in a project contract, as in a project quote. For a project quotation, the estimate is done by using contract lines and contract line details. Contract line details can also be generated from a project plan that was created by using the bottom-up estimate approach.

Contract line details can be used to estimate time, expenses, materials, or fees. Estimated tax amounts can also be entered on a contract line detail.

## Use a project to create an estimate 

You can estimate time, expenses, and materials on projects.

Time estimates are generated when you create a task and identify the attributes of a generic resource that is required to perform the task. Time estimates are generated from schedule tasks. Time estimates aren't created if you create generic team members outside the context of the schedule.

Expense estimates are entered in the **Expense estimates** tab, and material estimates are entered in the **Material Estimates** tab.

Creating an estimate for a project is considered a best practice because you can build bottom-up detailed estimates for labor or time and expenses on each task in the project plan. You can then use this detailed estimate to create estimates for each quote line and build a more credible quote for the customer. When you import or create a detailed estimate on the quote line using the project plan, Project Operations imports the sales values and the cost values of these estimates. After import, you can view the profitability, margins, and feasibility metrics on the project quote.

> [!NOTE]
> **The Project estimate updates feature is now in Preview.**
>
> Once the **Project estimate updates** feature is enabled, it can't be disabled. These updates include label changes at the project level where the original **Estimates** tab shows **Time phased estimates**, and the newly labeled **Estimates** tab is a consolidated view of expense and material estimates. The new grid for expense and material estimates allows easy creation and editing of those estimates.
>
>To enable the **Project estimate updates** feature, follow these steps.
>
>1. Go to **Settings** \> **Parameters**.
>1. Open the **Parameters** record.
>1. On the Action Pane, on the **Feature Control** tab, select **Project estimate updates**.
>1. In the confirmation dialog box, select **OK**.
>1. After a few moments, refresh your browser. The feature capabilities is available, and the feature is removed from the list of features to be enabled. 

## Understanding estimates

Use the following table as a guide for understanding the business logic in the estimate phase.

| Scenario                                                                                                                                                                                                                                                                                                                                          | Entity record                                                                                                                                                                                                       | Transaction Type | Transaction Class | Additional information                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|-------------|-----------------------------------------------------------------------------------|
| When you need to estimate the sales value of time on a quote                                                                                                                                                                                                                                                                                    | Quote line detail (QLD) record is created                                                                                                                                                                               | Project contract | Time        | Transaction origin field on the sales side QLD row references the Cost side QLD |
|                                                                                                                                                                                                                                                                                     | A second QLD record is created by the system to store the corresponding cost values. All nonmoney fields are copied from the sales QLD to the Cost QLD by the system.                                                                                                                                                                               | Cost | Time        | Transaction origin field on the sales side quote line detail (QLD) row references the Cost side QLD |
| When you need to estimate the sales value of time on a contract                                                                                                                                                                                                                                                                                 | Project contract line detail (CLD) record is created                                                                                                                                                                    | Project Contract | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
|                                                                                                                                                                                                                                                                                  | A second CLD record is created by the system to store the corresponding cost values. All nonmoney fields are copied from the sales CLD to the cost CLD by the system.                                                                                                                                                                    | Cost | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
| When the user describes a resource on a project task                                                                                                                                                                                                                                                                                            | Estimate line record to show the sales value of the task is created when a task is created with all required pricing dimensions. Role and organizational units are the pricing dimensions | Project Contract | Time        |                                                                                   |
|     | The estimate line record to show the cost value of the task is created when a task is created with all required pricing dimensions. All nonmoney fields are copied from the sales estimate line to the cost estimate line by the system. Role and organizational unit are the pricing dimensions for both cost and bill rates.                                                                                                                                                                                                                | Cost             | Time           |                                                                                   |



## Customize the Quote line detail and Contract line detail entities

If you added a custom field on the quote line detail and want the system to enter the value of the field as a default value on the related cost line that it creates, use the **PreOperationContractLineDetailUpdate** and **PreOperationQuoteLineDetailUpdate** plug-in registration tools. These plug-ins must be re-registered after the quote line detail or the contract line detail is changed. Follow these steps to complete the process.

1. Open PluginRegistrationTool, and connect to your online instance.
1. Select **Search**, and search for the plug-in to update.
1. Select the plug-in, and then, on the main page, click **Select**.
1. Select the step of the plug-in to update, right-click, and then select **Update**.
1. In the **Update Existing Step** dialog box, in the **Filtering Attributes** field, select the ellipsis button (**...**):
1. In the **Select Attributes** dialog box, select check boxes for custom attributes.
1. Select **OK** to close the dialog box, and then select **Update Step**.
1. Repeat steps 1 through 7 for the second plug-in.
1. Close the **PluginRegistrationTool**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
