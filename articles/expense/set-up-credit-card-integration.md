---
title: Set up credit card integration
description: This article explains how to work with expense-related credit card transactions.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up credit card integration

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule. Alternatively, the transactions can be manually imported as they are required. The credit card transactions are imported through the credit card transactions data entity.

## Import credit card transactions

To import credit card transactions, follow these steps:

1. On the **Credit card transactions** page, select **Import transactions**. If you're opening data management for the first time, the system must update the list of data entities before you can continue.
2. In the **Name** field, enter a unique description for the import job.
3. In the **Source data format** field, select the format of the file that contains the credit card transactions to import.
4. Select **Upload**, and then find and select the file to import.
5. After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the credit card transactions data entity by selecting the **View map** link on the tile. If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.
6. To automate the credit card transactions, select **Create recurring data job**. You can then set the recurrence that defines how often credit card transactions should be imported. When you've finished, select **OK**.
7. To import the selected file now, select **Import**.
8. If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help ensure a successful import.

> [!NOTE]
> If you need to import more than one file format, you must create separate import jobs for each format type.

 
> [!NOTE]
> Credit card transactions can also be split, and starting with version 10.0.46, splitting is allowed even when there are policy violations though they have to be resolved before submission.

## Reassign the credit card transactions for terminated employees

After an employee record is terminated, the employee's Active Directory Domain Services (AD DS) account is disabled. However, there might be active credit card transactions that must still be expensed and reimbursed. On the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.

Select one or more credit card transactions, and then select **Reassign transactions**. You can then select another employee to assign the credit card transactions to. After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.

## Delete credit card transactions 

Sometimes, after credit card transactions are imported, certain transactions may need to be deleted. This could be because the transactions are duplicates or because the data isn't accurate. Admins can use the **"Delete credit card transactions"** feature to select and delete credit card transactions that are **not attached** to an expense report. 

1. Go to **Periodic tasks** > **Delete credit card transactions**.
2. Select **Filter** and provide information to identify the records to include.
3. Select **OK** to delete the records. 

## Storing credit card numbers

Three options are available for storing credit card numbers. Credit card numbers are stored on the **Expense management parameters** page.

- **Prevent card number entry** – Credit card numbers aren't stored.
- **Hash card numbers (store last four digits)** – The last four digits of credit card numbers are stored in an encrypted format.
- **Store card numbers** – Credit card numbers are stored in an unencrypted format. This option doesn't comply with the Payment Card Industry (PCI) Data Security Standard (DSS). Therefore, to keep their organization compliant with PCI DSS regulations, organization admins should choose either not to store credit card numbers or to store hash card numbers.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
