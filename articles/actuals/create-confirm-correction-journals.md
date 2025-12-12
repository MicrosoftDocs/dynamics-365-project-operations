---
title: Create and confirm Correction journals
description: This article provides information about how to create and confirm a correction journal.
author: rumant
ms.date: 06/10/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: abriccetti
ms.dyn365.ops.version: 
ms.search.validFrom: 2020-10-01
---

# Create and confirm Correction journals

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Occasionally, a time or expense entry might be entered incorrectly. For example, a consultant might select the wrong date when they create a time entry, or they might select the wrong project when they enter an expense. If a consultant can't update the submitted entries, a back-end admin can directly correct the actuals for a project.

By default, the following fields can be corrected using correction journals:
* Project
* Subcontract
* Project task
* Subcontract line
* Entry Date
* Bookable resource
* Resource role (time correction only)
* Expense category (expense correction only)
* Write in product (material entry only)

Any custom pricing dimensions that are added to the appropriate section of the journal form can be corrected using correction journals.

## Correct approved time entries     

Complete the following steps to correct single or multiple time entries for a project.

1. In the **Sales** area, select **Transactions**, and then select **Approved Time**. 

2. In the **Approved Time** list, locate and select one or more approved time entries to correct. You can use the filter to locate related entries. For example, you might filter on a Project ID, and select all approved time entries with that Project ID.

3. Select **Correct entries**. A new correction journal is automatically created, with the assigned type **Time correction**. The entries you selected are added to the journal. 

4. On the **New Journal** page, enter a **Description** for your correction journal, and then select the **Time Entry Corrections** tab.  

5. In the **New Values for Time Entries** section, update the fields with the correct information as necessary. For example, you can change the assigned project or the bookable resource.

6. Select **Preview**. In the dialog box, select **OK**. On the **Journal lines** tab, you can view a list of the original actuals that are related to the selected time entries that have been reversed and the corrected corresponding lines that have been created. If more corrections need to be made, repeat steps 5 and 6. 

    > [!NOTE]
    > All the corrected actuals will have the same values that you selected in the **New values for Time Entries** section.

7. If the corrections appear as expected, select **Confirm**. In the dialog box, select **OK**.

8. Return to the **Sales** area, select **Projects**, and then open the project for which you just updated the time entries. 

9. On the **Projects** page, on the **Actuals** tab, view the changes that you made. 

    > [!NOTE]
    > If the **Actuals** tab isn't visible, select **Related** > **Actuals**.  

10. In the **Actual Associated View** list, you can see that the original time entries that have been reversed are still listed, as are the corresponding corrected time entries. 

 
## Correct approved expense entries

Complete the following steps to correct one or more expense entries. 

1. In the **Sales** area, in the left navigation pane, under **Transactions**, select **Approved Expenses**.

2. In the **Approved Expenses** list, select the project that you want to correct, and then select **Correct entries**. A new correction journal will be created automatically with the assigned type of **Expense correction**. 

3. On the **New Journal** page, enter a **Description** for the correction, and on the **Expense Correction** tab, in the **New Values for Expenses** section, select the data fields that you want to correct for the selected expense lines. For example, you can assign the expense to another **Project**, or correct the **Expense Category**, **Expense Date**, or **Bookable Resource**.

4. Select **Preview**. In the dialog box, select **OK**. 

5. Verify the corrections on the **Journal lines** tab. You can view a list of the original actuals that are related to the selected expense entries that have been reversed and the corrected corresponding lines that have been created.

6. If the corrected values are as expected, select **Confirm**. In the dialog box, select **OK.** If the values aren't showing as expected, select **Cancel** to return to the **Approved Expenses** list. Repeat steps 2 through 5. 

7. After you confirm the correction journal, return to the project or projects that you updated to view your changes.

8. On the project page, on the **Actuals** tab, review the **Actual Associated View** list. The original entries and the corrected entries are listed.


## Correct approved material usage logs

Complete the following steps to correct one or more material usage log entries.

1. In the **Sales** area, in the left navigation pane, under **Transactions**, select **Actuals**.

2. In the **Actuals** list, use column filters to select the **Material** transaction class, so that only the actuals for materials are shown. Use other column filters to further limit the actuals that are shown. After you can find the desired set of actuals, select the actuals, and then select **Correct entries**. A new correction journal is automatically created, and the **Material correction** type is assigned.

3. On the **New Journal** page, in the **Description** field, enter a description for the correction. Then, on the **Material Correction** tab, in the **New Values for Materials** section, select the data fields to correct for the selected material lines. For example, you can assign the material to another project, or correct the product, material date, or subcontract.

4. Select **Preview**. Then, in the dialog box, select **OK**.

5. On the **Journal lines** tab, verify the corrections. You can view a list of the original actuals that are related to the selected material entries that have been reversed and the corrected corresponding lines that have been created.

6. If the corrected values are as expected, select **Confirm**. Then, in the dialog box, select **OK**. If the values aren't as expected, select **Cancel** to return to the **Actuals** list. Then repeat steps 2 through 5.

7. After you confirm the correction journal, return to the project or projects that you updated to view your changes.

8. On the project page, on the **Actuals** tab, review the **Actual Associated View** list. The original entries and the corrected entries are listed.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
