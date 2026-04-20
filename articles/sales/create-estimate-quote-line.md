---
title: Create estimates on a quote line
description: This article provides information about how to create an estimate on a quote line for a project.
author: poojafandan
ms.author: poojafandan
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Create estimates on a quote line

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

On a project-based quote, use the Quote line detail entity to estimate the work required to deliver a project. You can then share that estimate with the customer.

Project-based quote lines don't need any quote line details. Alternatively, they can have many quote line details. Use quote line details to estimate time, expenses, or fees. Dynamics 365 Project Operations doesn't allow for material estimates on quote line details. These estimates are called transaction classes. You can also enter estimated tax amounts on a transaction class.

In addition to transaction classes, quote line details have a transaction type. Two transaction types exist for quote line details: **Cost** and **Project Contract**.

## Estimate by using a contract

If you used a Project Operations quote when you created a project-based contract, the estimate that you created for each quote line on the quote is copied to the project contract. The structure of a project contract is like the structure of project quote that has lines, line details, and invoice schedules.

You can create estimates directly in a project contract, just like in a project quote. For a project quotation, you create the estimate by using contract lines and contract line details. You can also generate contract line details from a project plan that you created by using the bottom-up estimate approach.

Use contract line details to estimate time, expenses, or fees. You can also enter estimated tax amounts on a contract line detail.

Material estimates aren't allowed on contract line details.

The processes that a project contract supports are invoice creation and confirmation. Invoice creation creates a draft of a project-based invoice that includes all unbilled sales actuals up to the current date.

Confirmation makes the contract read-only and changes its status from **Draft** to **Confirmed**. After you take this action, you can't undo it. Because this action is permanent, it's a best practice to keep the contract in a **Draft** status.

The only differences between draft contracts and confirmed contracts are their status and the fact that draft contracts can be edited whereas confirmed contracts can't. You can do invoice creation and tracking actuals on both draft contracts and confirmed contracts.

Change orders aren't supported on contracts or projects.

## Estimating projects

You can estimate time and expenses on projects but not materials or fees.

You generate time estimates when you create a task and identify the attributes of a generic resource that is required to perform the task. You generate time estimates from schedule tasks. You don't create time estimates if you create generic team members outside the context of the schedule.

Enter expense estimates in the grid on the **Estimates** page.

## Understand estimation

Use the following table as a guide for understanding the business logic in the estimation phase.

| Scenario                                                                                                                                                                                                                                                                                                                                          | Entity record                                                                                                                                                                                                       | Transaction Type | Transaction Class | Additional information                                                            |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------|-------------|-----------------------------------------------------------------------------------|
| When you need to estimate the sales value of time on a quote                                                                                                                                                                                                                                                                                    | Quote line detail (QLD) record is created                                                                                                                                                                               | Project contract | Time        | Transaction origin field on the sales side QLD row references the Cost side QLD |
|                                                                                                                                                                                                                                                                                     | A second QLD record is created by the system to store the corresponding cost values. The system copies all non-money fields from the sales QLD to the Cost QLD.                                                                                                                                                                               | Cost | Time        | Transaction origin field on the sales side quote line detail (QLD) row references the Cost side QLD |
| When you need to estimate the sales value of time on a contract                                                                                                                                                                                                                                                                                 | Project contract line detail (CLD) record is created                                                                                                                                                                    | Project Contract | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
|                                                                                                                                                                                                                                                                                  | A second CLD record is created by the system to store the corresponding cost values. The system copies all non-money fields from the sales CLD to the cost CLD.                                                                                                                                                                    | Cost | Time        | Transaction origin field on the sales side CLD row references the cost CLD      |
| When the user describes a resource on a project task                                                                                                                                                                                                                                                                                            | Estimate line record to show the sales value of the task is created when a task is created with all required pricing dimensions. Role and organizational units are the pricing dimensions | Project Contract | Time        |                                                                                   |
|     | The estimate line record to show the cost value of the task is created when a task is created with all required pricing dimensions. The system copies all non-money fields from the sales estimate line to the cost estimate line. Role and organizational unit are the pricing dimensions for both cost and bill rates.                                                                                                                                                                                                                | Cost             | Time           |                                                                                   |

## Customize the Quote line detail and Contract line detail entities

If you add a custom field on the quote line detail and want the system to enter the value of the field as a default value on the related cost line that it creates, use the PreOperationContractLineDetailUpdate and PreOperationQuoteLineDetailUpdate plug-in registration tools. You must re-register these plug-ins after the quote line detail or the contract line detail is changed. Follow these steps to complete the process.

1. Open PluginRegistrationTool, and connect to your online instance.
1. Select **Search**, and search for the plug-in to update.
1. Select the plug-in, and then, on the main page, select **Select**.
1. Select the step of the plug-in to update, right-click, and then select **Update**.
1. In the **Update Existing Step** dialog box, in the **Filtering Attributes** field, select the ellipsis button (**...**):
1. In the **Select Attributes** dialog box, select check boxes for custom attributes.
1. Select **OK** to close the dialog box, and then select **Update Step**.
1. Repeat steps 1 through 7 for the second plug-in.
1. Close the PluginRegistrationTool.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
