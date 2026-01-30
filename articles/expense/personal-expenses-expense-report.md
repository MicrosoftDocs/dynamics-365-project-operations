---
title: Work with personal expenses on an expense report
description: This article provides information about how to work with personal expenses incurred by employees while traveling for business purposes.
author:  mukumarm
ms.date: 05/24/2024
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---


# Work with personal expenses on an expense report

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

During business travel, an employee might charge personal expenses to their corporate credit card. If a process hasn't been defined for handling personal expenses, the expense report approval process might be disrupted when an employee submits their itemized expense report.

There are two methods you can use to work with an employee's personal expenses:

  - **Paid by employee**: Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card. Instead, the employee pays the credit card vendor directly for the expenses. 
  - **Paid by company**: Your organization pays the full bill for the corporate credit card, and then debits the worker's account for the personal expenses.

You can select the method that your organization uses on the **Expense management parameters** page.


## Enable split expense function when personal amount field has value defined

The feature, **Enable split expense function when personal amount field has value defined** only applies to expense reports that are approved using a line-level workflow. Reports are approved by going to **Process expense reports** > **Expense reports assigned to me** > **Open expense report**. 

To enable this feature, go to **Workspaces** > **Feature Management**, select **Enable split expense function when personal amount field has value defined**, and then select **Enable now**. 

When the feature is enabled, expense lines that use this functionality generate two lines when the report is submitted. Two lines are generated so that the approver can approve each line separately.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
