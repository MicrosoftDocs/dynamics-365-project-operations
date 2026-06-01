---
title: Set up vendor retention
description: This article explains how to set up vendor retention. 
author: mukumarm
ms.author: mukumarm
ms.date: 02/25/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up vendor retention

_**Applies To:** Project Operations Integrated with ERP_

This article explains how to set up vendor retention.

## Set up a vendor retention account in General ledger

1. In Dynamics 365 Finance, go to **General ledger** > **Posting setup** > **Accounts for automatic transactions**.
1. Add a new line.
1. In the **Posting type** field, select **Vendor retention**.
1. Select the main account for the vendor retention posting.

## Create vendor retention terms

Use the **Vendor retention terms** page to set up and maintain retention terms for vendor payments. Enter the percentage of the vendor payment to retain and the percentage of the previously retained amounts to release. The system automatically retains amounts on vendor invoices until the contract reaches the specified state of completion. After you set up retention terms for a vendor, you can apply them to any project on which the vendor works.

1. In Finance, go to **Project management and accounting** > **Setup** > **Retention** > **Vendor payment retention terms**.
1. Select **New** to add a new vendor retention term. The value in the **Rule ID** field for the new term is automatically entered. 
1. In the **Description** field, enter a descriptive name for the new term.
1. On the  **Terms**  tab, select  **Add line**  to enter a vendor retention term.
1. In the  **Percentage of units delivered**  field, enter a percentage of completion for the rule. The system automatically retains amounts on vendor invoices until the project stage of completion is equal to the percentage that you enter. For example, if you enter 50.00, the system retains amounts until the project is 50 percent completed.
1. In the  **Percentage to retain**  field, enter the percentage of a vendor invoice amount to retain. For example, if you enter 10.00 in this field, 10 percent of the amount on vendor invoices is retained until the project reaches the percentage of completion that you select in the  **Percentage of units delivered**  field.
1. In the  **Percentage to release**  field, enter the percentage of any previously retained amounts to release at the selected level of project completion.

> [!NOTE]
> If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for every retention rule. Each line can specify a different percentage to retain and a different percentage to release for each designated level of project completion.

## Set up a vendor agreement for the project

Set up the vendor retention terms that apply to the project. The vendor retention terms also appear on purchase orders that you create for the vendor.

1. In Finance, go to **Project management and accounting** > **Projects** > **All projects**. 
1. Select a project, and on the Action Pane, select **Project group** > **Vendor agreements**.
1. On **Vendor agreements**, add a new line.
1. In the **Account code** field, select one of the following options:
   - **Table**: The vendor retention terms apply to a single vendor.
   - **Group**: The vendor retention terms apply to all vendors in a vendor group.
   - **All**: The vendor retention terms apply to all vendors.
1. In the **Vendor/Vendor group** field, select the vendor or vendor group to which the vendor retention terms apply. If you selected  **All**  in the previous step, this field is unavailable.
1. In the **Vendor retention terms** field, select the rule ID for the retention terms to apply to this vendor.

[!INCLUDE[footer-include](../includes/footer-banner.md)]