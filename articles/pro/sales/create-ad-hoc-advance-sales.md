---
title: Create an ad hoc advance on a project contract
description: This article provides information about creating an advance on a contract as needed.
author: suvaidya
ms.date: 06/07/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: nshrivastava
---

# Create an ad hoc advance on a project contract

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Microsoft Dynamics 365 Project Operations supports invoicing scenarios that involve pre-payments and advances. The process for using **Advances** in **Project Operations** is similar to **Retainer** contracts. 

Complete the following steps to invoice the customer for an advance.

1. Go to the **Project Contract** page, and then select the **Advances and Retainers** tab.
2. In the subgrid that lists all the previously recorded advances and prepayments, select **+ New Project contract retainer**. 

    The **Quick Create** form opens for recording a prepayment or advance.
    
3. The table below lists the fields for recording an advance and the considerations to keep in mind as you create new ones:

    | Field | Description | Downstream impact |
    | --- | --- | --- |
    | **Project Contract Customer** | This field indicates which customer on the contract will be invoiced for this advance. | If you have multiple customers on the contract and want to invoice each of them for a specific retainer or advance amount, create an advance for each customer individually. |
    | **Description** | The description of the purpose or timing of the advance to help identify this advance. | This description is displayed on the invoice line for this advance. |
    | **Amount** | The amount for the pre-payment or advance. | This amount is displayed on the invoice line for this advance. |
    | **Invoice Date** | The date on which this advance is invoiced to the customer. | This is the date for the automated invoice creation process to create an invoice line for this advance. |
    | **Invoice Status** | This is an option setting that indicates whether this advance is added to a draft invoice for this customer. The possible values are:</br>- **Not ready to invoice**</br>- **Ready to invoice** | When an advance or pre-payment is marked as **Ready to invoice**, it is added as a line time on a draft invoice. Only a fully invoiced advance can be used to reconcile against project costs for the next invoice period. |

4. Select **Save and close** on the quick create dialog to record the advance or the pre-payment.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
