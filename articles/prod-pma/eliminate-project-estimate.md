---
title: Eliminate project revenue recognition
description: Learn how to eliminate project revenue recognition after project completion with step-by-step guidance. Simplify financial processes and ensure accuracy.
author: Yowelle
ms.date: 01/30/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: andchoi
ms.dyn365.ops.version: 7.0
ms.search.validFrom: 2019-01-15
---
# Eliminate a project estimate

[!include [banner](../includes/banner.md)]

 > [!NOTE]
   > Estimates are renamed to revenue recognition in a recent product update. Terminology might reference either estimate or revenue recognition depending on if the feature is enabled.

Project estimates provide the financial view for work that is estimated and scheduled for a project. To work with estimates for a project, you must attach the project to an estimate project. An estimate project is always based on an existing project, but multiple projects can refer to a single estimate project. Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.

To eliminate an estimate project, it must be complete. The following steps explain how to eliminate an estimate.

1. Go to **Project management and accounting** > **All Projects** and open the project.
1. On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.
1. On the **Eliminate estimate** page on the **General** tab, set the following options:

   - **Period code**: Select the period code to choose the appropriate estimate projects.
   - **Estimate date**: Select the appropriate estimate date for elimination.
   - **Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated. When this option isn't enabled, elimination can't continue if any non-estimated transactions exist.
     > [!NOTE]
     > This option is available only when elimination is applied to an estimate project. It's not available if you are using periodic postings. This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.
   - **Set stage to Finished**: Enable this option to set the estimate project's stage to **Finished** after you run the elimination.
   - **Print estimate list**: Select the information to be included when the estimate list is printed.
   - **Show Infolog**: Enable this option to display the Infolog.
   - **Posting date**: Choose the ledger posting date of the estimate.

1. Select **OK**.
1. After the elimination process completes, the eliminated estimate project is displayed with a negative value.

If you didn't intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.

## Estimates are now revenue recognition

In the version 10.0.36 update, the feature **Update labels for revenue recognition and related forms and processes in Project Operations** became mandatory. This feature changes labels in many areas, including the following major changes:

- The menu structure under **Project management and accounting** -> **Periodic** ->
  - **Estimates** changes to **Revenue recognition**
- The menu structure under **Project management and accounting** -> **Setup** ->
  - **Estimates** changes to **Revenue recognition**
- The menu structure under **Project management and accounting** -> **Inquiries and reports** ->
  - **Estimates inquiries and reports** changes to **Revenue recognition inquiries and reports**
- Within a project, the **Estimates** tab under **Manage** in the ribbon changes to **Revenue recognition**

[!INCLUDE[footer-include](../includes/footer-banner.md)]
