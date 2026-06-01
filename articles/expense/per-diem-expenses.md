---
title: Per diem expenses
description: Learn how to configure and manage per diem expenses, including lodging, meals, and incidentals, in Microsoft Dynamics 365 Finance. Follow step-by-step instructions.
author: suvaidya
ms.author: nshrivastava
ms.date: 01/23/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak
---

# Per diem expenses

[!INCLUDE[banner](../includes/banner.md)]

A per diem payment is a fixed, predetermined daily allowance that a company pays to its employees for lodging (hotels), meals, and incidental expenses that those employees incur while they travel for work. The company pays this allowance to the employees instead of paying the actual travel expenses. Employees can use their **Incidentals/Other** per diem allowance to cover tips, room service, laundry, or dry-cleaning services for important business meetings. The per diem rate can vary, depending upon whether the employer chooses to reimburse for the combined cost of lodging and meals, or only for the cost of meals and incidentals.

Per diem rates can be based on the time of year, the travel location, or both. When you create a per diem rule, specify that a percentage of the per diem rate is withheld if an employee receives complimentary meals or services. You can also set a minimum number of hours and a maximum number of hours that the per diem rate applies to an employee's travel.

The per diem is calculated as the total allowance that is offered per day minus the meal reduction (cost of complimentary meals) that is provided to the employee.

## Configure per diems

To configure per diem expenses, follow these steps:

1. Go to **Expense management** \> **Setup** \> **General** \> **Expense management parameters**.
1. On the **Per diem** tab, in the **Calculate meal reduction by** field, select how per diems should be calculated:

    - **Meal type per trip** – Calculate the per diem based on the type of meal that is entered (breakfast, lunch, or dinner) and on the meal reduction that you specify for each meal type for the per diem allowance during the trip.
    - **Meal type per day** – Calculate the per diem based on the type of meal that is entered and on the meal reduction that you specify for each meal type for the per diem allowance per day.
    - **Number of meals per day** – Calculate the per diem based on the number of meals that are entered per day and on the meal reduction for the number of meals that are provided each day.

1. Go to **Expense management** \> **Setup** \> **Calculations and codes** \> **Per diem locations**.
1. Add locations where per diems can be used.
1. For each location that you add, on the **Per diems** tab, select the per diem rate and currency that are valid between specific start and end dates for lodging, meals, and other expenses. To configure per diem rates and currencies, go to **Expense management** \> **Setup** \> **Calculations and codes** \> **Per diems**.

## Per diems in the reimagined expense interface

The reimagined **Expense Management** workspace in Microsoft Dynamics 365 Finance version 10.0.25 and later supports the per diem feature.

To enable per diems, follow these steps:

1. In the **Feature Management** workspace, find and select the **Expense Reports Reimagined** feature in the list, and then select **Enable now**.
1. Find and select the **Per-diem for expense report re-imagined interface** feature in the list, and then select **Enable now**.

## How the feature works

This section provides examples for three configuration scenarios. For each example, the **Calculate meal reduction by** field is set to a different value. For all three examples, the total amount that you pay is the same until the meal reduction is applied. After that point, the total amount payable differs for each example.

To create the per diem expense that you use for all three examples, follow these steps:

1. Go to **Workspaces** \> **Expense Management**.
1. Select **New expense report**, or select an existing expense report.
1. Add a new expense. In the **Category** field, select **Per diem**. Select the location, and the start and end dates of your trip. The per diem for lodging, meals, and incidentals (other expenses) is calculated based on the daily allowance that you set for the selected location.

    For example, you select **Redmond (USA)** as the location. The daily allowance for that location is 150 US dollars (USD 150) for lodging, USD 75 for meals, and USD 5 for incidentals. You select January 10 as the start date, and January 14 as the end date. Therefore, the selected duration is five days when the configuration selected is calendar days with time, and the selected time begins and ends at 12:00 am on the start and end dates. Here are the calculations:

    - Total amount payable = 5 × (150 + 75 + 5) = 5 × 230 = USD 1,150
    - Meal and incidental portion of the total amount = 5 × (75 + 5) = USD 400

If breakfast, lunch, and dinner are provided during the trip, you must account for those meals as a meal reduction.

