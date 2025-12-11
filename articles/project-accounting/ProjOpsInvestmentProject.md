---
title: Enable Investment Projects in Dynamics 365 Project operations integrated with ERP
description: This topic provides information about the accounting options for billable projects.
author: mukumarm
ms.date: 12/12/2025
ms.topic: article
ms.reviewer: johnmichalak 
ms.author: mukumarm
---

# Enable Investment Projects in Dynamics 365 Project operations

_**Applies To:** Project Operations integrated with ERP_

Investment projects in integrated deployments (Dynamics 365 Project Operations + Finance) enable organizations to track, 
capitalize, and manage costs for internal initiatives—such as infrastructure development or R&D—that result in long-term assets. 
The integrated approach ensures seamless data flow, compliance, and accurate financial treatment across project and ERP systems.

## Prerequisites
To use the functionality, in Dataverse, activate the **Enable investment project for Project Operations integrated with ERP.** feature.

### Minimum versions required
To use the feature for **Dynamics 365 Project Operations integrated with ERP scenarios**, you must have the following versions:

- **Project Operations Dataverse** version 4.162.0.X or later
- **Dynamics 365 Finance** version 10.0.47 or later

### Dual-write maps

| Required dual-write map | Required version | Initial synchronization |
|---|---|---|
| Projects V2 (msdyn_projects) | 1.0.0.4 | Not applicable |

## Investment project
Users can create projects and designate them as investment projects in **Dynamics 365 Project operations**. This classification differentiates investment projects from other types (fixed price, time & material) and triggers specific system behaviors.
Once a project is designated as an investment project, it cannot be linked to or used for **project quotations** or **project contracts**. You may change the project type only if no actual transactions have been generated for the project. 
After any transactions are processed, the project type becomes locked and cannot be changed.

When an **investment project** is created in **Dynamics 365 Project Operations**, a corresponding project is automatically created in **Dynamics 365 Finance** and marked as an investment project. For each investment project in Dynamics 365 Finance, a dedicated **revenue recognition project** is also established.
This dual-project setup is essential for processing financials related to the investment initiative. The revenue recognition project enables the system to:

* Acquire the fixed asset associated with the investment project, or
* Move the accumulated Work In Progress (WIP) costs to the appropriate ledger accounts as part of the revenue recognition and elimination process.

To create an investment project in Dynamics 365 Project operations, do the following:
1.  Go to **Dynamics 365 Project Operations** > **Projects** > **Projects**.
2.  Click **+ New Project** to create a new project.
3.  Enter Name, Description, Owning Company and set **Investment Project** to **Yes**.
4.  Click Save to save the project. 

To review the **Investment project** and **Revenue recognition project** in **Dynamics 365 Finance**, do the following.
1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All projects**.
2. Lookup for the project created in **Dynamics 365 Project Operations**.
3. This project is marked as an **Investment project**.
4. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All reveneue recognition projects**.
5. A new revenue recogntion project is created with the same Project id.
6. Click on the Revenue project id and and verify that **Investment project** is associated with **Revenue recogntion project**.

Once the investment project is created in **Dynamics 365 Project operations**, you can define the Work Breakdown Structure (WBS) and enter project estimates. 
These estimates are automatically synchronized with Dynamics 365 Finance as project forecasts, ensuring alignment between project planning and financial management.

## Accounting
Once the project is created, users can enter and process timesheets, expenses, material usage, or purchase orders to record project cost actuals. 
These actual costs are transferred to Dynamics 365 Finance, where financial postings are made and the project subledger is generated.

### Project cost and revenue profile
**Project cost and revenue profiles** define the financial framework for how project costs, sales, and revenue recognition transactions are managed. 
To support financial management for investment projects, a new **accounting method** called **Investment** has been introduced as part of this feature. 
This method enables accurate tracking and posting of costs and revenues specific to investment projects, 
ensuring compliance with capitalization and financial reporting requirements.

To create an **Cost and revenue profile** for the Investment project in **Dynamics 365 Finance**, do the following:
1.  Go to **Dynamics 365 Finance** > **Project management and accounting** > **Setup** > **Posting** > **Project cost and revenue profile**.
2.  Click **+New** to create a new Project cost and revenue profile.
3.  Enter the profile id, name and choose **Accounting method** as **Investment**.
4.  Set the ledger setup for hour, expense, item and other type of tranactions.
5.  Select the **Cost template and period code** for revenue recogntion process.

### Project cost and revenue profile rules
**Project cost and revenue profile rules** define how projects are associated with specific **cost and revenue profiles**. 
You can assign a cost and revenue profile to an individual project, a group of projects, or apply it across all projects. 
This configuration ensures consistent financial treatment and reporting for project costs and revenue recognition.

To create an **Project cost and revenue profile rule** for the Investment project in **Dynamics 365 Finance**, do the following:
1.  Go to **Dynamics 365 Finance** > **Project management and accounting** > **Setup** > **Posting** > **Project cost and revenue profile rules**.
2.  Click **+New** to create a new Project cost and revenue profile rules.
3.  Select the **Accounting method** as **Investment**, Select project relation and choose **Project cost and revenue profile**.

### Revenue recogntion
The revenue recognition project linked to an investment project is used to execute periodic processes that assess the percentage of completion and transfer costs from the Profit and Loss account to the Balance Sheet (Work in Progress accounts). 
For revenue recognition, you can configure whether the project’s **work in progress costs** are transferred to a **ledger account** or to a **fixed asset** as part of the **elimination** process.

#### Periodic process
To link the **revenue recogntion project** with a **ledger account** or **fixed asset** during an elimination, do the following:

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All reveneue recognition projects**.
2. Click on the Revenue project id and and verify that **Investment project** is associated with **Revenue recogntion project**.
3. Click **Revenue recognition** and **+New** to create the snapshot for the period.
4. You can validate the percentage of completion till the period selected.
5. Go to **General** tab, Choose **Eliminate to** as **Ledger** or **Fixed asset**.
6. Click **Post** to generate financials for all the transactions used for the revenue recogntion process.

As part of this process, any transactions previously posted to Profit and Loss accounts are reclassified and moved to Balance Sheet (Work in Progress) accounts. This ensures accurate financial representation of project costs during the asset capitalization or elimination phase. 

#### Eliminate the project
Once all costs are posted to the project subledger and the project is ready to be closed, run the **revenue recognition elimination** process. 
This process transfers project costs from Balance Sheet (Work in Progress) accounts to the appropriate ledger or fixed asset account, ensuring accurate financial closure and asset capitalization.

To execute the **Revenue recognition elimination process**, do the following:
1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All reveneue recognition projects**.
2. Click on the Revenue project id and and verify that **Investment project** is associated with **Revenue recogntion project**.
3. Click **Revenue recognition** and choose **Cost to complete method** as **Set cost to complete to zero**.
4. Validate the WIP, profit & loss details and project snapshot.
5. Click **Eliminate** to the close the revenue recognition project. This step transfers project costs from **Balance Sheet (Work in Progress)** accounts to the appropriate **Ledger** or **Fixed asset** selected during first execution of revenue recogntion.
 

