---
title: Set up mileage using mileage rate tiers
description: This article provides information about mileage rates and mileage rate tiers.
author: mukumarm
ms.author: mukumarm
ms.date: 07/17/2024
ms.topic: how-to
ms.custom: 
  - bap-template
ms.reviewer: johnmichalak

---

# Set up mileage using mileage rate tiers

[!INCLUDE[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

When an expense is reported and the selected expense category is **Mileage**, the amount for that expense line is calculated according to the *rate per mileage* amount. This amount is determined by using defined mileage tiers or, if no mileage rate tiers are set up, by following a standard rate of mileage. 

Mileage rate tiers can be set up by going to **Expense Management** > **Setup** > **General** > **Expense categories** > **Mileage** > **Category setup**.

After you upgrade to version 10.0.18, if your organization uses the mileage expense category, consider enabling the mileage feature after reviewing the design changes. 

The new design of mileage rate tiers impacts how the value in the **Quantity** field is processed. Prior to the release of 10.0.18, the value in the **Quantity** field was considered to be the lower limit. When accumulation crossed that value, the corresponding rate was used. As of 10.0.18, the value in the **Quantity** field is considered the upper limit. The corresponding rate is used when mileage accumulation is less than the value in the **Quantity** field. The new model for mileage tiers helps with consistency across mileage tiers and better usability.   

All approved expense reports are recalculated during posting according to the new design.

## Example
 
### Before version 10.0.18
With two mileage rate tiers, the **Quantity** field in each tier represents the lower mileage limit. Currently, tier one has a value of zero (0) and a rate of 0.45, and tier two has a value of 1000 and a rate of 0.25. If the accumulated miles or kilometers crosses the value in the field, the related rate is used. If there's no line with zero quantity, the system uses the rate of mileage that is defined in Expense management. 
 
If an employee submits an expense report with 1,500 miles, the two mileage lines on the posted expense report would be: 1000 (rate 0.45) +  500 (rate 0.25) = 575.00.

### After version 10.0.18
In 10.0.18, the **Quantity** field in each tier represents the upper limit of the tier. Currently, tier one has a value of 999 and a rate of 0.45, and tier two has a value of 999,999,999.00 and a rate of 0.25. If the accumulated miles or kilometers crosses the value in the **Quantity** field, the related rate is used. If all upper limits are exceeded, the system uses the rate of mileage that is defined in Expense management. 
 
To correctly calculate the same scenario, the tier set up must be changed. The **Quantity** field in tier one has a value of 999.00 and a value of 999,999,999.00 in tier two. If an employee exceeds the total quantity of miles or kilometers in tier one, the system uses the rate of mileage that is defined in Expense management. 
  
If an employee submits an expense report with 1,500 miles, the two mileage lines on the posted expense report would be: 1000 (rate 0.45) +  500 (rate 0.25) = 575

## Enable the Mileage calculation improvements when using mileage rate tiers feature

The **Mileage calculation improvements when using mileage rate tiers** feature improves mileage rate calculation. To enable this feature, follow these steps.

1. Go to **Workspaces** > **Feature Management**. 
2. In the list, locate and select **Mileage calculation improvements when using mileage rate tiers**, and then select **Enable now**.

After you enable the feature, reset the mileage tiers to correctly reflect the value of the **Quantity** field. 

## Enable the Mileage totals calculation by fiscal year feature

The **Mileage totals calculation by fiscal year** feature enables a new setting in Expense management parameters that performs mileage totals calculations by fiscal year instead of calendar year. Complete the following steps to enable this feature.

1. Go to **Workspaces** > **Feature Management**.
1. In the list, locate and select **Mileage totals calculation by fiscal year**, and then select **Enable now**.
1. Go to **Expense Management** > **Setup** > **General** > **Expense management parameters**.
1. On the **Expense management parameters** page, locate and enable **Use fiscal year for mileage totals**.

After you enable **Use fiscal year for mileage totals**, mileage totals are calculated by fiscal year.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
