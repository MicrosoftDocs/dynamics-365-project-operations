---
title: Investment Projects in Dynamics 365 Project operations integrated with ERP
description: This article provides guidance on how to manage investment projects within Dynamics 365 Project Operations when integrated with ERP systems. 
author: mukumarm
ms.date: 12/11/2025
ms.topic: article
ms.reviewer: johnmichalak 
ms.author: mukumarm
---

# Enable investment projects in Dynamics 365 Project operations

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations integrated with ERP_

When you enable investment projects in **Dynamics 365 Project Operations** integrated with ERP systems, you can manage capital-intensive initiatives, such as infrastructure upgrades or asset acquisitions, with full financial control and compliance. When you create an investment project in Project Operations, you automatically create a corresponding project in **Dynamics 365 Finance** marked as an investment project.

This feature streamlines the lifecycle of **investment projects**, from initial planning to asset capitalization. It supports robust financial management and operational efficiency across integrated ERP environments.

## Prerequisites

To use this functionality, activate the **Enable investment project for Project Operations integrated with ERP** feature in **Dynamics 365 Finance**.

### Minimum versions required

To use the feature for **Dynamics 365 Project Operations integrated with ERP scenarios**, you must have the following versions:

- **Project Operations Dataverse** version 4.162.0.X or later
- **Dynamics 365 Finance** version 10.0.47 or later

### Dual-write maps

| Required dual-write map | Required version | Initial synchronization |
|---|---|---|
| Projects V2 (msdyn_projects) | 1.0.0.3 | Not applicable |

## Investment project

Users can create projects and designate them as investment projects in **Dynamics 365 Project operations**. This classification differentiates investment projects from other types (fixed price, time, and material) and triggers specific system behaviors.
Once you designate a project as an investment project, you can't link it to or use it for **project quotations** or **project contracts**. You can change the project type only if no actual transactions exist for the project. After you process any transactions, the project type becomes locked and can't be changed.

When you create an **investment project** in **Dynamics 365 Project Operations**, the system automatically creates a corresponding project in **Dynamics 365 Finance** and marks it as an investment project. For each investment project in Dynamics 365 Finance, the system also establishes a dedicated **revenue recognition project**.
This dual-project setup is essential for processing financials related to the investment initiative. The revenue recognition project enables the system to:

- Acquire the fixed asset associated with the investment project, or
- Move the accumulated Work In Progress (WIP) costs to the appropriate ledger accounts as part of the revenue recognition and elimination process.

To create an investment project in Dynamics 365 Project operations, follow these steps:

1. Go to **Dynamics 365 Project Operations** > **Projects** > **Projects**.
1. Select **+ New Project** to create a new project.
1. Enter a Name, Description, Owning Company, and set **Investment Project** to **Yes**.
1. Select **Save** to save the project.

To review the **Investment project** and **Revenue recognition project** in **Dynamics 365 Finance**, follow these steps.

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All projects**.
1. Search for the project created in **Dynamics 365 Project Operations**.
1. This project is marked as an **Investment project**.
1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All revenue recognition projects**.
1. A new revenue recognition project is created with the same Project ID.
1. Select the Revenue project ID and verify that the **Investment project** is associated with the **Revenue recognition project**.

After you create the investment project in **Dynamics 365 Project operations**, you can define the Work Breakdown Structure (WBS) and enter project estimates. The system automatically synchronizes these estimates with Dynamics 365 Finance as project forecasts, ensuring alignment between project planning and financial management.

## Accounting

After you create the project, enter and process timesheets, expenses, material usage, or purchase orders to record project cost actuals. 
Transfer these actual costs to Dynamics 365 Finance, where you make financial postings and generate the project subledger.

### Project cost and revenue profile

**Project cost and revenue profiles** define the financial framework for how project costs, sales, and revenue recognition transactions are managed. To support financial management for investment projects, this feature introduces a new **accounting method** called **Investment**. This method enables accurate tracking and posting of costs and revenues specific to investment projects,
ensuring compliance with capitalization and financial reporting requirements.

To create a **Cost and revenue profile** for the Investment project in **Dynamics 365 Finance**, follow these steps:

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Setup** > **Posting** > **Project cost and revenue profile**.
1. Select **+New** to create a new Project cost and revenue profile.
1. Enter the profile ID, name, and choose **Accounting method** as **Investment**.
1. Set the ledger setup for hour, expense, item, and other types of transactions.
1. Select the **Cost template and period code** for the revenue recognition process.

### Project cost and revenue profile rules

**Project cost and revenue profile rules** define how projects are associated with specific **cost and revenue profiles**.
Assign a cost and revenue profile to an individual project, a group of projects, or apply it across all projects.
This configuration ensures consistent financial treatment and reporting for project costs and revenue recognition.

To create a **Project cost and revenue profile rule** for the Investment project in **Dynamics 365 Finance**, follow these steps:

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Setup** > **Posting** > **Project cost and revenue profile rules**.
1. Select **+New** to create a new Project cost and revenue profile rules.
1. Select the **Accounting method** as **Investment**, select project relation, and choose **Project cost and revenue profile**.

### Revenue recognition

Use the revenue recognition project linked to an investment project to execute periodic processes that assess the percentage of completion, and transfers costs from the Profit and Loss account to the Balance Sheet (Work in Progress accounts).
For revenue recognition, you can configure whether the project’s **work in progress costs** are transferred to a **ledger account** or to a **fixed asset** as part of the **elimination** process.

#### Calculate and post revenue recognition

To link the **revenue recognition project** with a **ledger account** or **fixed asset** during an elimination, follow these steps:

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All revenue recognition projects**.
1. Select the Revenue project ID and verify that **Investment project** is associated with **Revenue recognition project**.
1. Select **Revenue recognition** and **+New** to create the snapshot for the period.
1. Validate the percentage of completion until the period selected.
1. Go to **General** tab.
1. Select **Eliminate to** as **Ledger** or **Fixed asset**.
1. Select **Post** to generate financials for all the transactions used for the revenue recognition process.

As part of this process, reclassify and move any transactions previously posted to Profit and Loss accounts to Balance Sheet (Work in Progress) accounts. This reclassification ensures accurate financial representation of project costs during the asset capitalization or elimination phase.

#### Eliminate the project

When all costs are posted to the project subledger and the project is ready to close, run the **revenue recognition elimination** process.
This process transfers project costs from Balance Sheet (Work in Progress) accounts to the appropriate ledger or fixed asset account, ensuring accurate financial closure and asset capitalization.

To execute the **Revenue recognition elimination process**, follow these steps:

1. Go to **Dynamics 365 Finance** > **Project management and accounting** > **Projects** > **All revenue recognition projects**.
1. Select the Revenue project ID and verify that **Investment project** is associated with **Revenue recognition project**.
1. Select **Revenue recognition** and choose **Cost to complete method** as **Set cost to complete to zero**.
1. Validate the WIP, profit & loss details, and project snapshot.
1. Select **Eliminate** to close the revenue recognition project. This step transfers project costs from **Balance Sheet (Work in Progress)** accounts to the appropriate **Ledger** or **Fixed asset** selected during first execution of revenue recognition.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
