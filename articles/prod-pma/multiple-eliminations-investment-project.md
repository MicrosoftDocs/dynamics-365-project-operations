 ---
 title: Enable multiple eliminations for an investment project
 description: Learn how to enable and use the multiple eliminations feature for investment projects in Dynamics 365 Project Operations.
 author: [author-placeholder]
 ms.author: mukumarm
 ms.date: 05/30/2026
 ms.topic: how-to
 ms.custom: bap-template
 ms.reviewer: johnmichalak
 audience: Application User
 ms.search.form: ProjParameters, ProjTable, ProjTransElimination
 ms.search.region: Global
 ---
 
# Enable multiple eliminations for an investment project
 
**Applies to:** Project Operations for resource/non-stocked based scenarios, Project Operations for stocked/production-based scenarios
 
## Overview
 
In Dynamics 365 Project Operations, **Investment projects** track costs that are capitalized rather than expensed immediately. *Elimination* is the 
accounting process that reverses or removes capitalized costs from an investment project, transferring value to the associated fixed asset or ledger 
account.
 
By default, only a **single** elimination transaction is permitted per investment project. The **Enable multiple eliminations for investment project** 
feature removes this restriction, allowing finance and project accountants to post **multiple elimination transactions** against a single investment 
project — supporting staged capitalization, cost overruns, and partial expense scenarios.
 
## Key business scenarios
 
| Scenario | How this feature helps |
|---|---|
| **Staged asset capitalization** | Eliminate costs phase-by-phase as each wing/section is placed in service |
| **Cost overruns & scope changes** | Post a second elimination for incremental approved costs without reversing the original |
| **Partial capitalization** | Eliminate only qualifying cost components; leave ineligible costs for expense recognition |
| **Audit & compliance** | Single project number with per-voucher audit trail supports reconciliation |

> [!IMPORTANT]
> This feature changes elimination posting behavior. Review your organization's capitalization policy before enabling in production.

## Prerequisites
  
  1.  Enable the feature **Enable multiple eliminations for investment project**.
  2.  **Dynamics 365 Finance version 10.0.49**
 
## Project management and accounting parameters.


## Perform multiple eliminations
To Perform elimination process, genearte elimination proposal by following below steps:
 
1. Go to **Project management and accounting> Projects> All projects** and open your investment project.
2. Go to **Manage** Action pane, Select **Revenue recogntion**.
3. Generate **Revenue recogntion** for the period and Click **Post**.
4. Go to **Project management and accounting > Investment Projects > Elimination Proposal** or **Renveue recogntion > Click Elimination Proposal**.
5. Click **+New** to create the elimination proposal.
6. Select the **Revenue recognition project**, **elimination date** and Click **Ok**.
7. In the **Tranactions** tab, View the list of **transactions** available for the elimination process. All transactions that are not yet eliminated but have already undergone revenue recognition can be considered for estimation purposes.
8. Use **Add** or **Delete** button to add or remove the transactions from the elimination proposal.
9. In the **Elimination accounts** tab, enter the ledger account or fixed asset or other project and distribute the total amount to the selected accounts.
10. Click **Post** to post the **elimination proposal**.
     
### Repeat as needed
Repeat Steps 1–9 for each subsequent capitalization stage. Each transaction gets its own voucher and audit trail.
 
### Eliminate the project (optional)
Once all costs are eliminated, select the Eliminate option while posting the elimination proposal. The following validations are performed during the posting process when the Eliminate option is selected:
1.  All cost transactions must be fully eliminated.
2.  Revenue recognition must be completed and posted.
3.  No pending elimination transactions.
  
## Reverse eliminations
**Reverse elimination** is required to **undo** previously posted elimination entries when changes occur after the elimination process has been completed. 

To reverse the elmination proposal, follow below steps:

1.  Go to **Project management and accounting > Investment projects > Elimination proposal**.
2.  Select the elmination proposal with **posted** status.
3.  Click "Reverse" to reverse the elimination proposal. All transactions reversed through this process are available for use in future elimination cycles.

 > [!Note]
 > **Do not disable** this feature after use in production — it restricts future eliminations on already-affected projects.
 
