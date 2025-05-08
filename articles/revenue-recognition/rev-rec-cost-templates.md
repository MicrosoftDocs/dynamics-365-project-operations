---
title: Set up cost templates
description: This article provides information about how to create and use cost templates in Project Operations.
author:  sigitac
ms.date: 10/27/2023
ms.topic: how-to
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Set up cost templates

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

This article provides information about how to create and use cost templates in Project Operations. A cost template determines:

- The project categories for forecast and actual transactions to be included in a percentage of the project completion calculation. The percent-complete value is then used to calculate how much revenue is recognized.
- Whether the percentage of completion can be modified if it's automatically calculated.
- Whether the percent complete is calculated based on amounts or units.

## Cost template example

You are working on a web site design project for a customer in which you charge a flat fee of USD 10,000. You forecast that it will take 100 hours (USD 5,000) to complete the project. You also forecast two plane tickets and four nights in a hotel for trips to the customer's site (USD 1,800). This results in a total forecasted cost of USD 6,800.

When you run the fixed-price revenue recognition process to create an estimate at the end of the month, you find that you have worked 35 hours on the project. This doesn't yet include flights or hotel costs. You also had an assistant perform five hours of research for the project at a cost of USD 100, which you hadn't planned for.

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

- If you include unplanned hours in the cost template, you risk reaching 100 percent complete before the project is finished. This is because actual hours will be greater than planned hours. If you use either of the first two methods listed in the table, you should change the plan (forecasted units) when you become aware of deviations. In this case, you would add or subtract hours based on your knowledge of what is required to finish the project. If the project will require another 65 hours to complete, you would add five hours to the plan for a total of 105. If you know that your assistant will perform another five hours of research, the total will become 110 hours.
- If you use the third method listed in the table, you would only update the planned hours for your own time to keep the percent-complete calculation accurate. Your profitability will change when unplanned hours are logged, but you will remain on a known percent-complete trajectory.
- If you use the fourth method listed in the table, the risk is that expenses will occur at irregular times and may not be reflected in your completion progress. Therefore, if the expenses are included, they can cause your percent complete to fluctuate more than is desirable. For example, because you didn't take a flight yet, your percent complete was 27 percent instead of 35 percent or 37 percent if you were to base the calculation on time alone. If you had taken one trip for two nights and forecasted your flight and hotel costs accurately, the percent complete would have been 40.4 percent (USD 1850 for labor and USD 900 for expenses = USD 2750/USD 6800 = 40.4 percent). Therefore, incurring the expenses for just one plane trip would change the percent complete from 27 percent to 40 percent.

## Create cost templates
To create cost templates, follow these steps:

1. To access cost templates, in the Dynamics 365 Finance environment, go to **Project management and accounting** > **Setup** > **Estimates** > **Cost template**.
2. Select **New** to create new cost template. Enter a name and description.
3. Provide cost line ID for each transaction type.
4. Select a default completion method:

  - **Automatic**: Percentage of completion is calculated automatically on a project. The resulting value can't be changed.
  - **Manual**: Percentage of completion is calculated automatically on a project. The resulting value can be changed.

  > [!NOTE]
  > For manual calculations, the percentage of completion is maintained in **Manual calculation** on the **General** tab on the **Estimate** page.

5. In **Completion based on**, select one of the following values:

  - **Amount**: The amount in accounting currency calculates the percentage of completion.
  - **Unit**: The quantity calculates the percentage of completion.
  - **Straight line**: The system calculates the percentage of completion on a proportionate basis by using the project start and end dates to determine the length of the project.

6. Select **Cost lines** to review the cost lines of the cost template. At least one cost line is required for every transaction type. However, you can create multiple cost lines for the same transaction types and set the desired attributes for these lines.
7. On the **Categories** tab, select the project categories to be included on the cost template line.
8. On the **General** tab, select if this line will be included in the percentage of completion calculation.
9. Select the cost to complete method to be used when calculating the percentage of completion.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
