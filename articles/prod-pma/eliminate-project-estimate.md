---
title: Eliminate project revenue recognition
description: This article provides information about eliminating project revenue recognition after the project is complete. 
author: Yowelle
ms.date: 10/27/2023
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
   > Estimates have been renamed to revenue recognition in a recent product update. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

Project estimates provide the financial view for work that is estimated and scheduled for a project. To work with estimates for a project, you must attach the project to an estimate project. An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project. Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.

To eliminate an estimate project, it must be complete. The following steps explain how to eliminate an estimate.

1. Go to **Project management and accounting** > **All Projects** and open the project. 
2. On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.
3. On the **Eliminate estimate** page on the **General** tab, set the following options:

   - **Period code**: Select the period code to choose the appropriate estimate projects. 
   - **Estimate date**: Select the appropriate estimate date for elimination.
   - **Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated. When this option is not enabled, elimination can’t continue if any non-estimated transactions exist. 
   > [!NOTE]
   > This option is available only when elimination is applied to an estimate project. It is not available if you are using periodic postings. This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.
   - **Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.
   - **Print estimate list**: Select the information to be included when the estimate list is printed.
   - **Show Infolog**: Enable this option to display the Infolog.
   - **Posting date**: Choose the ledger posting date of the estimate.

4.  Select **OK**.
5. After the elimination process is complete, the eliminated estimate project is displayed with a negative value. 

If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.   

## Estimates have been renamed to revenue recognition

With the 10.0.36 version update, the feature **Update labels for revenue recognition and related forms and processes in Project Operations** was made mandatory and took effect for customers. This changes labels in many areas, including the major changes in:

- The menu structure under **Project management and accounting** -> **Periodic** -> 
    - **Estimates** changing to **Revenue recognition**
- The menu structure under **Project management and accounting** -> **Setup** -> 
    - **Estimates** changing to **Revenue recognition**
- The menu structure under **Project management and accounting** -> **Inquiries and reports** -> 
    - **Estimates inquiries and reports** changing to **Revenue recognition inquiries and reports**
- Within a project, the **Estimates** tab under **Manage** in the ribbon changing to **Revenue recognition**

[!INCLUDE[footer-include](../includes/footer-banner.md)]
