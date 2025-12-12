---
title: Cost to complete methods
description: This article provides information about the methods used to calculate the cost to complete a project.
author: sigitac
ms.date: 10/27/2023
ms.topic: article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Cost to complete methods

_**Applies To:** Project Operations Integrated with ERP_

 > [!NOTE]
   > Estimates have been renamed to revenue recognition in a recent product update with the **Update labels for revenue recognition and related forms and processes in Project Operations** feature. Terminology may reference either estimate or revenue recognition depending on if the feature is enabled.

This article provides information about the methods used to calculate the cost to complete a project. There are multiple methods you can use to calculate the cost to complete a project. 

When you create an estimate for a project, on the **Create estimate** page, in the **Cost to complete method** field, you can select one of the following cost to complete methods.

| Cost to complete method    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total cost-actual            | Enter estimate costs manually in the **Total cost** or **Total quantity** fields using the **Cost estimate** button on the **Estimate page**. The system subtracts the actual costs from the totals you entered. The total is the cost to complete the project. This method doesn't use the expense estimates and resources assignments entered in Project Operations built within Microsoft Dataverse. The total cost or total quantity can be updated manually as needed.  |
| Total forecast-actual        | Resource assignments and expense estimates are used to determine the total project forecast amount. Actual costs are compared against this forecast to calculate the cost to complete.                                                                                                                                                                                                                                                                          |
| As previous estimate         | The same estimate methods that was used in the previous period is used here. This method requires a forecast model if the previous period required a forecast model.                                                                                                                                                                                                                                                                                                                           |
| Set cost to complete to zero | Typically used before the estimate project is eliminated, this method matches total estimates with posted actual transactions and clears the **Cost to complete** column. When complete, the result is always 100 percent. For each cost line that you create, the **Forecasting** check box is cleared and the total estimate is copied from the previous cost estimate. The actual consumption for the estimate period is deducted from the cost to complete the project.              |
| From cost template           | The cost to complete method that is set up in the cost template that's associated with the selected estimate project.                                                                                                                                                                                                                                                                                                                                                                          |


[!INCLUDE[footer-include](../includes/footer-banner.md)]