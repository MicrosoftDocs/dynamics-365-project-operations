---
title: Revenue recognition overview
description: Learn how revenue recognition works in Dynamics 365 Project Operations, including time and material billing, fixed price methods, and accounting principles.
author: sigitac
ms.date: 01/30/2026
ms.topic: overview
ms.reviewer: johnmichalak
ms.author: sigitac

---

# Revenue recognition overview

[!include[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_
 > [!NOTE]
   > In a recent product update, the **Update labels for revenue recognition and related forms and processes in Project Operations** feature renamed estimates to revenue recognition. Depending on whether the feature is enabled, terminology might reference either estimate or revenue recognition.
In Dynamics 365 Project Operations, revenue recognition principles vary based on the selected billing method for a project or portion of the project. This article provides information about revenue recognition in Project Operations.

## Transactions accounted using time and material billing method

- Cost and revenue recognition are connected. Use the [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md) to post transaction cost and unbilled sales.
- The project cost and revenue profile determines if unbilled sales transactions go to the general ledger. If you select **Accrue revenue**, the system uses the **WIP sales value** and the **Accrued revenue sales value** accounts during posting. The following example shows this method.  

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | WIP Sales value | Debit | 100 |
  | Accrued revenue sales value | Credit | 100 |

- Revenue is recognized during invoicing. The system uses the **Invoiced revenue** account during posting. The following example shows this method.  

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | Customer balance | Debit | 120 |
  | Sales tax payable | Credit | 20 |
  | Invoiced Revenue | Credit | 100 |

- If you accrued revenue when you posted the unbilled sales, the system reverses the accrued revenue at invoicing.

  | Transaction type | Debit/Credit | Amount |
  | --- | --- | --- |
  | WIP Sales value | Credit | 100 |
  | Accrued revenue sales value | Debit | 100 |

## Transactions accounted by using the fixed price billing method

- Cost and revenue recognition are separate. The [Project Operations Integration journal](../project-accounting/project-operations-integration-journal.md) posts the transaction cost. The process doesn't create unbilled sales transactions.
- You can recognize revenue during invoicing if the project cost and revenue profile have **Principle used for project completion calculations** set to **No WIP**. Only use this method for short term, simple projects.
- You can recognize revenue by using fixed price revenue estimates, with either the **Completed contract** or **Percent completion revenue recognition** method.

## Additional resources

[Configure accounting for billable projects article](../project-accounting/configure-accounting-billable-projects.md)

[Fixed price revenue estimate projects](rev-rec-percentage-completion-method.md)

[Manage revenue estimates](rev-rec-completed-contract-method.md)

[Cost to complete methods](cost-complete-methods.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
