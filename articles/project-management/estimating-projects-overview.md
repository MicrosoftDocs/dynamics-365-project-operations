---
# required metadata
title: Financial estimation on projects 
description: This topic provides information about financial estimation of projects in Dynamics 365 Project Operations. 
author: ruhercul
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend
ms.author: rumant
---

# Financial estimation on projects 

_**Applies To:** Project Operations for resource/non-stocked based scenarios, Lite deployment - deal to proforma invoicing_

Project Operations allows for financially estimating your projects in 2 stages:
1. During the Pre-sales stage before the deal is won 
2. During the execution stage once the Project Contract is created. 

Creating a financial estimate for project-based work can be done using any of the following 3 pages
1. On each Quote line page, using the Quote line details  
2. On each Project contract line page, using the Contract line details 
3. On the Project, using the Tasks  or the Expense Estimates tab pages

## Estimation using a Project Quote 
On a project-based quote, you can use the **Quote line detail** entity to estimate the work that is required to deliver a project. You can then share that estimate with the customer.

Project-based quote lines can have zero to many quote line details. Quote line details are used to estimate time, expenses, or fees. Microsoft Dynamics 365 Project Operations doesn't allow for material estimates on quote line details. These are called transaction classes. Estimated tax amounts can also be entered on a transaction class.

In addition to transaction classes, quote line details have a transaction type. Two transaction types are supported for quote line details: **Cost** and **Project Contract**.

## Estimation using a Project contract

If you used a quote when you created a project-based contract, the estimate that you did for each quote line on the quote is copied to the project contract. The structure of a project contract is like the structure of project quote that has lines, line details, and invoice schedules.

Estimates can be done directly in a project contract, as in a project quote. For a project quotation, the estimate is done by using contract lines and contract line details. Contract line details can also be generated from a project plan that was created by using the bottom-up estimate approach.

Contract line details can be used to estimate time, expenses, or fees. Estimated tax amounts can also be entered on a contract line detail.

Material estimates are not allowed on contract line details.

## Estimation using a Project 

You can estimate time and expenses on projects. Project operations doesn't allow estimates of materials or fees on projects.

Time estimates are generated when you create a task and identify the attributes of a generic resource that is required to perform the task. Time estimates are generated from schedule tasks. Time estimates aren't created if you create generic team members outside the context of the schedule.

Expense estimates are entered in the grid on the **Expense Estimates** page.

Estimating on project is generally recommended as a best practice since you can build a bottom-up detailed estimation for both Labor or Time and Expenses on each Task in the Project plan. This detailed estimation can then be used to create the estimation for each Quote line to help build a more credible Quote for the customer. When you import or create a detailed estimate on the each Quote line using  the Project plan, PRoject Operations not only imports the sales values but also the cost values of these estimates and therefore you will be able see Profitability, margins, feasibility metrics on the Project Quote.

## Understanding estimation

Use the following table as a guide for understanding the business logic in the estimation phase.

| Scenario                                                                                                                                                                                                                                                                                                                                          | Entity record                                                                                                                                                                                                       | Transaction Type | Transaction Class | Additional information                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|-------------|-----------------------------------------------------------------------------------|
| When you need to estimate the sales value of time on a quote                                                                                                                                                                                                                                                                                    | Quote line detail (QLD) record is created                                                                                                                                                                               | Project contract | Time        | Transaction origin field on the sales side QLD row references the Cost side QLD |
|                                                                                                                                                                                                                                                                                     | A second QLD record is created by the system to store the corresponding cost values. All non-money fields are copied from the sales QLD to the Cost QLD by the system.                                                                                                                                                                               | Cost | Time        | Transaction origin field on the sales side quote line detail (QLD) row references the Cost side QLD |
| When you need to estimate the sales value of time on a contract                                                                                                                                                                                                                                                                                 | Project contract line detail (CLD) record is created                                                                                                                                                                    | Project Contract | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
|                                                                                                                                                                                                                                                                                  | A second CLD record is created by the system to store the corresponding cost values. All non-money fields are copied from the sales CLD to the cost CLD by the system.                                                                                                                                                                    | Cost | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
| When the user describes a resource on a project task                                                                                                                                                                                                                                                                                            | Estimate line record to show the sales value of the task is created when a task is created with all required pricing dimensions. Role and organizational units are the pricing dimensions | Project Contract | Time        |                                                                                   |
|     | The estimate line record to show the cost value of the task is created when a task is created with all required pricing dimensions. All non-money fields are copied from the sales estimate line to the cost estimate line by the system. Role and organizational unit are the pricing dimensions for both cost and bill rates.                                                                                                                                                                                                                | Cost             | Time           |                                                                                   |



## Customize the Quote line detail and Contract line detail entities

If you added a custom field on the quote line detail and want the system to enter the value of the field as a default value on the related cost line that it creates, use the **PreOperationContractLineDetailUpdate** and **PreOperationQuoteLineDetailUpdate** plug-in registration tools. These plug-ins must be re-registered after the quote line detail or the contract line detail is changed. Follow these steps to complete the process.

1. Open PluginRegistrationTool, and connect to your online instance.
2. Select **Search**, and search for the plug-in to update.
3. Select the plug-in, and then, on the main page, click **Select**.
4. Select the step of the plug-in to update, right-click, and then select **Update**.
5. In the **Update Existing Step** dialog box, in the **Filtering Attributes** field, select the ellipsis button (**...**):
6. In the **Select Attributes** dialog box, select check boxes for custom attributes.
7. Select **OK** to close the dialog box, and then select **Update Step**.
8. Repeat steps 1 through 7 for the second plug-in.
9. Close the **PluginRegistrationTool**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
