---
title: Define expense policies
description: Learn how to define expense policies that enforce limits, require justifications, or issue warnings for expense reports and travel requisitions.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Define expense policies

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core._

You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions. Implementing expense policies can help you manage expenses effectively.

For example, you can set a policy for hotel expenses in New York City, which states that the per night expense can't exceed USD 250. If a worker submits an expense report or travel requisition where the room rate exceeds this amount, the system notifies the worker that the policy amount for the expense has been exceeded. You can configure the message that the worker receives when you define the policy.
  
You can define three types of policies:
  
- **Warning**: Allows the worker to submit an expense report or travel requisition but the expense is marked for all approvers and for later reporting.

- **Error**: Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.

- **Justification**: Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.

## Policy tips

Here are a few suggestions that can assist you when creating new policies for expense management:

- Policies are date effective, which means a policy doesn't take effect if you create it with a date after the date that the expense occurred. For example, you create a new policy today to enforce a maximum meal expense of $50. Any existing expenses entered as of yesterday aren't checked against this policy.
- When creating a policy for an expense category that you can itemize, consider adding a condition for expense line type. Some policies, such as requiring a receipt, might not make sense for itemized lines. In this situation, the policy only applies to the header line or a nonitemized line.
- By default, the system evaluates expense management policies against the source entity. For intercompany scenarios, you can set the policy to evaluate the destination entity (borrowing entity) instead. To run the policies against the destination entity, turn on the **Evaluate Expense policy against borrowing legal entity** feature in the **Feature Management** workspace.

## When to evaluate policies

In expense management parameters, you can select to evaluate expense management policies when a line is saved or when an expense report is submitted. If you choose to evaluate policies when a line is saved, users see earlier what they need to do to complete their expense report all at once. Otherwise, you can delay policy evaluation and save time by validating at the end, during the submission to workflow.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
