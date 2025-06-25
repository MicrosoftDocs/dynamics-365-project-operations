---
title: Per diems
description: This article provides information about the per diem rules that are used in Expense management.
author: mukumarm
ms.author: mukumarm
ms.date: 05/24/2024
ms.topic: article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Per diems

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_


A per diem is an allowance that is paid to a worker who is traveling for work. In Expense management, you can create per diem rules for  various travel situations. Per diem rates can be based on the time of year, the travel location, or both. When you create a per diem  rule, you can specify that a percentage of the per diem rate will be withheld if a worker receives complimentary meals or services. You can also set a minimum and maximum number of hours that the per diem rate can apply to a worker's travel.

## Configuration 

1. To add per diem locations, go to **Set up** > **Calculations and codes** > **Per diem locations**.
2. For each of the locations added above, select a per diem rate and currency that is valid between a specific start and end date for hotel, meals, and other expenses. Per diem rates and currencies are configured under **Set up** > **Calculations and codes** > **Per diems**.
3. On the **Per diem locations** page, configure per diem rate tiers. Per diem rate tiers allow you to define the percentage split of a daily allowance for hotel, meal, and other expenses. 
4. To specify the meal percentage reduction for breakfast, lunch, or dinner, update the fields on the **Expense management parameters** page on the **Per diem** tab. 
	
## Submit expenses using per diem
To submit expenses utilizing per diems, use the **Per diem** expense category when you create an expense report. 
Enter the **Per diem from date**, **Per diem to date**,  and the **Per diem location**. 
The amount will be calculated based on the per diem rates for the selected location and meal reduction will be calculated based on the per diem rate tiers.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
