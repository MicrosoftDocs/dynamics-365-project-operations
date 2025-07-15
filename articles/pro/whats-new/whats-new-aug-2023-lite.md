---
title: What's new August 2023 - Project Operations Core
description: This article provides information about the quality updates that are available in the August 2023 release of Microsoft Dynamics 365 Project Operations Core.
author: ramagadu
ms.custom:
  - evergreen
ms.date: 04/09/2024
ms.topic: whats-new
ms.reviewer: johnmichalak 
ms.author: ramagadu
---

# What's new August 2023 - Project Operations Core

_**Applies To:** Project Operations Core_

This article applies to the following components and versions of Microsoft Dynamics 365 Project Operations:

- Project Operations in a Microsoft Dataverse environment version 4.75.0.56

## Features included in this release

| Feature area | Feature name | More information |
| --- | --- | --- |
|Subcontracting|**Enhanced Vendor Invoice Verification** </br></br>This feature introduces new fields that let users view real-time 3-way match progress for a vendor invoice line and ensures more accurate verification of invoices. </br>To view these updates, enable the feature flag named **Enhanced Vendor Invoice Verification**. In subsequent releases, this feature will introduce visualizations to track pending verification of invoice lines at the vendor invoice header level.| |
|Project Budgeting and Forecasting| **Project cost budget management**</br>Project cost budget management is enhanced with the following new capabilities.  </br> 1. Creation of project budget periods. </br> 2. Time phasing of project budget lines into project budget line details. </br>3. During revision, creation of project budget lines from the actuals that couldn't be matched to a budget line. </br></br>To use the project cost budget management, enable the Project budget management feature.| [Project cost budget management](/dynamics365/project-operations/pro/budget/projectbudgetmanagement). |

## Quality updates

| Feature area | Reference number | Quality update |
| --- | --- | --- |
|Billing and Pricing|3186838|Cost price list fails to default when the end date is outside the price list range.|
|Billing and Pricing|3233975|Imported estimate values don't match the estimates calculated on project.|
|Billing and Pricing|3370203|Validate ProjectParameterPriceList has a parameter reference.|
|Billing and Pricing|3419224|Material estimates should retain any price changes.|
|Opportunity Management|3107890|Transform the **Close as Lost** process for quotes into a long-running job and notify the user if the process is already in progress.|
|Project Management|2922153|When attempting to update the remaining effort for tasks, an error is thrown if the start date is later than the end date.|
|Project Management|3409749|Unable to modify the role of a team member created by a generic resource.|
|Project Management|3464455|Incorrect calculation of task start date due to Timezone difference in client and resource calendar.|
|Resource Management|3491772|Error received when using Specify Pattern on Team member grid.|
|Subcontracting|2920766|The Vendor field must be filled out when creating a subcontract, and it should throw an exception if left empty.|
|Subcontracting|3491867|Subcontract Line Resource creation leads to script error.|
