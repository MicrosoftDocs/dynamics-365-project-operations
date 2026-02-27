---
title: Project Operations setup and configuration data integration
description: This article provides information about setting up and configuring Project Operations dual-write maps. 
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: install-set-up-deploy
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project Operations setup and configuration data integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

This article provides information about Project Operations dual-write integration for setup and configuration entities.

## Project contracts, contract lines, and projects

You create project contracts, contract lines, and projects in Dataverse and synchronize them to finance and operations apps for additional accounting. You can only create and delete the records in these entities in Dataverse. However, you can add accounting attributes such as sales tax group defaults and financial dimensions to these records in the finance and operations apps.

  :::image type="content" source="./media/1ProjectContract.jpg" alt-text="Screenshot of project contract integration concepts.":::

You track sales activity leads, opportunities, and quotes in Dataverse. These records don't synchronize to finance and operations apps because there's no downstream accounting associated with this activity.

The project contract functionality in Dataverse creates a project contract record in finance and operations apps by using the **Project contract headers (salesorders)** table map. When you save a project contract in Dataverse, you also start the creation of a project contract customer entity record. This record is synchronized to finance and operations apps by using the **Project funding source (msdyn\_projectcontractssplitbillingrules)** table map. This map also synchronizes project contract customer additions, updates, and deletions. You master split billing percentages between project contract customers only in Dataverse and don't synchronize them to finance and operations apps.

After you create a project contract in Dataverse, the project accountant can update the accounting attributes for this project contract in finance and operations apps by going to **Project management and accounting** > **Project contracts** > **Set up** > **Show default accounting**. The accountant can review operational project contract attributes, such as requested delivery date and contract amount by selecting the project contract ID in finance and operations apps which opens the related project contract record in Dataverse.

You synchronize the project entity to finance and operations apps by using the **Projects V2 (msdyn\_projects)** table map. The project accountant can:

  - Review projects in finance and operations apps by going to **Project management and accounting** > **All projects**. 
  - Update accounting attributes for the project in finance and operations apps by going to **Project management and accounting** > **All projects** > **Set up** > **Show default accounting**.  
  - Review operational project attributes, such as estimated start and end dates, by selecting the project ID in finance and operations apps which opens the related project record in Dataverse.

You associate a project with a project contract through the **Project contract line** entity.

Project contract lines in Dataverse create a project contract billing rule in finance and operations apps by using the **Project contract lines (salesorderdetails)** table map. The billing method defines the project contract billing rule type in finance and operations apps:

  - Project contract lines with a billing method of time and material create a billing rule of time and material type.
  - Fixed price billing method contract lines create a milestone billing rule.

The project accountant can review project contract lines in finance and operations apps by going to **Project management and accounting** > **Project contracts** > **Set up** > **Show default accounting** and reviewing the details on the **Contract lines** tab. The accountant can also set default financial dimensions for the fixed price billing method contract lines on this tab.

## Billing milestones

The system invoices project contract lines that use the fixed price billing method through billing milestones. The **Project Operations integration contract line milestones (msdyn_contractlinescheduleofvalues)** table map synchronizes billing milestones to project on-account transactions in finance and operations apps.

  :::image type="content" source="./media/2Milestones.jpg" alt-text="Screenshot of billing milestones integration.":::

The accountant can review on-account transactions and adjust the accounting attributes for those transactions by going to **Project management and accounting** > **Project contracts** > **Maintain** > **On-account transactions** or **Project management and accounting** > **All projects** > **Maintain** > **On-account transactions**.

When you first create a billing milestone for a given project contract line, the system automatically creates a fixed price revenue estimate project for the project associated with this contract line. You can review fixed-price revenue estimate projects by going to **Project management and accounting** > **Fixed-price revenue estimate projects**.

### Project tasks

The **Project tasks (msdyn_projecttasks)** table map synchronizes project tasks to finance and operations apps for reference purposes only. Finance and operations apps doesn't support creating, updating, or deleting operations.

  :::image type="content" source="./media/3Tasks.jpg" alt-text="Screenshot of project tasks integration.":::

## Project resources

The **Project resource roles for all companies (bookableresourcecategories)** table map synchronizes the **Project resource roles** entity to finance and operations apps for reference purposes only. Because resource roles in Dataverse aren't company-specific, the system automatically creates respective company-specific resource roles records in finance and operations apps for all legal entities included in the dual-write integration scope.

:::image type="content" source="./media/5Resources.jpg" alt-text="Screenshot of resource roles integration.":::

You maintain project resources in Project Operations in Dataverse. You don't synchronize project resources to finance and operations apps.

### Transaction categories

Dataverse maintains transaction categories and synchronizes them to finance and operations apps by using the **Project transaction categories (msdyn\_transactioncategories)** table map. After you synchronize the transaction category record, the system automatically creates four shared category records. Each record corresponds to a transaction type in finance and operations apps and links them to the transaction category record.

:::image type="content" source="./media/4TransactionCategories.jpg" alt-text="Screenshot of transaction categories integration.":::

Using transaction categories for estimates and actuals requires the project accountant or system administrator to create corresponding project categories in every legal entity. For more information, see [Configure project categories](../project-accounting/configure-project-categories.md).
