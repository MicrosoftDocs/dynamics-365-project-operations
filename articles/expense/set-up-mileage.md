---
title: Set up expense categories
description: This topic provides information about how to set up expense categories and shared categories for expense reports.
author: suvaidya
ms.date: 05/18/2021
ms.topic: article
ms.reviewer: kfend 
ms.author: suvaidya
---

# Set up Mileage using Mileage Rate Tiers

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

When the employee reports expenses with "mileage" expense category, the amount for that expense line is calculated according to the “rate per mileage” amount.  The “rate per mileage” is determined using mileage tiers setup or standard rate of mileage when the mileage rate tiers are not defined. 

In  the Dynamics 365 Finance version 10.0.18 (PU42) the design of Mileage tier setup has been modified to better reflect customer needs . Below you find explanation of old design and new design and recommendations to proceed once you upgrade customer database to 10.0.18 version. 

** Setting up Mileage rate Tiers** 

The difference between old and the new design of Mileage rate tiers is in Quantity field processing. 
Before 10.0.18 the Quantity field was considered as *lower limit* - when accumulation crosses that Quantity – the corresponding rate was used. 

From 10.0.18 onwards, the Quantity field is considered as the *upper limit* – and corresponding rate is used when mileage accumulation is lesser than that defined in the Quantity field.  The new model for mileage tiers helps with consistency across mileage tiers and better usability.   

All approved expense reports will be recalculated during posting according to the new design.

## Example below: 
 
The Quantity field represents lower limit of mileage. If accumulated miles/kilometers for a user crosses quantity in the field - the related rate is used. If there's no line with Zero quantity - system will use 'Standard rate of mileage' from Expense management setup. 
 
Expense report after posting with 2 lines - 1000 (rate 0.45) +  500 (rate 0.25) = 575

Design from 10.0.18
In 10.0.18 the design of mileage tiers has changed. The Quantity field represent upper limit of the tier. If all upper limits are exceeded, system will use 'Standard rate of mileage setup' from Expense management parameters. 
 
To correctly calculate the same scenario, the tier set up needs to change as below: 
If any employee exceeds total quantity of miles/kilometers 999 999 999.00 - system will use rate from 'Standard rate of mileage' from Expense management parameters. 
  
Expense report after posting with 2 lines - 1000 (rate 0.45) +  500 (rate 0.25) = 575

## Enabling the new design

The **Mileage amount calculation for multiple mileage tiers with same rate** feature addresses key bug fixes and improvements for mileage rate calculation. 
To enable this feature, go to **Workspaces > Feature Management**, select **Mileage amount calculation for multiple mileage tiers with same rate**, and then select **Enable now**.
It is necessary to setup the new tiers after upgrading to 10.0.18 to reflect new design of Mileage tiers setup. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
