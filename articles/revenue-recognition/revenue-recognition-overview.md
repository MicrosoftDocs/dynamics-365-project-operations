---
title: Revenue recognition overview
description: This article provides information about revenue recognition in Project Operations.
author: sigitac
ms.date: 10/27/2023
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: sigitac

---

# Revenue recognition overview

_**Applies To:** Project Operations Integrated with ERP_
 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.
In Dynamics 365 Project Operations, revenue recognition principles vary based on the selected billing method for a project or portion of the project. This article provides information about revenue recognition in Project Operations.

## Transactions accounted using time and material billing method

- Cost and revenue recognition are connected. Transaction cost and unbilled sales are posted using the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md).
- Project cost and revenue profile determine if unbilled sales transactions are posted to the general ledger. If **Accrue revenue** is selected, the system uses the **WIP sales value** and the **Accrued revenue sales value** accounts during posting. The following is an example of this method.  

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | WIP Sales value | Debit | 100 |
  | Accrued revenue sales value | Credit | 100 |

- Revenue is recognized during invoicing. The system uses the **Invoiced revenue** account during posting. The following is an example of this method.  

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | Customer balance | Debit | 120 |
  | Sales tax payable | Credit | 20 |
  | Invoiced Revenue | Credit | 100 |

- If revenue was accrued when the unbilled sales are posted, the system will reverse the accrued revenue at invoicing.

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | WIP Sales value | Credit | 100 |
  | Accrued revenue sales value | Debit | 100 |

## Transactions accounted using the fixed price billing method

- Cost and revenue recognition are separate. Transaction cost is posted using the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md). Unbilled sales transactions aren't created.
- Revenue can be recognized during invoicing if the project cost and revenue profile have **Principle used for project completion calculations** set to **No WIP**. Only use this method for short term, simple projects.
- Revenue can be recognized using fixed price revenue estimates, with either the **Completed contract** or **Percent completion revenue recognition** method.

## Additional resources
[Configure accounting for billable projects article](../project-accounting/configure-accounting-billable-projects.md)

[Fixed price revenue estimate projects](rev-rec-percentage-completion-method.md)

[Manage revenue estimates](rev-rec-completed-contract-method.md)

[Cost to complete methods](cost-complete-methods.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]