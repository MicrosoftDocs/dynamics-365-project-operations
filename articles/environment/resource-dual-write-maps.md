---
title: Project Operations Dual-write map versions
description: This article provides the list of Dual-write maps required for Dynamics 365 Project Operations.
author: mukumarm
ms.author: mukumarm
ms.date: 04/25/2025
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Project Operations Dual-Write Map Versions

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

Using Dynamics 365 Project Operations for resource/non-stocked scenarios requires a set of **Dual-Write Maps** to be running in the environment. 

## Prerequisites

### 1. Required Apps for Dataverse Environment

To ensure a smooth setup, the following apps must be installed in the **exact order** listed below:

1. **Dual-write Application Core Solutions**
2. **Dual-write Asset Management Solutions**
3. **Dual Write Finance and Extended Solutions**
4. **Dual-write Dynamics 365 Human Resources**
5. **Dual Write Supply Chain Extended Solution**
6. **Dynamics 365 HR Integration to URS**

> [!TIP]
> #### Steps to Install/Manage Apps via PowerApps Portal
> To install and manage the apps mentioned above, follow these steps:
> 1. Sign in to the **Power Platform Admin Center**.
> 2. Select **Environments** and then select an environment.
> 3. Under **Resources**, select **Dynamics 365 apps**.
> 4. Select **Install** app.
> 5. Select an **Enabled** app, and then select Next.
> 6. Agree to the terms of service, and then select **Install**.
>    
> For detailed instructions, refer to [Manage Apps](https://learn.microsoft.com/en-us/power-platform/admin/manage-apps#install-an-app-in-the-environment-view)

### 2. Required Solutions for Finance & Operations

To ensure a smooth setup, the following solutions must be applied as listed below. **This is a crucial prerequisite.**

1. **Dynamics 365 Human Resources entity maps**
2. **Dynamics 365 Project Operations Dual Write Entity Maps**
3. **Dual-write applications core entity maps**
4. **Dynamics 365 Finance extended entity maps**
5. **Dynamics 365 Asset Management entity maps**
6. **Dynamics 365 Supply Chain Management extended entity maps**
7. **HCM Scheduling**

> [!TIP]
> #### Steps to Apply Solution from F&O
> To install and manage the apps mentioned above, follow these steps:
> 1. Sign in to the **Finance and Operations**.
> 2. Select **Data management**.
> 3. Select **Dual-write**.
> 4. Select **Apply Solution**.
> 5. Select all listed solutions from the list above, then select **Apply**.
>
> ![image](https://github.com/user-attachments/assets/f7fb9538-86b1-488b-8d71-7bdaacc5cc8f)


### 3. Refresh Entities from F&O

Before proceeding, ensure that you refresh the entities from Finance and Operations (F&O). **This is a crucial prerequisite.**

_Refreshing the entity list ensures all entities are available in the environment and that the entities have the latest metadata._

> [!TIP]
> #### Steps to Refresh Entities from F&O
> To install and manage the apps mentioned above, follow these steps:
> 1. Sign in to the **Finance and Operations**.
> 2. Select **Data management**.
> 3. Select **Framework parameters**.
> 4. Select **Entity settings**.
> 5. Select **Refresh entity list**.
>    
> For detailed instructions, refer to [Refresh Entity List](https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities#entity-list-refresh)

### 4. Required Maps for Project Operations Solution

The table below shows the maps required for the Project Operations solution. Ensure to run the maps in the exact order listed and include any related table maps in your environment:

| Table Map Name                                       | Initial Sync Details                                                                                                                                        |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Legal entities (**cdm_companies**)                   | Initial Sync **REQUIRED** for the table map and all related table map(s). <br> _Master for the initial sync_ should be the **Finance and Operations apps.** |
| CDS Exchange Rates (**msdyn_currencyexchangerates**) | Initial Sync **REQUIRED** for the table map and all related table map(s). <br> _Master for the initial sync_ should be the **Finance and Operations apps.** |
| Ledger (**msdyn_ledgers**)                           | Initial Sync **REQUIRED** for the table map and all related table map(s). <br> _Master for the initial sync_ should be the **Finance and Operations apps.** |
| Customers V3 (**accounts**)                          | Initial Sync **NOT REQUIRED**                                                                                                                               |
| Vendors V2 (**msdyn_vendors**)                       | Initial Sync **NOT REQUIRED**                                                                                                                               |

1. From the list of maps, select the Ledger **(msdyn\_ledgers)** map with all prerequisites and select the **Initial sync** check box. In the **Master for initial sync** field, select **Finance and operations apps** for both ledger map and all prerequisite maps. Select **Run**.

    ![Ledger map synchronization.](media/DW6.png)

2. Follow the same steps for all remaining table maps listed in the above table. Do not select the **Initial sync** check box when running those maps.

## Project Operations Dual-Write Maps

Dual-Write map versions are listed starting with the Project Operations May 2021 update, version 4.10.0.186.

The table below shows the maps required for the Project Operations solution. Ensure to run the maps in the exact order listed and include any related table maps in your environment:

| Table Map Name                                                                                   | Latest Version | Initial Sync Details                                                                                                                      | Required Dynamics 365 Finance Version |
|--------------------------------------------------------------------------------------------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| Project resource roles for all companies <br> (**bookableresourcecategories**)                   | 1.0.0.1        | Initial Sync **REQUIRED** for the table map and all related table map(s). <br> _Master for the initial sync_ should be the **Dataverse.** |                                       |
| Integration entity for project transaction relationships <br> (**msdyn_transactionconnections**) | 1.0.0.0        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project contract headers <br> (**salesorders**)                                                  | 1.0.0.1        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project contract lines <br> (**salesorderdetails**)                                              | 1.0.0.1        | Initial Sync **NOT REQUIRED**                                                                                                             | 10.0.42 or later                      |
| Project funding source <br> (**msdyn_projectcontractsplitbillingrules**)                         | 1.0.0.2        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Projects V2 <br> (**msdyn_projects**)                                                            | 1.0.0.2        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project tasks <br> (**msdyn_projecttasks**)                                                      | 1.0.0.4        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project transaction categories <br> (**msdyn_transactioncategories**)                            | 1.0.0.0        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project integration table for material estimates <br> (**msdyn_estimatelines**)                  | 1.0.0.4        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |
| Project invoice proposals V2 <br> (**invoices**)                                                 | 1.0.0.3        | Initial Sync **NOT REQUIRED**                                                                                                             |                                       |

| Table Map Name                                                                                                      | Latest Version | Initial Sync Details          | Required Dynamics 365 Finance Version |
|---------------------------------------------------------------------------------------------------------------------|----------------|-------------------------------|---------------------------------------|
| Project Operations integration actuals <br> (**msdyn_actuals**)                                                     | 1.0.0.19       | Initial Sync **NOT REQUIRED** | 10.0.39 or later                      |
| Project Operations integration contract line milestones <br> (**msdyn_contractlinescheduleofvalues**)               | 1.0.0.7        | Initial Sync **NOT REQUIRED** |                                       |
| Project Operations integration entity for expense estimates <br> (**msdyn_estimatelines**)                          | 1.0.0.3        | Initial Sync **NOT REQUIRED** | 10.0.42 or later                      |
| Project Operations integration entity for hour estimates <br> (**msdyn_resourceassignments**)                       | 1.0.0.6        | Initial Sync **NOT REQUIRED** | 10.0.38 or later                      |
| Project Operations integration project expense categories export entity <br> (**msdyn_expensecategories**)          | 1.0.0.1        | Initial Sync **NOT REQUIRED** |                                       |
| Project Operations integration project expenses export entity <br> (**msdyn_expenses**)                             | 1.0.0.5        | Initial Sync **NOT REQUIRED** | 10.0.42 or later                      |
| Project Operations integration project vendor invoice export entity <br> (**msdyn_projectvendorinvoices**)          | 1.0.0.1        | Initial Sync **NOT REQUIRED** | 10.0.29 or later                      |
| Project Operations integration project vendor invoice line export entity <br> (**msdyn_projectvendorinvoicelines**) | 1.0.0.9        | Initial Sync **NOT REQUIRED** | 10.0.42 or later                      |
| Project Operations integration project vendor invoice export entity V2 <br> (**msdyn_projectvendorinvoices**)       | 1.0.0.1        | Initial Sync **NOT REQUIRED** | 10.0.42 or later                      |

| Entity map | Latest version | Initial sync | Required Dynamics 365 Finance version |
| --- | --- | --- | --- |
| Project resource roles for all companies (bookableresourcecategories) | 1.0.0.1 | Requires an initial synchronization for the table map to sync the Project Manager and Team member resource roles that are populated in the Dynamics 365 Dataverse environment during provisioning. Dataverse is the main source for the initial synchronization. ||
| Integration entity for project transaction relationships (msdyn\_transactionconnections) | 1.0.0.0 | Not required for provisioning. ||
| Project contract headers (salesorders) | 1.0.0.1 | Not required for provisioning. ||
| Project contract lines (salesorderdetails) | 1.0.0.1 | Not required for provisioning. | 10.0.42 or later |
| Project funding source (msdyn_projectcontractsplitbillingrules) | 1.0.0.2 | Not required for provisioning. ||
| Projects V2 (msdyn\_projects) | 1.0.0.2 | Not required for provisioning. ||
| Project tasks (msdyn\_projecttasks) | 1.0.0.4 | Not required for provisioning. ||
| Project transaction categories (msdyn\_transactioncategories) | 1.0.0.0 | Not required for provisioning. ||
| Project integration table for material estimates (msdyn\_estimatelines) | 1.0.0.0 | Not required for provisioning. ||
| Project invoice proposals V2 (invoices) | 1.0.0.3 | Not required for provisioning. ||
| Project Operations integration actuals (msdyn_actuals) | 1.0.0.18 | Not required for provisioning. |10.0.39 or later|
| Project Operations integration contract line milestones (msdyn_contractlinescheduleofvalues) | 1.0.0.6 | 10.0.42 or later ||
| Project Operations integration entity for expense estimates (msdyn_estimatelines) | 1.0.0.3 | Not required for provisioning. | 10.0.42 or later |
| Project Operations integration entity for hour estimates (msdyn_resourceassignments) | 1.0.0.6 | Not required for provisioning. |10.0.38 or later|
| Project Operations integration project expense categories export entity (msdyn_expensecategories) | 1.0.0.1 | Not required for provisioning. ||
| Project Operations integration project expenses export entity (msdyn_expenses) | 1.0.0.5 | Not required for provisioning. | 10.0.42 or later |
| Project Operations integration project vendor invoice export entity (msdyn_projectvendorinvoices) | 1.0.0.2 | Not required for provisioning. |10.0.29 or later|
| Project Operations integration project vendor invoice line export entity (msdyn_projectvendorinvoicelines) | 1.0.0.8 | Not required for provisioning. | 10.0.42 or later |
| Project Operations integration project vendor invoice export entity V2 (msdyn_projectvendorinvoices) | 1.0.0.1 | Not required for provisioning.  | 10.0.42 or later |


Complete the following steps to run the listed maps.

1. Enable the Project resource roles for the **Project resource roles for all companies (bookableresourcecategories)** table map, because this map requires the initial synchronization. In the **Master for initial sync** field, select **Microsoft Dataverse**. 

    ![Resource role table map sync.](media/6ResourceInitialSync.jpg)

    Wait until the status of the map is **Running** before you move on to the next step.

2. Select all the remaining required maps. You can filter the maps in the Dual-write map list by entering the keyword **Project** in the search field in the upper-right corner. You can multi-select all maps and then run them. For more information, see [Manage multiple table maps](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/multiple-entity-maps). Make sure that you also enable and run related entity maps.

    > [!NOTE]
    > If you receive a "Project validation failed" message while you're running all the maps simultaneously, select the relevant map, and then select **Refresh tables**.
    >
    > ![Refresh tables button.](media/6RefreshTables.jpg)

3. With the 10.0.40 and later Dual-write maps release, a change was made to add a new required key for references to Bookable Resource that is required for several maps. From the **Dual-write** page, select into **Integration key**. In the first column next to **Bookable Resource**, add bookableresourceid [Bookable Resource] and Select **Save**.

The following maps are optional for a Project Operations solution.

| Entity map | Latest version | Initial sync | Required Dynamics 365 Finance version |
| --- | --- | --- | --- |
| Project worker resource import (bookableresources) | 1.0.0.1 | Not required for provisioning |10.0.39 or later|

### Project Operations Dual-write map versions

Always run the latest version of the map in your environment. Certain features and capabilities might not work correctly if any of the following conditions exist:

- A map isn't activated.
- The latest version of the map isn't activated. 
- Related table maps aren't activated.

You can view the active version of the map on the **Dual-write** page. The **Version** column indicates which version is active. Activate a new version of the map by selecting **Table map versions**, selecting the latest version, and then saving the selected version. If you've customized an out-of-box table map, you must reapply the changes. For more information, see [Application lifecycle management](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/app-lifecycle-management).
