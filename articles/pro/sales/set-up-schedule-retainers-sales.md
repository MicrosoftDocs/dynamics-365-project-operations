---
title: Set up a retainer schedule
description: This article provides information about how to set up a retainer schedule in Project Operations.
author: poojafandan
ms.date: 02/26/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# Set up a retainer schedule

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

Set up retainer schedules on the **Project Contract** page in Dynamics 365 Project Operations.

1. On the **Project Contract** page, select the **Advances and Retainers** tab, and then select **Set up retainer schedule**.
1. On the dialog box, enter the values for the fields listed in the following table. The table explains how each field affects the retainer schedule.

| Field | Description | Downstream impact |
| --- | --- | --- |
| Project Contract Customer | The customer on the contract who you invoice for this retainer or advance. | If the contract has multiple customers and you need to invoice each customer for a specific retainer or advance amount, manually create one invoice for each customer. |
| Retainer Schedule Start | Enter the start date of the retainer schedule. | This date might not be the date for the first retainer or advance. The invoice frequency also affects the date for the first retainer or advance. |
| Retainer Schedule End | Enter the end date of the retainer schedule. | This date might not be the date for the last retainer or advance. The invoice frequency also affects the date for the last retainer or advance. |
| Number of Retainers to Create | When you enter the number of retainers to create, the system uses the start date and frequency to create the number in this field. | When you manually update this field, the system ignores the value in the **Retainer Schedule End** field and instead creates the specific number of retainers or advances. |
| Invoice Frequency | How often the application creates retainers and advances. | This value directly influences the number of retainers and advances and the created dates. |
| Total Amount | The total amount that the system splits into the individual retainer or advance payments that it creates. | There's no downstream impact for this field. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
