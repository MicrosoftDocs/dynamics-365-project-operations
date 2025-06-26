---
title: Configure non-stocked materials and pending vendor invoices
description: This article explains how to enable non-stocked materials and pending vendor invoices.
author: mukumarm
ms.author: mukumarm
ms.date: 05/22/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure non-stocked materials and pending vendor invoices

_**Applies To:** Project Operations Integrated with ERP_

## Minimum version requirement

Using non-stocked materials and pending vendor invoices for Dynamics 365 Project Operations non-stocked/resource based scenarios requires the following versions:

Dynamics 365 Dataverse solutions:

- Project Operations – 4.9.0.221 or higher
- Dual-write application orchestration solution - 2.2.2.23 or higher

Dynamics 365 Finance:
- 10.0.18 (10.0.793.52) or higher. Make sure that your Finance environment is current and all quality updates are applied to meet the minimum version requirements.

## Run Dual-write maps for non-stocked materials and vendor invoice integration

This section provides information about specific the maps required for non-stocked materials and vendor invoices. Verify that the prerequisite maps listed in the [Provision a new environment](../environment/resource-provision-new-environment.md#run-project-operations-dual-write-maps) article are running on your environment.

1. Go to Lifecycle Services (LCS), navigate to your LCS project, and go to the **Environment details** page.
2. In the **Common Data Service Environment Information** section, select **Link to CDS for Apps**. After you select the link, you will be redirected to the list of entities in the mappings.
3. Make sure the following maps are running. If they aren't running, start them and make sure to include all related table maps.

    - CDS released distinct products (products)
    - Vendors v2 (msdyn_vendors)
    - Project Operations table for material estimates (msdyn_estimatelines)
    - Project Operations integration project vendor invoice export entity (msdyn_projectvendorinvoices)
    - Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines)
    - Project Operations integration actuals (msdyn_actuals). Make sure you are running map version 1.0.0.14 or higher. You can see the active version of the map in the **Version** column on the **Dual Write** page. You can activate a new version of the map by selecting **Table map version** and then saving the selected version.

If you are using standard demo data, you might also need to stop and restart the following entity maps with initial sync:
  - Payment days CDS V2 (msdyn_paymentdays)
  - Payment schedule (msdyn_paymentschedules)
  - Terms of payment (msdyn_paymentterms)
  - Vendor groups (msdyn_vendorgroups)
  - Units (uom)

> [!NOTE]
> The initial sync for vendor groups and units might fail for a few records in the existing demo data set. You can ignore the failures as they won't prevent you from using demo data with Project Operations.

## Configure prerequisites in Dataverse

### Activate workflow to create accounts based on vendor entity

The Dual Write Orchestration solution provides [Vendors master integration](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/vendor-mapping). As a prerequisite for this feature, vendor data must be created in the **Accounts** entity. Activate a template workflow process to create vendors in the **Accounts** table as described in [Switch between vendor designs](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/vendor-switch).

### Set products to be created as active

Non-stocked materials must be configured as **Released products** in Finance. The Dual Write Orchestration solution provides an out-of-the-box [Released products integration to Dataverse Product catalog](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/product-mapping). By default, products from Finance are synchronized to Dataverse in a draft state. To synchronize the product to an active state so that it can be directly used in material usage documents or pending vendor invoices, go to **System** > **Administration** > **System administration** > **System settings**, and on the **Sales** tab, set **Create products in active state** to **Yes**.

## Configure prerequisites in Finance

### Enable the feature key for pending vendor invoices

Complete the following steps to enable functionality to add project details on pending vendor invoice lines.

1. In Finance, go to the **Feature Management** workspace.
2. In the feature list, find **Enable pending vendor invoices on Project Operations for resource based/non-stocked scenarios** feature and select **Enable**.

### Define category groups and project categories for items

Configure at least one category group for the **Item** transaction type , and at least one project category using this group. For more information, see [Configure project categories](../project-accounting/configure-project-categories.md#category-groups).

Review the project cost and revenue profiles, and configure ledger posting setup for item transactions. For more information, see [Configure accounting for billable projects](../project-accounting/configure-accounting-billable-projects.md).

### Set up a write-in product

In Project Operations, you can record material estimates and usage for catalog products that are configured in the released product catalog and for write-in products. Using write-in products requires a single released product that's configured in Finance for this purpose. Complete the following steps to configure a write-in product. Repeat these steps in each legal entity that is using Project Operations for Project Operations Integrated with ERP scenarios.

1. In Finance, go to **Product Information Management** > **Products** > **Released products**, and select **New**.
2. In the **Product type** field, select **Item** and in the **Product subtype** field, select **Product**.
3. Enter the product number (WRITEIN) and the product name (Write-in Product).
4. Select  the item model group. Make sure that the item model group you select has the **Inventory policy Stocked product** field set to **False**.
5. Select values in the **Item group**, **Storage dimension group**, and **Tracking dimension group** fields. Use the **Storage dimension** for **Site** only, and in the **Tracking dimensions** field, select **None**.
6. Select values in the **Inventory unit**, **Purchase unit**, and **Sales unit** field, and then save your changes.
7. In the **Plan** tab, set the default order settings, and on the **Inventory** tab, set the default site and warehouse.
8. Go to **Project management and accounting** > **Setup** > **Project management and accounting parameters** and open **Project Operations on Dynamics 365 Dataverse**. 
9. On the **Materials** tab, in the **Write-in product** field, select the product you created.
10. In your Dataverse environment, in the site map, open the **Products** entity and find the write-in product record. 
11. Open the record details and set product state to **Retired**. This product state prevents anyone from accidentally using this record directly in material estimates and usage documents.

### Set up a procurement integration account

The procurement integration account is used as a clearing account when posting a pending vendor invoice with lines attributed to a project.

When the system posts a pending vendor invoice, this account is used for the project cost amount. The vendor invoice details are processed in Dataverse, and a corresponding project actual is created. The information from the project actual is added to the Project Operations Integration journal. When you post the integration journal, the amount is cleared from the procurement integration account and recorded to the project cost.

1. To set up the procurement integration account, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**, and open **Project Operations on Dynamics 365 Dataverse**. 
2. Select the **Materials** tab, and select a value in the **Procurement integration account** field.

#### Set up project category defaults for an item

1. In Finance, go to **Project management and accounting** > **Setup** > **Project management and accounting parameters**, and open **Project Operations on Dynamics 365 Dataverse**. 
2. On the **Project category defaults** tab, in the **Item** field, select a value. This project category is used for material transactions if the project category wasn't set on the project actuals record.
