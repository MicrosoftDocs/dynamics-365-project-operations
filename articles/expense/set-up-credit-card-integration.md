---
title: Set up credit card integration
description: Learn how to set up credit card integration for expense management. Import transactions automatically or manually, and streamline your financial processes.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: how-to
ms.custom: 
  - bap-template 
ms.reviewer: johnmichalak

---

# Set up credit card integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

You can set up expense-related credit card transactions to automatically import on a recurring schedule. Alternatively, you can manually import the transactions as needed. Import the credit card transactions through the credit card transactions data entity.

## Import credit card transactions

To import credit card transactions, follow these steps:

1. On the **Credit card transactions** page, select **Import transactions**. If you're opening data management for the first time, the system updates the list of data entities before you can continue.
1. In the **Name** field, enter a unique description for the import job.
1. In the **Source data format** field, select the format of the file that contains the credit card transactions to import.
1. Select **Upload**, and then find and select the file to import.
1. After the file is uploaded, validate the mapping of the credit card transaction file and the columns of the credit card transactions data entity by selecting the **View map** link on the tile. If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.
1. To automate the credit card transactions, select **Create recurring data job**. You can then set the recurrence that defines how often credit card transactions should be imported. When you finish, select **OK**.
1. To import the selected file now, select **Import**.
1. If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help ensure a successful import.

> [!NOTE]
> If you need to import more than one file format, you must create separate import jobs for each format type.
>
> You can also split credit card transactions. Starting with version 10.0.46, you can split transactions even when there are policy violations, but you must resolve the violations before submission.

## Reassign the credit card transactions for terminated employees

When you terminate an employee record, the process disables the employee's Active Directory Domain Services (AD DS) account. However, the employee might have active credit card transactions that you still need to expense and reimburse. On the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee is terminated.

Select one or more credit card transactions, and then select **Reassign transactions**. Select another employee to assign the credit card transactions to. After you reassign the credit card transactions, select them for an expense report and pay through the usual process for expense report reimbursement.

## Delete credit card transactions

Sometimes, after you import credit card transactions, you need to delete certain transactions. This need could be because the transactions are duplicates or because the data isn't accurate. Admins can use the **Delete credit card transactions** feature to select and delete credit card transactions that are **not attached** to an expense report.

1. Go to **Periodic tasks** > **Delete credit card transactions**.
1. Select **Filter** and provide information to identify the records to include.
1. Select **OK** to delete the records.

## Storing credit card numbers

Three options are available for storing credit card numbers. Store credit card numbers on the **Expense management parameters** page.

- **Prevent card number entry** – Credit card numbers aren't stored.
- **Hash card numbers (store last four digits)** – The last four digits of credit card numbers are stored in an encrypted format.
- **Store card numbers** – Credit card numbers are stored in an unencrypted format. This option doesn't comply with the Payment Card Industry (PCI) Data Security Standard (DSS). To keep their organization compliant with PCI DSS regulations, organization admins should choose either not to store credit card numbers or to store hash card numbers.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
