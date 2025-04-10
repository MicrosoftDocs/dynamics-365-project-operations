---
title: Managed stocked products
description: This article explains how to manage and utilize stocked products within integrated Project Operations deployments.
author: mukumarm
ms.date: 04/11/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
ms.author: mukumarm
---

# Configure and use stocked products

[!INCLUDE[banner](../../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios._

This article provides an overview of the Stocked Product feature in Microsoft Dynamics 365 Project Operations, which is seamlessly integrated with Dynamics 365 Finance. This feature enables users to manage stocked products, create purchase orders and subcontracts, consume stock for projects, and utilize stocked products in project estimates, quotations, and contracts within Dataverse. 
It supports the creation of project invoices for materials consumed under time and materials-based contract lines, and it uses product costs for revenue recognition in fixed-price contract lines. Additionally, this feature ensures that project costs are accurately reflected in both Dynamics 365 Project Operations and Dynamics 365 Finance.

## Prerequisites

### Features
To use the functionality, activate the following features:

- **Enable stocked products usage for project operations integrated deployments** in **Dynamics 365 Finance**.
- **Enable stocked products usage for project operations integrated deployments** in **Dynamics 365 Project opreations**.

### Minimum versions required

To use the feature for Project Operations integrated deployments, you must have the following versions:

- **Project Operations Dataverse** version 4.141.0.x or later
- **Dynamics 365 Finance** version 10.0.44 or later

### Run Dual-write maps

This section provides information about specific the maps required for stocked products. These dual-write maps for related to **Dynamics 365 supply chain** solution. For more information about **Dynamics 365 supply chain** dual write entities, refer [Unified product experience](articles/fin-ops-core/dev-itpro/data-entities/dual-write/product-mapping.md)

|Dual write map|Version|
|--|--|
|All products (msdyn_globulproducts)|1.0.0.0|
|CDS inventory on-hand entries (msdyn_inventoryonhandentries)|1.0.0.1|
|CDS inventory on-hand requests (msdyn_inventoryonhandrequests)|1.0.01|
|CDS released distinct product (products)|1.0.0.3|
|Colors (msdyn_productcolors)|1.0.0.0|
|Configurations (msdyn_configurations)|1.0.0.0|
|DV Released products (msdyn_sharedproductdetails)|1.0.0.0|
|Inventory aisle (msdyn_warehouseaisles)|1.0.0.0|
|Item batches (msdyn_batchnumbers)|1.0.0.0|
|Item serial numbers (mydyn_serialnumbers)|1.0.0.0|
|Product dimension groups (msdyn_productdimensiongroups)|1.0.0.0|
|Project integration table for material estimates (msdyn_estimatelines)|1.0.0.2|
|Project subcontract purchase order line (msdyn_subcontractlines)|1.0.1.0|
|Sites (msdyn_sites)|1.0.0.0|
|Sizes (msdyn_productsizes)|1.0.0.0|
|Storage dimension groups (msdyn_productstoragedimensiongroups)|1.0.0.0|
|Styles (msdyn_productstyles)|1.0.0.0|
|Tracking dimension groups (msdyn_productdimensiongroups)|1.0.0.0|
|Units (uoms)|1.0.0.0|
|Warehouse locations (msdyn_inventorylocations)|1.0.0.1|

## Products 
**Dynamics 365 Finance** serves as the master system for creating and **releasing products**. When a new product is created or released in Finance, it is automatically synchronized with **Dynamics 365 Project Operations**. 
The product type—whether it is a service item or a stocked item—is also reflected accordingly in Project Operations. If the product includes **multiple variants** based on dimensions such as **size, color, configuration, or style**, each variant is represented as a **separate product** in Project Operations. 
In **Project operations**, products can be activated or deactivated using the **Activate** button on the action pane. 

![Products](/articles/media/Products.png)

![ProductPrice](/articles/media/ProductPrice.png)

### On hand inventory
**Dynamics 365 Project operations**  allows users to view on-hand inventory for specific products within a company. 
On-hand stock can be accessed from various areas, including the **product master**, **project estimates**, **project quotation lines**, **project contract lines**, and **project journals**. 
While Project Operations does not maintain its own inventory data, it retrieves and displays **on-hand stock** information from **Dynamics 365 Finance**. Currently, **Project Operations** supports viewing on-hand inventory up to the **site and warehouse** level.

![Onhand](/articles/media/Onhand.png)
### Cost and sales price list
When a new **product** is released in **Dynamics 365 Finance** and a default **purchase price, sales price, or inventory cost** is added or updated, 
**Dynamics 365 Project Operations** identifies the appropriate cost and sales price lists during synchronization. It selects the **first cost price list** and **sales price list** in **alphabetical order** that matches the **company's currency**. 
If there are any price changes in Dynamics 365 Finance, the corresponding prices in Dynamics 365 Project Operations are automatically updated to reflect the changes.

## Project material estimates
**Dynamics 365 Project Operations** allows users to create **project estimates** for **time, expenses, and materials**. 
These estimates are synchronized as **project item forecasts** in **Dynamics 365 Finance**. For **material estimates**, users can create them for either a **specific product** or a **project variant**. 
When **stocked products** are selected, the **site and warehouse** can be specified on the quick create or detail form. 
This information is then reflected in the corresponding **project item forecast** in **Dynamics 365 Finance**. Additionally, project item forecasts can be used to run master planning, enabling the generation of planned purchase orders or production orders.

![Project material forecast](/articles/media/EstimateLine.png)

![Itemforecast](/articles/media/Itemforecast.png)

For more information about project material estimates, refer [Financial estimates for materials on projects](create-material-estimate.md)

## Project quotations
**Dynamics 365 Project Operations** supports the use of **stocked products** in project quotations. 
**Stocked products** can be added directly to the **project quotation line details**. **Sales prices** are retrieved based on the price list associated with the project quotation, 
but users also have the flexibility to manually adjust the sales price on the quotation line. Additionally, **profitability analysis** for project can be reviewed and validated directly from the project quotation form.

![Project quotation line](/articles/media/ProjectQuote.png)

For more information about project quotations, refer [Manage project quotes](manage-quotes-sales.md)

## Project contracts
**Dynamics 365 Project Operations** supports the use of **stocked products** in project contracts. 
**Stocked products** can be added directly to the **project contract line details**. **Sales prices** are retrieved based on the price list associated with the project contract, 
but users also have the flexibility to manually adjust the sales price on the contract line. Additionally, **profitability analysis** for project can be reviewed and validated directly from the project contract form.

![Project contract line](/articles/media/Projectcontractline.png)

For more information about project contracts, refer [Manage project contracts](manage-contracts-sales.md)

## Purchase orders
**Dynamics 365 Project Operations** enables the execution of the full procurement lifecycle, including **purchase requisitions, purchase agreements, and purchase orders**. 
To utilize **purchase orders** in the **integrated deployments**, the feature **Enable project purchase orders on Project Operations for resource-based/non-stocked scenarios** must be activated.

By enabling the **Enable stocked products usage for project operations integrated deployments**, purchase orders can also be created for **stocked items**. 

Once a purchase order line is created or saved, the **Project Contract Line ID** is automatically populated based on the **project category** and **activity**, provided a project contract exists for the project. 
The **activity** is optional if contract lines are not tied to project tasks in Project Operations or if the project is an internal project. The **Project Contract Line ID** is particularly important for **revenue recognition** when linked to a **fixed-price** contract line.

Upon confirming the **purchase order**, **accounting distributions** are generated to record the **project cost**. This applies only to **stocked products**. 
A warehouse worker can then receive the product using the **product receipt** functionality. The **Accounts Payable clerk** creates the **vendor invoice** through the invoice feature, and these vendor invoices are synchronized with **Dynamics 365 Project Operations**, generating both **project cost actuals and unbilled sales actuals**.

> [!NOTE]
> Project cost generates and posts directly in Dynamics 365 Finance when the vendor invoice is posted. Integration journals are not created for project cost actuals, as the cost is posted during the vendor invoice posting process. This behavior applies only to stocked products. For service items or procurement categories, vendor invoices post the transactions to the procurement integration account.

> [!NOTE]
> Product receipts aren't recorded to the project actuals in Microsoft Dataverse and don't impact the project subledger.

For more information about project purchase orders, refer [Project purchase purchase orders](non-stocked-materials-project-purchase-orders.md)

## Material usage
In **Dynamics 365 Project Operations**, a material usage log provides a way to record material consumption so it can be approved by the project manager and eventually invoiced to the customer. By enabling the stocked product feature, users can create material usage entries for stocked products. These entries can be created for either a **specific product** or a **project variant**. Based on the item and required inventory dimensions, users must specify details such as **site, warehouse**, and, if applicable, **batch or serial number**. It is essential to ensure that inventory is only consumed when sufficient stock is available with the relevant inventory dimensions.

![Material usage](/articles/media/MaterialUsage.png)

For more information about project material usage, refer [Record material usage on projects and project tasks](material-usage-log.md)
### Validations for on hand inventory
When a user **submits material usage** for a stocked product, the system **validates** whether the product is available in stock. If the stock is **unavailable**, the system displays an error and prevents the submission of the material usage.
Similarly, when an **approver** attempts to **approve** material usage, the system checks whether the product is available in stock. If the stock is unavailable, the system displays an error and blocks the approval.

### Inventory cost for material usage
When material usage is approved by the approver, cost and unbilled sales actuals are generated based on the associated cost and sales price lists. Cost actuals are derived from the cost price list; however, the **weighted average** cost of the material may differ. During the posting of the **integration journal** for the cost transaction in the **Dynamics 365 finance**, if the actual cost amount differs from the material’s weighted average cost, the **difference** is treated as an **adjustment**. This adjustment is synchronized back to **Dynamics 365 Project Operations** and reflected in a new field called **Adjustment Value**. The **extended amount** is updated accordingly.

> [!NOTE]
> In **Dynamics 365 Finance**, inventory consumption using inventory journals are always posted using the **weighted average** cost, regardless of the costing method assigned to the material. To align the **inventory cost** of a transaction with the assigned inventory model group, the Inventory **Closing and adjustment** job must be executed.

![Project actuals](/articles/media/Actuals.png)

## Journals
Entry journals are used to record actuals directly in **Dynamics 365 Project Operations**. When you use Entry journals, you don't have to enter Time, Expense, and Material usage logs in Project Operations.
By enabling the stocked product feature, users can create material consumption entries for stocked products. These entries can be created for either a **specific product** or a **project variant**. Based on the item and required inventory dimensions, users must specify details such as **site, warehouse**, and, if applicable, **batch or serial number**. It is essential to ensure that inventory is only consumed when sufficient stock is available with the relevant inventory dimensions.

![Project journals](/articles/media/Projectjournal.png)

For more information about project journals, refer [Create and confirm Entry journals](create-confirm-entry-journals.md)

### Validations for on hand inventory
When a user confirms the **journal** for a stocked product line, the system **validates** whether the product is available in stock. If the stock is **unavailable**, the system displays an error and prevents the confirmation of the journal entry.

## Inventory recalculation and closing
To align the **inventory cost** of a transaction with the assigned inventory model group, the Inventory **Closing and adjustment** job must be executed. If there is any deviation between the **project cost** recorded through the **project integration journal** and the cost calculated based on the **inventory model group**, an adjustment transaction is generated to update the project cost accordingly.

To update project costs in **Dynamics 365 Project Operations**, the recurring batch job **Project cost update for inventory adjustments** must be executed after the Inventory Closing and Adjustment job is completed. This batch job can be scheduled to run on a recurring basis; however, it is recommended to run it only after the inventory closing and adjustment process has been completed.

To run the **Project cost update for inventory adjustments**, do the following:

1. In **Dynamics 365 for finance**, Go to **Project management and accounting**.
2. Go to **Periodic** > **Project operations integration** > ****Project cost update for inventory adjustments**.
3. Apply the filters for the project or project contract.
4. Click **Ok** to update the project cost in **Dynamics 365 project operations**.




