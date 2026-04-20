---
title: Set up cost templates
description: Learn how to create and use cost templates in Project Operations to calculate project completion percentages and manage revenue recognition effectively.
author: sigitac
ms.date: 01/30/2026
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Set up cost templates

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

 > [!NOTE]
   > In a recent product update, the **Update labels for revenue recognition and related forms and processes in Project Operations** feature renames estimates to revenue recognition. Depending on whether the feature is enabled, terminology might reference either estimate or revenue recognition.

This article explains how to create and use cost templates in Project Operations. A cost template determines:

- The project categories for forecast and actual transactions that the template includes in the percentage of the project completion calculation. The percent-complete value is used to calculate how much revenue is recognized.
- Whether you can modify the percentage of completion if it's automatically calculated.
- Whether the percent complete is calculated based on amounts or units.

## Cost template example

You're working on a web site design project for a customer in which you charge a flat fee of USD 10,000. You forecast that it takes 100 hours (USD 5,000) to complete the project. You also forecast two plane tickets and four nights in a hotel for trips to the customer's site (USD 1,800). This forecast results in a total forecasted cost of USD 6,800.

When you run the fixed-price revenue recognition process to create an estimate at the end of the month, you find that you worked 35 hours on the project. This count doesn't yet include flights or hotel costs. You also had an assistant perform five hours of research for the project at a cost of USD 100, which you hadn't planned for.

When you calculate the percent complete value for this project, you have the following choices to make:

- Do you want to include all costs (hours and expenses) or just hours?
- Do you want to include all hours or only planned hours?
- Do you want to calculate the percent complete based on the dollar cost of the planned hours (USD 5,000) or just on the number of hours (100)?

Your answers to these questions determine the options that you set on the cost template and the categories that you select on the cost template lines.

The following table illustrates the results of different methods of calculating the percent-complete value for this scenario.

| Completion based on | Dollar cost or units | Percent complete | Calculation |
| --- | --- | --- | --- |
| All hours, no expenses | Dollar cost | 37% 35 x USD 50 + USD 100 = USD 1,850 USD 1,850/USD 5,000 |
| All hours, no expenses | Units | 40% | 40 hours/100 hours (including five unplanned hours) |
| Planned hours, no expenses | Dollar cost or unit | 35% | 35/100 hours or 35 x USD 50/5,000 |
| All hours and expenses | Dollar cost | 27.2% | USD 1,850/USD 6,800 |

Deciding which approach to take to create a cost template can depend on several considerations:

- If you include unplanned hours in the cost template, you risk reaching 100 percent complete before the project is finished. This risk happens because actual hours are greater than planned hours. If you use either of the first two methods listed in the table, change the plan (forecasted units) when you become aware of deviations. In this case, add or subtract hours based on your knowledge of what is required to finish the project. If the project requires another 65 hours to complete, add five hours to the plan for a total of 105. If you know that your assistant will perform another five hours of research, the total becomes 110 hours.
- If you use the third method listed in the table, update the planned hours for your own time to keep the percent-complete calculation accurate. Your profitability changes when unplanned hours are logged, but you remain on a known percent-complete trajectory.
- If you use the fourth method listed in the table, the risk is that expenses occur at irregular times and might not be reflected in your completion progress. Therefore, if you include expenses, they can cause your percent complete to fluctuate more than is desirable. For example, because you didn't take a flight yet, your percent complete was 27 percent instead of 35 percent or 37 percent if you were to base the calculation on time alone. If you took one trip for two nights and forecasted your flight and hotel costs accurately, the percent complete would have been 40.4 percent (USD 1850 for labor and USD 900 for expenses = USD 2750/USD 6800 = 40.4 percent). Therefore, incurring the expenses for just one plane trip changes the percent complete from 27 percent to 40 percent.

## Create cost templates

To create cost templates, follow these steps:

1. To access cost templates, in the Dynamics 365 Finance environment, go to **Project management and accounting** > **Setup** > **Estimates** > **Cost template**.
1. Select **New** to create a new cost template. Enter a name and description.
1. Provide cost line ID for each transaction type.
1. Select a default completion method:

- **Automatic**: Percentage of completion is calculated automatically on a project. You can't change the resulting value.
- **Manual**: Percentage of completion is calculated automatically on a project. You can change the resulting value.

  > [!NOTE]
  > For manual calculations, maintain the percentage of completion in **Manual calculation** on the **General** tab on the **Estimate** page.

1. In **Completion based on**, select one of the following values:

- **Amount**: The amount in accounting currency calculates the percentage of completion.
- **Unit**: The quantity calculates the percentage of completion.
- **Straight line**: The system calculates the percentage of completion on a proportionate basis by using the project start and end dates to determine the length of the project.

1. Select **Cost lines** to review the cost lines of the cost template. At least one cost line is required for every transaction type. However, you can create multiple cost lines for the same transaction types and set the desired attributes for these lines.
1. On the **Categories** tab, select the project categories to include on the cost template line.
1. On the **General** tab, select if this line is included in the percentage of completion calculation.
1. Select the cost to complete method to use when calculating the percentage of completion.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
