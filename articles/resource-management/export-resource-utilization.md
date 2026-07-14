---
title: Export resource utilization data to Excel
description: Learn about exporting resource utilization data to Excel from the Resource Utilization board in Dynamics 365 Project Operations.
author: dishantpopli
ms.author: dishantpopli
ms.date: 05/11/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Export resource utilization data to Excel

[!INCLUDE [banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

The export to Excel feature on the Resource Utilization board helps resource managers export utilization data for bookable resources into an Excel file. You can apply filters to narrow the resource set. The export reflects the current time period view and filters on the board.

## Export utilization data

To export utilization data, follow these steps:

1. Go to **Resource Utilization**.

   The Resource Utilization board opens, displaying utilization data for bookable resources.

1. In the left navigation pane, apply filters to narrow the resources you want to export. Available filters include:

   - **Characteristics - Rating**
   - **Role**
   - **Territories**
   - **Organizational Units**
   - **Resource Types**
   - **Pool Types**
   - **Teams**
   - **Business Units**

1. Select the time period view (daily, weekly, or monthly) that you want reflected in the export.

   > [!NOTE]
   > The export respects the time period view on the board. The exported data matches the granularity you see on screen.

1. On the toolbar, select the **Export to Excel** icon.

   The system starts preparing the data for download. The export includes utilization data for all resources that match your current filters.

   > [!IMPORTANT]
   > You can run only one export at a time. Wait for the current export to complete before starting another.

1. When the data is ready, you receive a notification indicating that the file is ready for download.

1. Select **Download** to download the Excel file.

## Exported data columns

The following table describes the columns included in the exported Excel file.

| Column | Description |
| ------ | ----------- |
| **Date** | The date or period for the utilization data row. |
| **Bookable Resource** | The name of the resource. |
| **Resource Capacity** | Total available capacity hours for the resource in the period. |
| **Total Book Hours** | Total booked hours for the resource in the period. |
| **Chargeable Time Actuals** | Hours logged as chargeable time actuals. |
| **Non Chargeable Time Actuals** | Hours logged as nonchargeable time actuals. |
| **Internal Time Actuals** | Hours logged as internal time actuals. |
| **Billable Utilization** | Percentage of capacity used for billable (chargeable) work. |
| **Non Billable Utilization** | Percentage of capacity used for nonbillable work. |
| **Internal Utilization** | Percentage of capacity used for internal work. |
| **Total Utilization** | Overall utilization percentage across all work types. |
| **Booking %** | Percentage of capacity that is booked. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
