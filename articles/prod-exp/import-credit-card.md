---
title: Import and maintain credit card transactions
description: This article explains how to import and maintain expense-related credit card transactions. These transactions can be set up so that they are automatically imported on a recurring schedule, or they can be manually imported as they are required.
author: mukumarm 
ms.author: mukumarm 
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.search.form: TrvPbsMainDataLines
ms.reviewer: johnmichalak
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4

---

# Import and maintain credit card transactions

You can set up expense-related credit card transactions to import automatically on a recurring schedule. Alternatively, you can manually import the transactions as needed. Import the credit card transactions through the **Credit card transactions** data entity.

For more information about data entities, see [Data entities](/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities).

## Import credit card transactions

1. On the **Credit card transactions** page, select **Import transactions**. If you're opening data management for the first time, the system updates the list of data entities before you can continue.
1. In the **Name** field, enter a unique description of the import job.
1. In the **Source data format** field, select the format of the file that contains the credit card transactions to import.
1. Select **Upload**, and then find and select the file to import.
1. After the file is uploaded, validate the mapping of the credit card transaction file and the columns of the **Credit card transactions** data entity by selecting the **View map** link on the tile. If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.
1. To automate the credit card transactions, select **Create recurring data job**. You can then set the recurrence that defines how often credit card transactions should be imported. When you finish, select **OK**.
1. To import the selected file now, select **Import**.
1. If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.

> [!NOTE]
> If you must import more than one file format, you must create separate import jobs for each format type.

## Reassign the credit card transactions for terminated employees

After you terminate an employee record, the employee's Active Directory Domain Services (AD DS) account is disabled. However, there might be active credit card transactions that you must still expense and reimburse. From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee is terminated.

Select one or more credit card transactions, and then select **Reassign transactions**. You can then select another employee to assign the credit card transactions to. After the credit card transactions are reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
