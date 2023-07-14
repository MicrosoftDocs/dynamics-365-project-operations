---
# required metadata

title: GST/TDS-TCS tax support for Project integration journals
description: This article explains the calculation of Indian taxes and how to adjust accounting attributes for GST and TDS-TCS transactions in Project integration journals.
author: prabhatb
ms.date: 06/02/2023
ms.topic: article
ms.prod: 
ms.technology: 

# optional metadata

# ms.search.form: 
audience: Application User
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: Core, Operations
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: India
# ms.search.industry: 
ms.author: kfend
ms.search.validFrom: 2023-05-25
ms.dyn365.ops.version: 10.0.35
---

# GST/TDS-TCS tax support for Project integration journals

[!include [banner](../includes/banner.md)]

The Project integration journal is extended so that you can select tax attributes of direct and indirect taxes of India in the Integration journal. You can use this extension to apply and calculate the required taxes on Project invoice proposal transactions that go through Microsoft Dynamics 365 Project Operations.

To activate this feature, follow these steps.

1. Open the **Feature management** workspace.
2. Find and select **Enable (India) GST/TDS-TCS tax support for Project Integration Journal feature** in the list.
3. Select **Enable**.

    ![Screenshot that shows the feature in the list of available features in the Feature management workspace.](media/project-integration-journal-001.png)

For tax setup, the required configuration version is **85.157.303**.

## Enable GST/TDS-TCS taxes in Integration journals

Project Operations Integration journals are created by using the **Import from staging table** periodic process. You can run this process in Dynamics 365 Finance by going to **Project management and accounting** \> **Periodic** \> **Project Operations Integration** \> **Import from staging table**.

When this feature is enabled, you can calculate Indian taxes and adjust accounting attributes for Goods and Services Tax (GST) and Tax Deducted at Source–Tax Collected at Source (TDS-TCS) transactions in project integration journals. These journals help you use revenue recognition with taxes in the books of accounts. They also let you generate customer tax documents and legally compliant tax reports, such as GSTR-1, GSTR-2, and the GST offline tool.

India-specific tax information is added to the following processes:

- Dynamics 365 Finance:

    - Hour, Fee, Item, and Expense journals
    - Integration journals
    - Project invoice proposals

- Dataverse:

    - Invoice corrections
    - Project invoice proposals

Default tax information and TDS/TCS groups are included in the Hour, Fee, Item, and Expense journals. In Dynamics 365 Finance, you can edit the default tax attributes in Integration journals and Project invoice proposals.

GST calculation is included on the tax document for Expense integration journals. TDS/TCS calculation is included in the withholding tax in Expense integration journals.

## Feature scenarios

The following scenarios are affected by this feature.

### Expense

- Pending vendor invoices that have a project category expense in Finance
- Expense submissions or Project journals that have an expense in Dataverse

### Hour

- Pending vendor invoices that have a project category hour in Finance
- Time entries for a project in Dataverse or creation of a journal that has time

### Fee

- Creation of a fee journal line in Dataverse

### On account

- Project contracts that have fixed price and milestones on an invoice schedule
- Creation of an advance or a retainer in Dataverse

### Item

- Project purchase orders in Finance
- Pending vendor invoices for non-stocked and stocked items in Finance
- Creation of a journal line that has material in Dataverse
- Material usage approval in Dataverse
