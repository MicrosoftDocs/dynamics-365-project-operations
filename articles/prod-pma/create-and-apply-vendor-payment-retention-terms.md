---
# required metadata

title: Create and apply vendor payment retention terms
description: Learn how to set up and apply vendor payment retention terms to ensure payments are retained until project milestones are met. Follow step-by-step instructions.
author: abriccetti
ms.author: abriccetti
ms.date: 02/06/2026
ms.topic: how-to
audience: Application User
ms.reviewer: johnmichalak
ms.search.region: Global
ms.search.industry: Service industries
ms.dyn365.ops.version: 7.0
ms.search.validFrom: 2019-01-15

---

# Create and apply vendor payment retention terms

[!include [banner](../includes/banner.md)]

Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor. For example, you might want to hold payment to a vendor until the products delivered meet your expectations. You can specify vendor payment retention terms when you negotiate a vendor contract.

## Create vendor payment retention terms

Enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to release. The system automatically retains amounts on vendor invoices until the contract reaches the specified state of completion. After you set up the retention terms, you can apply them to any project for that vendor.

Use the following steps to set up and maintain retention terms for vendor payments.

1. Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.
1. Select **New** to add a new vendor retention term. The system automatically enters the **Rule ID** value for the new term.
1. Enter a brief description in the **Description** field. On the **Terms** FastTab, select **Add line** to enter term values for the following values:

   - **Percentage of units delivered**: Enter a percentage of completion for the term. The system automatically retains amounts on vendor invoices until the project stage of completion is equal to the specified percentage. For example, if you enter 50.00, the system retains amounts until the project is 50 percent completed.
   - **Percentage to retain**: Enter a percentage of the vendor invoice amount to retain. For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.
   - **Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to release for the selected level of project completion.

> [!NOTE]
> If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule. Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.

After you create vendor retention terms for a vendor, you can apply the terms to a project.

## Apply vendor retention terms to a project

1. Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.
1. On the **Vendor agreements** FastTab, select **Add line**.
1. In the **Account code field**, select one of the following options:

   - **Table**: The vendor retention terms apply to a single vendor.
   - **Group**: The vendor retention terms apply to all vendors in a vendor group.
   - **All**: The vendor retention terms apply to all vendors.

1. In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply. If you selected **All** in the previous step, this field is unavailable.
1. In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.
1. If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.

The vendor retention terms also appear on purchase orders that you create for the vendor.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
