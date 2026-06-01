---
title: Cost to complete methods
description: Learn about the different methods to calculate the cost to complete a project. Explore manual and automated approaches to streamline your project estimates.
author: sigitac
ms.date: 01/30/2026
ms.topic: concept-article
ms.reviewer: johnmichalak
ms.author: sigitac
---

# Cost to complete methods

[!include[banner](../includes/banner.md)]

_**Applies To:** Project Operations Integrated with ERP_

 > [!NOTE]
   > In a recent product update, the **Update labels for revenue recognition and related forms and processes in Project Operations** feature renamed estimates to revenue recognition. Depending on whether the feature is enabled, terminology might reference either estimate or revenue recognition.

This article provides information about the methods used to calculate the cost to complete a project. You can use multiple methods to calculate the cost to complete a project.

When you create an estimate for a project, on the **Create estimate** page, in the **Cost to complete method** field, select one of the following cost to complete methods.

| Cost to complete method    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total cost-actual            | Enter estimate costs manually in the **Total cost** or **Total quantity** fields by using the **Cost estimate** button on the **Estimate page**. The system subtracts the actual costs from the totals you entered. The total is the cost to complete the project. This method doesn't use the expense estimates and resources assignments entered in Project Operations built within Microsoft Dataverse. You can update the total cost or total quantity manually as needed.  |
| Total forecast-actual        | Resource assignments and expense estimates determine the total project forecast amount. Actual costs are compared against this forecast to calculate the cost to complete.                                                                                                                                                                                                                                                                          |
| As previous estimate         | Uses the same estimate methods as the previous period. This method requires a forecast model if the previous period requires a forecast model.                                                                                                                                                                                                                                                                                                                           |
| Set cost to complete to zero | Typically used before the estimate project is eliminated, this method matches total estimates with posted actual transactions and clears the **Cost to complete** column. When complete, the result is always 100 percent. For each cost line that you create, the **Forecasting** check box is cleared and the total estimate is copied from the previous cost estimate. The actual consumption for the estimate period is deducted from the cost to complete the project.              |
| From cost template           | The cost to complete method that is set up in the cost template that's associated with the selected estimate project.                                                                                                                                                                                                                                                                                                                                                                          |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
