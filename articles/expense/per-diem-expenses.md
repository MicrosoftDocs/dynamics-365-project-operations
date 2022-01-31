---
# required metadata

title: Per diem expenses
description: This topic provides information about how to work with per diem expenses.
author: suvaidya
ms.date: 01/26/2022
ms.topic: article
ms.prod: 
#

# optional metadata

ms.search.form: 
audience: Application User
# ms.devlan: 
ms.reviewer: kfend
ms.search.scope: 
# ms.tgt_pltfrm: 
# ms.custom: 
ms.search.region: 
# ms.search.industry: 
ms.author: suvaidya
ms.search.validFrom: 
ms.dyn365.ops.version: 
---

# Per diem expenses

A Per diem is a fixed, pre-determined amount of money that a company pays to its employees who are traveling for work. 

As per the Internal Revenue Service (IRS), a per diem payment is a daily allowance paid by a company to its employees for lodging, meals, and incidental expenses that are incurred during travel. This allowance is paid to the employee instead of paying the actual travel expenses. Employees can use their **Incidentals/Other** per diem allowance to cover tips, room service, laundry, or dry-cleaning services for all-important business meetings. The per diem rate can differ depending upon whether the employer chooses to reimburse for the combined lodging and meal costs or if they choose to reimburse for only meals and incidentals.

Per diem rates can be based on the time of year, travel location, or both. When you create a per diem rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services. You can also set a minimum and maximum number of hours that the per diem rate can apply to a worker's travel.

The per diem calculation is the total allowance offered per day minus the meal reduction (cost of complimentary meals) provided to the employee. 

## Per diems in reimagined Expense interface 
The Per diem feature is supported in the reimagined **Expense** workspace in Dynamics 365 Finance version 10.0.25 and above.  

1. To enable per diems, go to the **Feature Management** workspace. 
2. In the list, first select the feature, **Expense Reports Reimagined** and then select **Enable now**.
3. In the feature list, locate and select **Per-diem for expense report re-imagined interface** and then select **Enable now**.

## Configure per diems
Complete the following steps to configure per diem expenses. 

1. Go to **Expense management parameters** > **Per diems**.
2. Select how the per diems should be calculated based on the following options: 

  - **Meal type per trip** – The per diem is calculated based on the type of meal entered (breakfast, lunch, or dinner), and the meal reduction specified for each meal tyoe for the per diem allowance for the duration of the trip. 
  - **Meal type per day** - The per diem is calculated based on the type of meal entered and the meal reduction specified for each meal type for the per diem allowance per day. 
  - **Number of meals per day** – The per diem is calculated based on the number of meals entered per day and the meal reduction for the number of meals provided per day.

2. Go to **Set up** > **Calculations and codes** > **Per diem locations** and add locations where per diems can be used.
3. For each location you add, on the **Per diems** tab, select a per diem rate and currency that is valid between a specific start and end date for hotel, meals, and other expenses. Per diem rates and currencies are configured by going to **Set up** > **Calculations and codes** > **Per diems**.

## How the feature works
The following is an example of the each of the three scenario configurations. The total amount is the same across all three scenarios until the meal reduction is applied based on the selected configuration. This will make the total amount payable difference in each scenario.

1. Create a new per diem expense, select the location, and provide the start and end dates. The per diem is calculated, for hotel, meals, and incidentals, based on the daily allowance set for the location you select. 

   For example, if you select Redmond (USA) as the location, if the daily hotel allowance is $150, meals are $75 and Incidentals (Other) is $5, then for the selected duration of 10th-14th January (five days, assuming calendar day with time) the calculation would be:

 - Total amount payable = 5 (150+75+5)  = 5* 230  =  1150 USD
 - Meals and incidentals portion of the total amount = 5(75+5) = 400 USD

  Now, if breakfast, lunch, and dinner were provided during the trip, those will need to be accounted for as meal reduction.

### Per diem is set to meal type per trip

In this example, meal reduction is 30% for breakfast, 30% for lunch and 40% for dinner. This means, for example that the three breakfasts, two lunches, and zero dinners that were provided to the employee can be calculated as:

  - Meal reduction = 3(30%*75) + 2(30%*75) + 0 =  3(22.5)+2(22.5) +0=  67.5+45 = 112.5 
  - Meals and incidentals = 400 USD- 112.5 USD = 287.5 USD 
  - Total amount = Total allowance - Meal reduction = 1150 USD – 112.5 USD = 1037.5 USD 

  ![Meal type per trip, per diem expense.](media/1-meal-type-per-trip.png) 


###	Per diem is set to meal type per day

In this example, meal reduction is 30% for breakfast, 30% for lunch, and 40% for dinner. When the per diem is set to **Meal type per day**, in the **Meals** grid, you can clear the check boxes to indicate which meals were provided to you during the trip.   

For example, when breakfast has been provided for the first three days of the trip,  the per day meal reduction on the first three days = 30% (75) = 22.5.

 - Total meal reduction = 3(22.5) = 67.5 USD  
 - Meals and incidentals for days 1-3 = 75-22.5 = 57.5 USD 

Total meals and incidentals is equal to the sum of meals and incidentals across five days = 400-67.5= 332.5 USD 
Total amount payable = total amount – meal reduction =  1150- 67.5 = 1082.5 USD

  ![Meal type per day, edit a per diem expense.](media/2-meal-type-per-day.png) 

### Per diem is set to number of meals per day

In this example, meal reduction is calculated based on the number of meals provided per day. These are the meals that would have unmarked check boxes in the **Meals** grid.
With this option selected, per diems are calculated as follows:

Hotel= $150, Meals =$75, Incidentals =$5
 
 - 1 meal – meal reduction = 20% = $15
 - 2 meals – meal reduction = 50% = $37.5
 - 3 meals – meal reduction = 100% = $75  

Meals and incidentals allowance which includes $5 for incidentals:

 - 1 meal =  $75-$15 =  $60+$5 = $65
 - 2 meals =  $75 -$37.5 =  $37.5 +$5 =  $42.5
 - 3 meals = $75- $75 =0 +$5 = $5 

Total meals and incidentals = sum (meals and incidentals/day) = 235 USD
Total amount = $Total allowance - Total meal reduction = 985 USD

  ![Numer of meals per day, edit per diem expense.](media/3-number-of-meals-per-day.png) 

> [!NOTE] 
> In the reimagined expense interface, starting in Finance version 10.0.23, you can't create per diem expenses with overlapping dates. If you try to do this, you will receive an error. 

