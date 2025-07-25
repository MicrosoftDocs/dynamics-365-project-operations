---
title: Integrate project invoices using dual-write async configuration (preview)
description: Learn how to configure Dynamics 365 Project Operations dual-write asynchronous integration for customer invoicing.
author: mukumarm
ms.author: mukumarm
ms.date: 07/23/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Integrate project invoices using dual-write async configuration (preview)

[!INCLUDE[banner](../includes/banner.md)]
[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to configure Dynamics 365 Project Operations dual-write asynchronous integration for customer invoicing. The asynchronous dual-write process enables the creation of customer invoices with more than 1,000 invoice lines, overcoming the current limitation of the real-time dual-write synchronization.

In Project Operations, customer invoicing is a critical process that ensures accurate and timely billing for project-based work. 
Traditionally, the **dual-write real-time** synchronization mechanism was used to integrate data between Dynamics 365 Finance and Dataverse. 
However, this real-time sync has a known limitation: it supports a maximum of 1,000 invoice lines per customer invoice.

To address this constraint, Microsoft introduced dual-write asynchronous (async) integration for customer invoicing. This enhancement significantly improves scalability and performance, especially for organizations dealing with high-volume, complex billing scenarios.

## Enable dual-write async configuration for customer invoicing

In Project Operations, the Project manager manages the project billing backlog and creates a proforma invoice for the customer in Dataverse. 
Dual-write integration ensures that the proforma invoice details are synchronized to finance and operations apps. 
The following graphic provides a high-level conceptual overview of this integration.

:::image type="content" source="./media/DW5Invoicing.png" alt-text="Screenshot of project invoice integration flow.":::

### Update Project Operations parameters

To update the Project Operations parameters, follow these steps.

1. Go to **Dynamics 365 Project operations** app.
1. Select **Settings** and open **Parameters** form.
1. Select **Edit**.
1. On the **Project task time tracking** dropdown, choose **Delayed update**.
1. On the **Project actual values tracking** dropdown, choose **Delayed update**.

### Update the Dual-write Core solution

In the **Power Apps portal**, update the **Dual-write Core** solution to the latest version available for your environment to ensure compatibility and access to the newest features.

To update the Dual-write Core solution, follow these steps.

1. Go to https://make.powerapps.com.
1. Ensure you're logged into the correct environment where dual-write is configured.
1. In the navigation pane, select **Solutions**. Solutions lists all installed solutions in your environment.
1. Locate the **Dual-write Core** solution in the list, and select it to view the current version and details.
1. Compare the list with the latest version available on **Microsoft AppSource**.
1. In the **Solutions** area, select **Open AppSource**. Search for **Dual-write Core**.
1. Select the latest version of the **Dual-write Core** solution.
1. Select **Get it now** and follow the prompts to install or update. Choose the correct **environment** during installation.

### Enable the dual-write asynchronous (async) integration for Project invoice

In **Dynamics 365 Finance**, the generation of a project invoice involves the synchronization of three key entities:

- **Project invoice proposal V2 (invoices)** – Represents the draft version of the invoice.
- **Project Operations integration actuals (msdyn_actuals)** – Contains the billed sales invoice transactions.
- **Integration entity for project transaction relationships (msdyn_transactionconnections)** – Links actuals to the invoice proposal, ensuring traceability and data integrity.

To enable the dual-write asynchronous (async) integration, these entities must be transitioned from the **real-time sync** process to the **asynchronous** processing model. 

To enable the dual-write asynchronous (async) integration, follow these steps.

1. In Dynamics 365 Finance, go to the **Data management** workspace.
1. Select **Dual-write**.
1. Select the dual-write maps for Project Operations integration actuals (msdyn_actuals), Project invoice proposal V2 (invoices), and Integration entity for project transaction relationships (msdyn_transactionconnections).
1. Select **Integration jobs**.
1. Select **New** to create a new integration job.
1. Select the integration job ID.
1. Select **Add table map** and select Project invoice proposal V2 (invoices), Project Operations integration actuals (msdyn_actuals) and Integration entity for project transaction relationships (msdyn_transactionconnections) in sequence.
1. Select **Save** to save the integration job.
1. Select **Run** to run the integration job in async mode.
