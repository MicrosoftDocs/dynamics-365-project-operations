---
title: Expense reports and multiple approvers
description: Learn how to set up workflows for expense reports requiring multiple approvers. Ensure compliance with approval policies using step-by-step guidance.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Expense reports and multiple approvers

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Depending on your organization's expense approval policies, more than one person might need to approve a submitted expense report. When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers. For example, you might require that all expense reports be approved by two separate people, the manager of the employee who submitted the report and the Accounts payable coordinator.

If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:

- Add one approval element that has one step. For example, the step might require that an expense report be assigned to a user group, and that 50 percent of the user group's members approve it.
- Add one approval element that has multiple steps. For example, the approval element might have the following steps:

    1. The manager of the employee who submitted the expense report approves it.
    1. The Accounts payable clerk verifies the receipts and the expense report items.
    1. The budget owner approves the expense report.

- Add multiple approval elements, each of which has one step. For example, you might add a separate approval element for each of the following steps:

    1. The employee's manager approves the expense report.
    1. The budget owner approves the expense report.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
