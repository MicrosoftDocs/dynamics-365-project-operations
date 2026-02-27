---
title: Set up mileage using mileage rate tiers
description: This article provides information about mileage rates and mileage rate tiers.
author: mukumarm
ms.author: mukumarm
ms.date: 02/27/2026
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up mileage by using mileage rate tiers

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

When a user reports an expense and selects the **Mileage** expense category, the system calculates the amount for that expense line according to the *rate per mileage* amount. The system determines this amount by using defined mileage tiers or, if you don't set up mileage rate tiers, by following a standard rate of mileage. 

Set up mileage rate tiers by going to **Expense Management** > **Setup** > **General** > **Expense categories** > **Mileage** > **Category setup**.

After you upgrade to version 10.0.18, if your organization uses the mileage expense category, consider enabling the mileage feature after reviewing the design changes. 

The new design of mileage rate tiers impacts how the system processes the value in the **Quantity** field. Prior to the release of 10.0.18, the system considered the value in the **Quantity** field to be the lower limit. When accumulation crossed that value, the system used the corresponding rate. As of 10.0.18, the system considers the value in the **Quantity** field to be the upper limit. The system uses the corresponding rate when mileage accumulation is less than the value in the **Quantity** field. The new model for mileage tiers helps with consistency across mileage tiers and better usability.   

The system recalculates all approved expense reports during posting according to the new design.

## Example
 
### Before version 10.0.18
With two mileage rate tiers, the **Quantity** field in each tier represents the lower mileage limit. Currently, tier one has a value of zero (0) and a rate of 0.45, and tier two has a value of 1,000 and a rate of 0.25. If the accumulated miles or kilometers crosses the value in the field, the system uses the related rate. If there's no line with zero quantity, the system uses the rate of mileage that is defined in Expense management. 
 
If an employee submits an expense report with 1,500 miles, the two mileage lines on the posted expense report are: 1,000 (rate 0.45) +  500 (rate 0.25) = 575.00.

### After version 10.0.18
In 10.0.18, the **Quantity** field in each tier represents the upper limit of the tier. Currently, tier one has a value of 999 and a rate of 0.45, and tier two has a value of 999,999,999.00 and a rate of 0.25. If the accumulated miles or kilometers crosses the value in the **Quantity** field, the system uses the related rate. If all upper limits are exceeded, the system uses the rate of mileage that is defined in Expense management. 
 
To correctly calculate the same scenario, change the tier set up. The **Quantity** field in tier one has a value of 999.00 and a value of 999,999,999.00 in tier two. If an employee exceeds the total quantity of miles or kilometers in tier one, the system uses the rate of mileage that is defined in Expense management. 
  
If an employee submits an expense report with 1,500 miles, the two mileage lines on the posted expense report are: 1,000 (rate 0.45) +  500 (rate 0.25) = 575.

## Enable the Mileage calculation improvements when using mileage rate tiers feature

The **Mileage calculation improvements when using mileage rate tiers** feature improves mileage rate calculation. To enable this feature, follow these steps:

1. Go to **Workspaces** > **Feature Management**. 
1. In the list, locate and select **Mileage calculation improvements when using mileage rate tiers**, and then select **Enable now**.

After you enable the feature, reset the mileage tiers to correctly reflect the value of the **Quantity** field. 

## Enable the Mileage totals calculation by fiscal year feature

The **Mileage totals calculation by fiscal year** feature enables a new setting in Expense management parameters that performs mileage totals calculations by fiscal year instead of calendar year. Complete the following steps to enable this feature.

1. Go to **Workspaces** > **Feature Management**.
1. In the list, locate and select **Mileage totals calculation by fiscal year**, and then select **Enable now**.
1. Go to **Expense Management** > **Setup** > **General** > **Expense management parameters**.
1. On the **Expense management parameters** page, locate and enable **Use fiscal year for mileage totals**.

After you enable **Use fiscal year for mileage totals**, mileage totals are calculated by fiscal year.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
