---
# required metadata

title: New Quote form experience
description: This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.
author: poojafandan
ms.date: 1/3/2025
ms.topic: article
ms.custom: bap-template
ms.reviewer: johnmichalak
ms.author: poojafandan
---

# New Quote form experience

_**Applies To:** Project Operations Integrated with ERP, Project Operations Core_

This article provides information about the updates to the project quotes form in Microsoft Dynamics 365 Project Operations.

We're releasing the initial version of our new quote experience. The goal is to improve the overall user experience, uptake new platform capabilities, and simplify user interactions when a quote is created.

Here are some of the features:

- A new, clean experience that uses a single form layout
- A new key performance indicator (KPI) control that highlights key quote metrics
- A reduction in the number of form interactions
- Scenario-focused data views

## Usage changes

The number of tabs in the **Quote** form was significantly reduced. This section describes the changes and where to find them.

### Summary tab

All the related tabs for the quote are moved to the **Summary** tab. The quote summary tab provides a comprehensive view of a quote’s financial health, including customer budget, profitability, scheduled delivery date, and cost-revenue breakdown over time. This page enables you to track and manage quote details efficiently, ensuring alignment with project financial and business objectives.

### Project Lines tab

The **Project Lines** tab allows you to view project quote lines and the attached quote line details within the same grid, with the latter appearing in an expandable, nested grid.

For each quote line, you have details on the billing method, invoice schedule type, project association, and budget performance that includes transaction classes, discount and fee, margin percentage, and extended amount for the quote line. Expanding the quote line displays all the quote line details under the quote line.

You can create a new quote line or delete an existing line from this view. You can also import the project estimates for a quote line to create new quote line details directly from this view. You can also manually create new quote line details directly from this tab.

When you select the quote line details, you can edit or delete the line details. To view the cost detail, select **Open cost detail**.

To create price overrides for time transaction line details, select the line detail, and then the price override button. You can create a price override within the Quote and Quote Line forms.


### Product Lines tab

The **Product Lines** tab includes all the product capabilities, so that you can add product-based quote lines for the project.

### Pricing tab

In this tab, you can view all the price lists that are used in the quote.

### Analytics tab

The **Analytics** tab is a replica of the out-of-box **Analytics** tab, where you can do a deep dive into the data behind the quote.

Along with key performance indicators, such as total chargeable and nonchargeable costs, total amount, gross margin, and adjusted gross margin, you can view the amount by transaction class and customer budget comparison charts.

To update the KPIs, select **Recalculate** on the quote.


## Use role price override within Quote and Quote Line form
The Price Override button, integrated into the Quote and Quote Line form, facilitates the modification of price overrides for quote line details. This functionality significantly reduces the number of clicks and streamlines the process of adjusting prices while maintaining focus within the context of each specific quote line detail.

**Usage Instructions:**
Select the quote line detail that requires price adjustment. To initiate the price modification process, select **Price Override**. A flyout appears allowing you to edit the price while retaining the context of the quote line detail.

**Functionality:**
If an existing price override exists, the new price is automatically updated. In cases where no existing override is present, a new price override is updated. The Price Override button illuminates only if the price you're editing is sourced from the role price list.

**More information:**
The scope of the price override is automatically configured to the respective quote. 




[!INCLUDE[footer-include](../includes/footer-banner.md)]
