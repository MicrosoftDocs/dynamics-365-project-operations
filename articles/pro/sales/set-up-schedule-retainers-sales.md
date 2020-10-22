---
title: Set up a retainer schedule
description: This topic provides information about how to set up a retainer schedule in Project Operations.
author: rumant
manager: Annbe
ms.date: 10/22/2020
ms.topic: article
ms.service: dynamics-365-customerservice
ms.reviewer: kfend 
ms.author: rumant
---

# Set up a retainer schedule

_**Applies To:** Lite deployment - deal to proforma invoicing_

Retainer schedules are set up on the **Project Contract** page in Dynamics 365 Project Operations.

1. On the **Project Contract** page, on the **Advances and Retainers** tab, select **Set up retainer schedule**.
2. On the dialog page that opens, the fields listed in the following table are shown. The table gives an idea on how the entered valuesimpact or influence the retainer schedule that will be created.

| Field | Relevance, purpose, and guidance | Downstream impact |
| --- | --- | --- |
| Project Contract Customer | The customer on the contract who will be invoiced for this retainer or advance. | If you have multiple customers on the contract, and if you need to invoice each of them for a specific retainer or advance amount, manually create one invoice for each customer. |
| Retainer Schedule Start | Enter the start date of the retainer schedule. | This date may not be the date on which the first retainer or advance is created. The date on which the first retainer or advance is created is also influenced by the invoice frequency. |
| Retainer Schedule End | Enter the end date of the retainer schedule. | This date may not be the date on which the last retainer or advance is created. The date on which the last retainer or advance is created is also influenced by the invoice frequency. |
| Number of Retainers to Create | When you enter the number of retainers to create, the system uses the start date and frequency to create the number in this field. | When this field is manually updated, the system ignores the value in the **Retainer Schedule End** field and instead creates the specific number of retainers or advances. |
| Invoice Frequency | How often the application will create retainers and advances. | This value directly influences the number of retainers and advances and the dates of those created. |
| Total Amount | The total amount is the amount that is split into the individual retainer or advance payments that will be created. | There is no downstream impact for this field. |