### Example 1: Per diem where meal reductions are based on meal type per trip

In this example, the meal reduction is 30 percent for breakfast, 30 percent for lunch, and 40 percent for dinner. On the **Expense management parameters** page, the **Calculate meal reduction by** field is set to **Meal type per trip**. Here are the calculations if three breakfasts, two lunches, and zero dinners were provided to the employee:

- Meal reduction = (3 × \[75 × 30%\]) + (2 × \[75 × 30%\]) + 0 = (3 × 22.50) + (2 × 22.50) + 0 = 67.50 + 45 + 0 = USD 112.50
- Meals and incidentals = 400 – 112.50 = USD 287.50
- Total amount payable = Total allowance – Meal reduction = 1,150 – 112.50 = USD 1,037.50

:::image type="content" source="media/1-meal-type-per-trip.png" alt-text="Screenshot of per diem expense where the meal reduction is based on meal type per trip.":::

###	Example 2: Per diem where meal reductions are based on meal type per day

In this example, the meal reduction is 30 percent for breakfast, 30 percent for lunch, and 40 percent for dinner. On the **Expense management parameters** page, the **Calculate meal reduction by** field is set to **Meal type per day**. In this case, in the **Meals** grid in the **Edit expense** dialog box, you clear checkboxes to indicate which meals were provided to you during your trip.

For example, here are the calculations if breakfast was provided for the first three days of the trip:

- Daily meal reduction for each of the first three days = 75 × 30% = USD 22.50
- Total meal reduction = 3 × 22.50 = USD 67.50
- Meals and incidentals for days 1 through 3 = 75 – 22.50 = USD 57.50
- Total meals and incidentals = Sum of meals and incidentals across five days = 400 – 67.50 = USD 332.50
- Total amount payable = Total amount – Meal reduction = 1,150 – 67.50 = USD 1,082.50

:::image type="content" source="media/2-meal-type-per-day.png" alt-text="Screenshot of per diem expense where the meal reduction is based on meal type per day.":::

### Example 3: Per diem where meal reductions are based on number of meals per day

In this example, the meal reduction is calculated based on the number of meals that are provided each day (that is, the **Calculate meal reduction by** field on the **Expense management parameters** page is set to **Number of meals per day**). In the **Meals** grid in the **Edit expense** dialog box, you clear checkboxes to indicate which meals are provided.
In this case, the meal reduction is based only on the number of meals provided, and not on the type of meal (breakfast, lunch, or dinner) provided.

Here are the calculations for per diems when the daily allowance is USD 150 for lodging, USD 75 for meals, and USD 5 for incidentals:

- **Total amount payable** = 5 × (150 + 75 + 5) = 5 × 230 = USD 1,150
- **One meal:** Meal reduction = 20% = USD 15
- **Two meals:** Meal reduction = 50% = USD 37.50
- **Three meals:** Meal reduction = 100% = USD 75

Here are the calculations for the **meals and incidentals allowance**, which includes USD 5 for incidentals:

- Day 1 - Two meals provided = (75 – 37.50) + 5 = 37.50 + 5 = USD 42.50
- Day 2 - Two meals provided = (75 – 37.50) + 5 = 37.50 + 5 = USD 42.50
- Day 3 - One meal provided = (75 – 15) + 5 = 60 + 5 = USD 65
- Day 4 - Zero meals provided = (75-0) + 5 = 75 + 5 = USD 80
- Day 5 - Three meals provided = (75 – 75) + 5 = 0 + 5 = USD 5

- Total meals and incidentals = Meals and Incidentals for Day 1 + Day 2 + Day 3 + Day 4 + Day 5 = USD 235
- Total meal reduction = Meal reduction for Day 1 + Day 2 + Day 3 + Day 4 + Day 5 = 37.5 + 37.5 + 15 + 0 + 75 = USD 165
- Total amount payable = Total allowance – Total meal reduction = USD 1,150 – USD 165 = USD 985

:::image type="content" source="media/3-number-of-meals-per-day.png" alt-text="Screenshot of per diem expense where the meal reduction is based on number of meals per day.":::

> [!NOTE]
> As of Finance version 10.0.23, if you use the reimagined expense interface, you can't create per diem expenses that have overlapping dates. If you try, you receive an error message.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
