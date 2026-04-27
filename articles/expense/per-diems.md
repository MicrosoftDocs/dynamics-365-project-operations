---
title: Per diems
description: Learn how to configure and manage per diem rules in Expense management. Discover how to set rates, apply reductions, and streamline travel expense reporting.
author: mukumarm
ms.author: mukumarm
ms.date: 02/04/2026
ms.topic: concept-article
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Configure and manage per diems

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

A per diem is an allowance that you pay to a worker who travels for work. In Expense management, you can create per diem rules for various travel situations. Per diem rates can be based on the time of year, the travel location, or both. When you create a per diem rule, you can specify that a percentage of the per diem rate is withheld if a worker receives complimentary meals or services. You can also set a minimum and maximum number of hours that the per diem rate applies to a worker's travel.

## Configuration

To configure per diems, follow these steps:

1. To add per diem locations, go to **Set up** > **Calculations and codes** > **Per diem locations**.
1. For each location, select a per diem rate and currency that's valid between a specific start and end date for hotel, meals, and other expenses. Configure per diem rates and currencies under **Set up** > **Calculations and codes** > **Per diems**.
1. On the **Per diem locations** page, configure per diem rate tiers. Per diem rate tiers define the percentage split of a daily allowance for hotel, meal, and other expenses.
1. To specify the meal percentage reduction for breakfast, lunch, or dinner, update the fields on the **Expense management parameters** page on the **Per diem** tab.

## Submit expenses using per diem

To submit expenses that use per diems, use the **Per diem** expense category when you create an expense report.
Enter the **Per diem from date**, **Per diem to date**,  and the **Per diem location**.
The system calculates the amount based on the per diem rates for the selected location. The meal reduction is calculated based on the per diem rate tiers.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
