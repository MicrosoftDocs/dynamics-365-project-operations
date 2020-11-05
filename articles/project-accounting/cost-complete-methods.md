---
title: Cost to complete methods
description: This topic provides information about the methods used to calculate the cost to complete a project.
author: sigitac
manager: Annbe
ms.date: 11/04/2020
ms.topic: article
ms.service: project-operations
ms.reviewer: kfend 
ms.author: sigitac
---

# Cost to complete methods

_**Applies To:** Project Operations for resource/non-stocked based scenarios_

There are multiple methods you can use to calculate the cost to commplete a project. When you are creating an estimate for a project, on the **Create estimate** page, in the **Cost to complete method** field, select one of the following cost to complete methods.

| Cost to complete method    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total cost-actual            | Enter estimate costs manually in the **Total cost** or **Total quantity** fields using the **Cost estimate** button on the **Estimate page**. The system subtracts the actual costs from the totals you entered. The total is the cost to complete the project. This approach doesn't use the expense estimates and resources assignments entered in Project Operations on Common Data Service (CDS) environment. The total cost or total quantity can be updated manually as needed.  |
| Total forecast-actual        | Resource assignments and expense estimates in Project Operations on CDS are used to determine the total project forecast amount. Actual costs are compared against this forecast to calculate the cost to complete.                                                                                                                                                                                                                                                                          |
| As previous estimate         | The same estimate methods that  was used in the previous period is used here. This method requires a forecast model if the previous period required a forecast model.                                                                                                                                                                                                                                                                                                                           |
| Set cost to complete to zero | Typically used before the estimate project is eliminated, this method matches total estimates with posted actual transactions and clears the **Cost to complete** column. The result of completion is always 100 percent. For each cost line that you create, the **Forecasting** check box is cleared and the total estimate is copied from the previous cost estimate. The actual consumption for the estimate period is deducted from the cost to complete the project.              |
| From cost template           | The cost to complete method that is set up in the cost template that's associated with the selected estimate project.                                                                                                                                                                                                                                                                                                                                                                          |


